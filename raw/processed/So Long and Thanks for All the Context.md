---
title: "So Long and Thanks for All the Context"
source: "https://www.oreilly.com/radar/so-long-and-thanks-for-all-the-context/"
author:
  - "[[Andrew Stellman]]"
published: 2026-06-25
created: 2026-06-27
description: "The fourth article in my context management trilogy"
tags:
  - "clippings"
---
I got a really interesting question last week from Mike Loukides, my editor at Radar, after he read the third part of this trilogy on context management. “Another issue I’ve read about,” Mike asked, “is the tendency for a model to ignore the middle of the context. I’ve seen that particularly for the models with very large context windows. Is there anything to be said about that?”

Excellent question, Mike, and yes, there is. In that same email he pointed out that clearing the context and reloading it with just what’s important does a pretty good job dealing with this “ignore the middle” problem when it happens, but that’s clearly a stopgap.

It’s worth a deeper dive into what’s actually happening when an AI starts forgetting what’s in the middle of its context, because the problem is deeper (and more interesting!) than it might seem at first. It turns out that there’s a basic problem that’s fundamental to how LLMs manage context, and we’re still learning about it as an industry. That problem is called a **U-shape**. There’s been a lot of really interesting research into the U-shape problem recently, and several useful techniques have emerged that can help you manage it. And it’s probably not a coincidence that I’ve had to use all of them in my [ongoing experiments with AI-driven development and agentic engineering](https://www.oreilly.com/radar/the-accidental-orchestrator/) (even if I didn’t always realize that’s what I was doing at the time).

A few weeks ago, in fact, I ran into the exact failure mode that Mike described. I was running the [Quality Playbook](https://github.com/andrewstellman/quality-playbook), my open source code quality engineering skill, and ran into trouble with one of its phases—the one that writes up the bugs the earlier phases find. There’s a part of the bug writeup process where it had just created a file called `BUGS.md` that had an overview of each of the bugs, and had to create individual writeups for each bug it found. But instead of filling in the details correctly, it produced skeletal-looking stub files, with a generic template that had blank values instead of populated ones.

The thing is, the instructions for how to write a populated writeup were in the prompt. The actual bug data was in `BUGS.md`. I was absolutely certain that everything the agent needed was sitting in its context window, because I could see that it hadn’t compacted yet, and the skill’s intermediate artifacts let me see that earlier phases had read and reasoned about both files (which I talked about in my last article in this series). But the agent was producing stubs anyway. It really looked like the agent had everything it needed sitting in plain sight, and just wasn’t using the information it had. Frustrating!

I thought at the time that the model was just an idiot (which, arguably, was true but beside the point). It turns out that I had run directly into the U-shaped context problem.

In the previous three articles I covered [what context is](https://www.oreilly.com/radar/why-doesnt-anyone-teach-developers-about-context-management/) and why it disappears, how to [keep important information in files](https://www.oreilly.com/radar/your-ai-agent-already-forgot-half-of-what-you-told-it/) instead of leaving it in the agent’s context window, and how to [detect and recover](https://www.oreilly.com/radar/when-context-collapses-teaching-agents-to-detect-and-recover-from-lost-memory/) when context has been compacted out from under you. All three were about losing context, through fragmentation, through compaction, through long sessions that overrun the window. This article is about this entirely different U-shaped failure mode, where the context is still sitting in the window and the model just isn’t using it.

## The U-shape failure, and why bigger windows don’t fix it

The U-shape is an active area of academic investigation, so I’m going to start by going into a little bit of that research, because I think it will actually help us pin down what’s going on. I’ll start with an experiment run by [Nelson Liu](https://cs.stanford.edu/~nfliu/), an AI researcher at Stanford, who tested how language models actually use the contents of long inputs by giving them documents with the relevant answer placed at different positions and measuring whether the model could still find it. An interesting thing his findings show is that the U-shape didn’t appear to be a quirk of a single model. The U-shape showed up across model families, and even models with larger context windows still exhibited it.

If you have time, it’s actually worth taking a look at the paper that Liu and his team wrote, called “ [Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/abs/2307.03172).” (It’s surprisingly readable for an academic paper.) The result they reported was a robust U-shape: The model performed best when the relevant information was at the beginning of its context window or at the recent end and worst when it was in the middle. Performance on questions where the answer was buried mid-context fell off sharply, even when the answer was sitting right there in plain sight. The field now uses the terms primacy bias and recency bias for those two preferences, and the U-shape is what you get when you plot them together against position.

I’m going to lean a little into academia here, because a lot of researchers are still learning about how LLM context actually works and what behavior has emerged in it.

One reason the U-shape matters more than “just another LLM quirk” is that recent research has started showing it’s a structural property of how transformers work, not a learned artifact. A 2025 ICML paper called“ [On the Emergence of Position Bias in Transformers](https://arxiv.org/abs/2502.01951) ” explained it as the equilibrium between two opposing forces inside the model: The causal mask amplifies the influence of the first few tokens (the primacy bias), while position encodings like RoPE heavily weight the tokens closest to where the model is generating (the recency bias). The middle is where those two forces cancel out. A 2026 paper by Borun Chowdhury, a researcher at Meta, called “ [Lost in the Middle at Birth: An Exact Theory of Transformer Position Bias](https://arxiv.org/abs/2603.10123),” took the argument even further by proving mathematically that the U-shape exists at the moment of initialization, before any training has happened, with random weights.

That matters because the natural assumption about large context windows is that more room means fewer problems. Most of today’s frontier models give you a million tokens or more, with some pushing well past two million, and some have made real progress on the simplest version of the lost-in-the-middle test, the needle-in-a-haystack benchmark, where the model has to retrieve a single sentence buried in a long document. Google’s Gemini 1.5 Pro reported near-perfect single-needle recall at 1M tokens, and current Gemini 3 models are similar.

So the accurate version of “bigger windows don’t fix it” is this: Bigger windows have made simple single-fact retrieval much better. They have not made long-context agent work reliable by default. A two-million-token window means a bigger middle to fall into.

The important idea that’s emerging here is that it’s increasingly looking like the U-shape isn’t just a bug in today’s models that will eventually be worked out or trained away by more data or better fine-tuning. Instead, it seems like the U-shape may actually be a geometric property of the LLM architecture itself.

In other words, we’re all going to have to deal with the U-shape. And that means we need techniques for managing it, and any effective technique we use isn’t likely to become obsolete any time soon. And that’s my goal in this article: to show you the techniques that have emerged for managing U-shaped context memory loss that you can use today in your own work.

## Five techniques to help with U-shaped context problems

The previous article in this series laid out a pattern for detecting and recovering from context loss, which I called *externalize-recognize-rehydrate*. The techniques below extend the same discipline to the lost-in-the-middle problem. The principle I keep coming back to is that working memory is untrustworthy, and the discipline that follows from it is to externalize what matters, curate what stays in context, and verify what the agent claims to know against what’s on disk. The five techniques are how I do that in practice, and each one is drawn from a real moment in the Quality Playbook’s development.

### Curate, don’t accumulate

This is the technique which, in its most brute-force form, is exactly what Mike talked about in his email to me: just clear the context and reload it with just what matters, periodically and deliberately. In other words, don’t trust an accumulated session to stay coherent; build the artifact, then start fresh against it. And if you have the AI write down the important parts of the context (like we’ve talked about throughout this series), then you can start a new session with refreshed AI that has a more targeted, curated context as a starting point.

I ran into this during the v1.5.2 release prep for the Quality Playbook. I was using a long Claude Code session that had been working through a series of fixes. But I noticed that it was just starting to show its age: It had forgotten a couple of things it should know, and its thinking times were starting to grow.

When it came time to land the final four fixes for the release, I worked with the AI to write a **context brief**, or a separate document with everything the implementing session needed. The question was whether to keep using the existing session, which already “knew” the codebase from the earlier work, or open a fresh CLI session and point it at the brief. I asked another session what to do:

> `Should we run that in a new cli session rather than continue my current `
> `claude code session that has the existing context?`

The AI gave me a good answer—start a fresh session, using a starting prompt to read the brief—and it gave three reasons that have stuck with me. First, the brief was self-contained, including file paths, line numbers, exact diffs, regression test bodies, and preflight greps. Anything the new session needed to know was already there, and continuing context bought nothing. Second, fresh context is stricter about adherence. A session that already “knows” the codebase tends to skim the new instructions and improvise from prior assumptions. Surgical fixes are exactly the case where you want the agent to read the brief carefully rather than rely on memory of what felt right last round. And third, the audit trail: The brief is the artifact, and the implementing session is reproducible from just the brief. If the same work has to be redone in six months by a different model, you point at the brief and say, “This is the input.”

The approach worked really well. I was able to pick up development seamlessly, and the model’s memory problems disappeared.

### Position critical information at the edges

The U-shape says the model attends best to the beginning and end of its context. The natural move is to put your most load-bearing information in those positions and keep the middle for things you don’t need the model to focus on. Anything important that lives only in the middle of an accumulated context tends to slide out of attention.

The other side of this technique is what *not* to put in the middle. If something matters, don’t bury it in a long preamble of context you’ve been accumulating; move it to the edges, restate it where the model will act on it, and let the middle absorb the less important material. Luckily, there’s a useful technique that can help with this problem.

In Claude Code, for example, one really clean way to put information at the beginning of context is to use the system prompt. The CLI gives you `--append-system-prompt` for exactly this. (Most of the other providers’ CLI tools have similar options.) If you put your brief (or selected parts of it) there, the agent will attend to it strongly throughout the session, and that in turn will help keep the per-turn user prompt focused on the action you want the agent to take right now.

### Short sessions over long ones

Don’t run one long session. Run many short ones, each reading fresh from disk. This will help you iterate on your brief and your external development context, so instead of relying on an opaque context window, you have a visible and constantly changing set of documents that give you a lot more visibility into—and control over—your AI’s context.

Something useful I started doing was taking all my chat history from Gemini, ChatGPT, Claude, and Cowork and putting it into a single folder I could keep updated and indexed for fast search. I built out an entire system to manage this, which turns out to be a great tool when I’m writing articles like this, because I can search through my development history for specific examples and techniques that I’ve used. The system uses Haiku 4.5 to read through chat history, summarize what happened, and create an index. Haiku turned out to be a smart enough model to read each individual interaction in a chat and write a useful index entry for it. But the model being smart enough to do one summary didn’t mean its context management could keep up across all 18,000 records. I ran smack into the U-shape problem.

The first attempt tried to keep dedupe state and progress counts in the model’s head, and it failed spectacularly. The model really didn’t want to keep track of specific deterministic things like accurate numbers or the current state. Haiku 4.5, in particular, seems especially bad at this. What worked was reframing the architecture entirely. Here’s the actual prompt that I gave it to fix the problem:

> `ok, so we need context management. it doesn't need to remember things, `
> `it just needs to write them down as they go. we had this same context `
> `management problem with Quality Playbook, when it was running out of `
> `context. Just write down after each message.`

The protocol I greenlit for the full run made the short-session discipline explicit:

1. Resume processing from the cursor recorded in progress.json, working through each input file in order.
2. Update progress.json after every line.
3. Expect to run out of context well before finishing—that’s fine. Just stop cleanly after each step (or a group of steps), then spin up a fresh session that reads progress.json and continues.
4. When all files are complete, set status: “complete” in progress.json and report back.

Item 3 is the technique in one line: expect context loss, so make sure you’ve written your state down, and build fresh restarts into the process. The technical details, like spinning up subagents, orchestrating with script, etc., will change, but the core idea stays the same. In a lot of ways, you can think of treating the agent like a pipe, not a database. The state lives on disk, and the session is something you throw away and replace.

### Restate key info close to the point of use

When the model needs a constraint to apply right now, repeat it right now. Don’t trust an instruction from earlier in the session to carry forward through the middle of the context.

This is the technique that fixed the problem I opened the article with, where the Quality Playbook seemed to forget everything it had just written into a file called `BUGS.md` and produced stubs when it needed to write the same information into more detailed files, and instead writing generic blank templates with the bug-specific fields left blank.

The fix was to restate the read-the-source rule right before the action that needed it, using this prompt:

> `Before writing BUG-NNN.md, re-read the BUG-NNN entry in BUGS.md. `
> `Copy the Spec basis, Minimal reproduction, Location, Expected behavior, `
> `Actual behavior, Regression test name, and Patches fields `
> `from that entry into the writeup. Do not paraphrase from memory.`

“Do not paraphrase from memory” is the line that did the actual work. The instruction couldn’t trust the agent’s memory of what `BUGS.md` said, even though `BUGS.md` was sitting right there in the context window. So the instruction forced a fresh read of the file at the moment of writing. The restatement and the fresh-read together fixed the bug.

The same pattern applies any time a rule was stated earlier in the session and the model needs to act on it now. Restate the rule next to the action, and force the model back to the source rather than letting it work from memory.

### Test the middle

The previous four techniques are about avoiding lost-in-the-middle failures. This one is about catching them. If you don’t know whether the agent is actually using the information you think it’s using, find out, with a deterministic check rather than a judgment call.

The pattern is the one I used in the Haiku summarizer that I described earlier: compare what the agent claims to know against what’s on disk. You have something the agent claims to know (its progress, its current state, the latest version of a rule), and you have something on disk that’s the ground truth (a file, a log, a database record). At the moment the agent’s claim has to be trusted, you check it.

In the summarizer’s resume protocol, every new session started by cross-checking `progress.json` against the actual last line written to the summary file, and the agent printed a checkpoint report when it did—at session start, and periodically through the run. A representative one looked like this:

> `Checkpoint Report:   ✓ progress.json confirmed: cursor for cowork_04_06 is at 238, status is `
> `"running"   ✓ Disk state verified: Last line in summaries/cowork_04_06.md is [237] `
> `assistant: Tool invocation repeating chat file read.    Discrepancy noted: The prior session left a bulk note claiming records `
> `238–296 are duplicates but didn't write individual lines for them. Per `
> `your instructions, I must write one line per record, even for duplicates, `
> `in the format [idx] <sender>: Duplicate of record [X] (<note>).   Status: Cursor matches disk state. Ready to resume from record 238.`

The agent doesn’t need to introspect whether it lost context, only to compare two files. When they agree, the agent proceeds; when they disagree, the agent flags the discrepancy and stops before adding any new work on top of a broken state. Disagreement is the signal.

You can build this kind of check into any agent that does multistep work. Pick something the agent has to track, pick the file that’s the source of truth for it, and have the agent compare the two at every session start. When the agent’s view of the world drifts from the file, you find out before the drift becomes a buried bug.

## The discipline behind these techniques

When I built the Quality Playbook’s multi-phase architecture, I was solving the compaction problem. Long pipeline runs were filling the context window and triggering silent compaction in the middle of work. Breaking the pipeline into separate phases that read fresh from disk and stopped after each phase fixed it.

What I didn’t realize until later was that the same architecture also helps with the lost-in-the-middle problem. Each phase has its own short, focused context, with the phase brief at the beginning and the latest progress update at the end, so there’s almost no middle for information to fall into. The architectural move that helped with working memory disappearing turns out to also help with working memory being there and unused.

That’s the lesson I want to land. Both failure modes, context loss and lost-in-the-middle, are problems of working-memory unreliability, and the discipline that addresses them is the same: keep the working set small, put the load-bearing information at the edges of the window, and check the agent’s claims against ground truth on disk when it matters.

Context windows will keep getting bigger, and compaction will get smarter. Some of the techniques in these four articles may eventually be unnecessary. But the underlying constraint won’t disappear. After all, we’ve added a lot more RAM to our computers since the 1MB 286 I wrote about in the last article, and memory management has gotten much more complex since then. And many of these problems are structural; for example, it’s increasingly looking like the U-shape itself is a geometric property of the transformer architecture, not a training artifact that more compute will smooth out.

The bottom line is that if your agent’s ability to do its job depends on information, that information needs to live somewhere more durable than working memory. That was true for my dad’s 32 kilobytes of core memory at Princeton in the 1970s, it was true for my 640 kilobytes of conventional RAM on my 286 in the 1980s, it was true for the 200K-token windows in last year’s models, and it will be true for whatever comes next.

Post topics: [AI & ML](https://www.oreilly.com/radar/topics/ai-ml/ "AI & ML")