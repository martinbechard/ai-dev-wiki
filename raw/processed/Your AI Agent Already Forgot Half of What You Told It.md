---
title: "Your AI Agent Already Forgot Half of What You Told It"
source: "https://www.oreilly.com/radar/your-ai-agent-already-forgot-half-of-what-you-told-it/"
author:
  - "[[Andrew Stellman]]"
published: 2026-05-28
created: 2026-06-27
description: "How to keep agents and skills from losing track mid-workflow"
tags:
  - "clippings"
---
> *This is the seventh article in a series on agentic engineering and AI-driven development. Read part one [here](https://www.oreilly.com/radar/the-accidental-orchestrator/), part two [here](https://www.oreilly.com/radar/keep-deterministic-work-deterministic/), part three [here](https://www.oreilly.com/radar/the-toolkit-pattern/), part four [here](https://www.oreilly.com/radar/ai-is-writing-our-code-faster-than-we-can-verify-it/), part five [here](https://www.oreilly.com/radar/ai-code-review-only-catches-half-of-your-bugs/)*, *and part six [here](https://www.oreilly.com/radar/why-doesnt-anyone-teach-developers-about-context-management/).*

This is the latest article in my Radar series on AI-driven development and agentic engineering, and I have to admit that this one took a bit of a turn I wasn’t expecting.

In my [last article](https://www.oreilly.com/radar/why-doesnt-anyone-teach-developers-about-context-management/) I talked about context and context management and I promised to give you some real practical tips for using it. It was originally meant to be about specific, practical context management techniques that were really helpful to me building [Octobatch](https://github.com/andrewstellman/octobatch) and the [Quality Playbook](https://github.com/andrewstellman/quality-playbook), two open source projects where I work with AIs to plan and orchestrate all of the work and every line of code is written by AI tools like Claude Code and Cursor.

But as I was writing this, I found that I’d adapted those same techniques to my work writing articles like this one. Which is surprising! I’ve been doing all this work finding ways to help people developing AI skills improve context management, so their skills run more efficiently. It turns out that those same exact techniques apply to anyone using AI tools, even when you’re using chatbots like Claude.ai or ChatGPT.

Full disclosure: I use multiple AI tools to manage this article series. My primary tools are Claude Cowork for brainstorming and managing my article research, notes, and backlog and Gemini’s mobile app for reading drafts aloud and taking my notes while I’m away from my desk. And I want to tell you about something that happened while I was using those tools, because I think it really helps show why context management isn’t just a problem for developers.

While I was writing this article, I was using Gemini’s mobile app to read the draft aloud and take my notes. Partway through the session I asked it to go back and check whether there were earlier notes it hadn’t incorporated yet. It told me it didn’t have access to the previous notes, which seemed weird and insane, since we had *just taken those notes a few prompts earlier in the session*. I could scroll back up and see them earlier in the conversation, but somehow it didn’t “know” about them.

Here’s what happened. Gemini had compacted our conversation without telling me, and the notes from the first half of the session were just… gone.

If you’ve ever had a web chat AI just seem to forget things you talked about earlier, you’ve experienced context compaction, just like I did. Understanding even the basics of context and context windows can make a big difference in preventing that kind of frustration.

This all reminded me of something I wrote more than two decades ago in *[Applied Software Project Management](https://learning.oreilly.com/library/view/applied-software-project/0596009488/)* (back in 2005!): “Important information is discovered during the discussion that the team will need to refer back to during the development process, and if that information is not written down, the team will have to have the discussion all over again.”

Jenny Greene and I wrote that about human teams and project meetings, but it applies to AI sessions just as well.

Which brings me back to context, which I wrote about in my last article, and which I’ll write more about in the next one, because it’s one of the most important concepts to keep top of mind when working with AI.

### Context loss may be invisible, but that doesn’t make it any less frustrating

**Context** is everything the AI is holding in its working memory during a conversation: what you’ve told it, what it’s told you, any files or instructions it’s read, and whatever internal notes the system has made along the way. All of that lives in a fixed-size **context window** —think of that as your AI’s short-term memory, the stuff it’s thinking about right now—and when the window fills up, the AI has to start letting things go. Different tools handle this differently: Some truncate older messages, some compress the conversation into a summary (which means details get lost even though the summary looks complete), and some just start behaving inconsistently so you can’t tell whether the AI forgot something or never understood it in the first place. The result is the same: The AI loses track of things you told it, decisions you made together, or details it noticed earlier in the session. And it won’t tell you it forgot. It’ll just keep generating confident-sounding output based on whatever it still has.

Before we dive in a little deeper, I want to do a quick jargon check. If you’ve seen the terms “skills” and “agents” floating around but aren’t sure what they are, think of skills as libraries for AIs and agents as interactive executables. Those aren’t perfectly precise definitions, but if you’re a developer they’re close enough for this discussion.

When you’re coding skills and agents, you run into context problems quickly. The work you’re asking the AI to do is often complex enough that the context window fills up, and the AI has to start compacting: compressing or dropping older parts of the conversation to make room for new ones. Compaction always seems to happen at the most frustrating and inconvenient time, which makes sense when you think about it. You hit context limits precisely when you’ve put the most information into the conversation, which is exactly when losing that information costs you the most.

That’s why I think it can often help to think of AIs as having the same shortcomings that human teams do, except those shortcomings are exaggerated by their AI nature. A person who forgets something from a meeting last week might remember it when you remind them. An AI that lost something to context compaction won’t, because the information is gone. But there’s something you can do about it, and it turns out the techniques that help are the same whether you’re building autonomous AI skills or just trying to get a chatbot to remember what you told it 20 minutes ago.

I’ve landed on four techniques that I come back to over and over again. Each one exists because at some point the AI forgot something important and I responded by putting that thing in a file where it couldn’t be forgotten. None of them require special tooling. And to my surprise, all of these techniques have turned out to be useful for both building software and managing a writing project like this one, whether I’m chatting with Claude, ChatGPT, or Gemini, or using a desktop tool like Claude Cowork or Codex. These are the techniques I find most valuable:

- **Split discovery from documentation:** Don’t ask the AI to figure something out and produce polished output in the same pass.
- **Use handoff documents, not continuation prompts:** Before closing a stale session, have the AI write down everything the next session needs to know.
- **Give the AI an acceptance criterion, not a procedure:** Tell it what “done” looks like instead of spelling out the steps.
- **Use spec documents as the bridge between AI tools:** Make a shared document the single source of truth that all your tools read from.

### Split discovery from documentation

When you ask an AI to do something complex, you’re often asking it to do two things at once without realizing it. You’re asking it to figure something out and produce polished output at the same time. The problem is that figuring things out takes attention, and producing output takes attention, and the model only has so much of it. When you combine both tasks in the same prompt, the model starts cutting corners on one of them, and you can’t tell which one it shortchanged.

I ran into this with the [Quality Playbook](https://github.com/andrewstellman/quality-playbook), an open source AI coding skill I built that runs structured code reviews against any codebase. One of the things it does is derive requirements from source code: It reads through the code, identifies what the code promises to do (I call these behavioral contracts), and then produces a requirements document. Originally this all happened in a single pass. The problem was that single-pass requirement generation ran out of attention after about 70 requirements. The model forgot behavioral contracts it had noticed earlier in the code, and the forgetting was completely invisible. There was no stack trace or error message, just incomplete output and no way to know what was missing. I fixed it by splitting the work into two separate prompts:

> *Read each source file and write down every behavioral contract you observe as a simple list in CONTRACTS.md.*
>
> *Read CONTRACTS.md and the documentation, then derive requirements from them and write REQUIREMENTS.md.*

Then a third pass checks whether every contract has a corresponding requirement, and if there are gaps, goes back to step one for the files with gaps.

The key idea is that CONTRACTS.md is external memory. When the model “forgets” about a behavioral contract it noticed earlier, that forgetting is normally invisible. With a contracts file, every observation is written down before any requirements work begins, so an uncovered contract is a visible, greppable gap. You can see what was forgotten and fix it.

The principle: Don’t ask the AI to figure out what exists and write formatted output in the same pass. The model runs out of attention trying to do both at once. Whenever you’re asking an AI to do something complex, consider whether you’re actually asking it to do two things at once. “Analyze this codebase and write a report” is two tasks. “Read this document and suggest improvements” is two tasks. Split them, and let the first pass write its observations to a file before the second pass starts working with them.

### Use handoff documents, not continuation prompts

Anyone who’s spent a long session with an AI coding tool has felt the moment when the context starts to go stale. The AI stops tracking details it was handling fine an hour ago, or it contradicts something it said earlier. The session gets slow, and you’re often restarting because the AI seems to have gotten bogged down and filled up on what you told it. You get the sense that if you keep going, you’re going to spend more time correcting it than making progress.

Most developers respond to their session getting too long in one of two ways: They push through the problem, or they start a fresh one and try to reexplain everything from scratch. Both of those approaches can cause the AI to lose context. The first loses it to compaction; the second loses it to incomplete reexplanation. And both are frustrating! Specifically because you just spent so much time building up all that context with the AI.

There’s a third option. Before you close the session, ask the AI to write a handoff document: a file that captures everything the next session needs to know, written while the current session still has full context. The key is that you’re asking the AI to write this while the relevant details are still fresh in the working context, and in a way that it or another AI can read.

I built this into the Quality Playbook as a core part of how phases communicate. When I split the playbook from a single prompt to independent phases, I needed each phase to run as a completely independent session with no context carryover. So each phase got its own kickoff prompt as a standalone file. Here’s the structure each one follows:

> *Write a handoff document that a fresh session could use to pick up this work cold. Include everything it would need to know.*

Every kickoff opens with what prior phases accomplished, includes explicit boundaries about what’s frozen, and names which future phase owns each piece of remaining work, because without it the AI will helpfully start doing Phase 3 work while you’re still in Phase 2. Each phase also ends with a required forward-looking handoff where the completing agent writes down what the next session needs to know.

The principle: Each handoff is a complete state snapshot. The incoming AI agent never needs to read prior kickoff prompts or chat history. Everything it needs is in the current handoff file: current state, uncommitted changes, immediate next task, pending tasks, file locations, and anything that was discovered during the prior session. A fresh AI session can pick it up cold.

If you’re deep into a Claude Code or Copilot session and you can feel the context getting stale, ask the AI to write a handoff document before you close the session. Tell it to include everything a fresh session would need to continue the work. Then start a new session and point it at that file. A fresh session with a good handoff document will usually outperform a stale session, because it’s starting with clean context instead of compacted, fragmented context.

### Give the AI an acceptance criterion, not a procedure

When you give an AI a multistep task, the natural instinct is to spell out the steps. First do this, then do that, then combine the results. The problem is that step-by-step procedures are the first thing the AI forgets when the context window fills up. It’ll skip steps, merge phases, or quietly drop tasks, and there’s nothing in the procedure itself that would help the AI notice what it missed. The procedure tells the AI what to do, but it doesn’t tell the AI what “done” looks like.

I learned this the hard way with the Quality Playbook. The playbook runs multiple iteration passes over a codebase, and the results need to be cumulative. It keeps a list of all the bugs it finds in the code being tested in a file called BUGS.md. Early on, I gave the AI a procedure to run four times and then update that file:

> *First run the main pass, then run four iteration passes, then merge the findings into BUGS.md.*

The AI did not respond well to that instruction.

It turns out that when you ask an AI to do a very complex task a specific number of times, it can lose count. In fact, from my experimentation, it seems that count is one of the first casualties of context compaction. Most of the time the AI decided three iterations was enough, or merged findings from only two passes, and no matter how many different ways I tried to rephrase that instruction, there was nothing I could come up with that prevented the problem.

However, everything changed when I replaced the “run four times” instruction with an **acceptance criterion**, or a specific condition that tells the AI when to stop looping:

> *You are done only when BUGS.md contains the cumulative findings from the main run plus all four itration passes.*

Even when the AI lost track of intermediate steps, it could check the output against the criterion and know whether it was finished. And I could verify the output against the same criterion, which gave me a way to audit the agent’s work without watching every step.

In developer terms, the AI is really bad at loops like *for (i = 0; i < 4; i++)* because it loses track of the value of the iterator *i* when it compacts its context. But it’s really good at loops like *while (!done)* because it can check *done* based on the current state without relying on history.

The principle behind all this is that an acceptance criterion survives context pressure because the AI can always check “Am I done?” against a concrete test. This is actually the same principle behind test-driven development: write the test before the code so you know when you’re done. The acceptance criterion is the test for your AI session. When you’re giving an AI a task that has multiple steps, don’t describe the steps. Describe what “done” looks like, and let the AI figure out how to get there.

### Use spec documents as the bridge between AI tools

Most developers working with AI don’t use just one tool. You might use Claude for design, Cursor for coding, and Copilot for quick edits. You might even use multiple models inside the same tool, like GPT-5.5 and Opus 4.7 in separate Copilot chats inside VS Code. It’s common to have one model for coding, another for review, and a third for orchestration and project management. The problem is that none of these tools or chats know what you told the others. Claude doesn’t know what you decided with Cursor. Two separate Copilot chats in the same editor don’t share context. You’re the one carrying context between them, and that’s exactly the kind of lossy handoff that causes drift. A design decision you made in one conversation gets lost or distorted by the time it reaches the tool that needs to implement it.

The fix is to make the spec document the single source of truth that all your AI tools read from. I used this when building a game prototype, where I had Claude handling design and planning and Cursor doing the coding. They never talked to each other directly, so the spec documents served as the shared contract: Claude wrote the specs, and Cursor read them. The rule I followed was simple:

> *Never tell the AI coder something that isn’t already in the specs. If you make a design decision in conversation, write it into the spec first, then point the coder at the spec.*

If I made a design decision in a conversation with Claude, that decision had to be written into the spec before I told Cursor about it. If I discovered something during implementation, I wrote it into the appropriate doc first, then pointed the coder at it. The spec was always the single source of truth. When Claude and I changed the wound topology (removing one wound type, promoting another), we updated the docs first, then told Cursor to reread them. When we decided to add a new UI element, we wrote it into the UI spec first, then told Cursor to reread the doc.

The key was including rationale in the specs. Not just “show 5 progressive labels” but why: “The player shouldn’t be told what they’re fighting. They should discover it.” This helps the AI coder make better decisions when the spec doesn’t cover an edge case because it knows the intent behind the requirement.

The principle: The spec document is the shared context that all your tools can read. It prevents the drift that happens when design intent lives only in chat history that the other tool can’t see. This technique works any time you’re using more than one AI tool on the same project, which at this point is most projects.

### How these techniques combine: Managing this article series

Those four practices came out of AI-driven development work, but they apply to almost any AI work. And while these techniques emerged for me while working on agents and skills, I think it’s valuable to demonstrate them in a nondevelopment context, so I’ll share an example from my work on the article series you’re reading now.

Over time, the process for how my AI assistant and I manage this article backlog evolved organically in conversation, but it was never written down anywhere except in the AI’s context window. Which means every time the session compacted or I started a fresh chat, the process was gone and I had to reexplain it. I caught this when the AI did something slightly wrong and I wanted to confirm we were on the same page. So I asked:

> *Every time I suggest a new article idea, you add an entry to the backlog, and then create a new markdown file with the source material, right?*

That’s split discovery from documentation. I didn’t say “document our process.” I said “confirm what we do.” Discovery first, then documentation as a separate step. If I’d said “write up our process” without confirming first, the AI might have written something plausible but wrong, and I wouldn’t have caught the discrepancy.

Once we’d confirmed the process, I asked the AI to create two files. **AGENTS.md** is an emerging standard for AI-readable project context—a single file that tells any AI session what it needs to know about a project. You can learn more about the convention at [agents.md](https://agents.md/). **CONTEXT.md** serves a similar role as a bootstrapping document—it’s less established as a standard, but the practice of asking the AI to dump everything it knows into a context file so the next session can pick it up cold has been one of the most valuable habits I’ve developed. Here’s the prompt I used:

> *Update the backlog file to explain what it is and how we maintain it. Create a CONTEXT.md with everything you’d need to bootstrap a new chat. Create an AGENTS.md to make it easy to bootstrap with a single-line prompt.*

That prompt is a handoff document. I was explicitly asking the AI to write down everything it knew while it still had full context, specifically because I knew that context would be lost to compaction. The CONTEXT.md file is a handoff from this session to whatever fresh session picks up the work next week.

Notice what I didn’t say. I didn’t give step-by-step instructions for what should go in those files. I said “everything you would need to bootstrap this process again in case we lost it” and “a complete dump of all of the context you would need to bootstrap a new chat and get it to the point where this current chat is.” Those are acceptance criteria, not procedures. The AI had to figure out what belonged in those files. If I’d given it a procedure (“first write the publication history, then the voice rules, then the file locations”), it would have followed the list and missed anything I forgot to include. The acceptance criterion is harder to satisfy but more robust: the test is “Could a fresh session bootstrap from these files alone?”

And the AGENTS.md file itself is a spec document as a bridge between tools. It’s the shared contract that any AI session, whether it’s Claude, Gemini, Cowork, or a fresh chat, can read to get aligned with the project. This session wrote it; the next session reads it. The two sessions never communicate directly, so the spec file bridges the gap between them.

That’s all four practices in two prompts, applied to something as ordinary as managing a writing project. It didn’t require pipelines or codebases or batch orchestration. The practices work because they solve the same underlying problem regardless of the domain: important information living in the AI’s context window instead of on disk.

### Context management is a development skill

Every practice I’ve described in this article and the last one is something developers have always been told to do: write things down, record your rationale, be deliberate about what you save and what you let go, write ADRs and design docs and inline comments explaining nonobvious choices. We’ve always known we should do more of it. When you’re working with AI, the cost of not doing it becomes immediate and visible.

The practices in this article all come down to the same thing: putting the important information in files where compaction can’t touch it, so you can see what the AI knows and verify that it matches reality. In the next article, I’ll go deeper on the debugging angle: how to use externalized files to understand what your AI is actually doing, with practical techniques that work even if you’re not building agents but are just using a chatbot.

*The [Quality Playbook](https://github.com/andrewstellman/quality-playbook) is open source and works with GitHub Copilot, Cursor, and Claude Code. It’s also available as part of [awesome-copilot](https://awesome-copilot.github.com/#file=skills%2Fquality-playbook%2FSKILL.md).*

---

*Disclosure: Aspects of the approach described in this article are the subject of US Provisional Patent Application No. 64/044,178, filed April 20, 2026 by the author. The open source Quality Playbook project (Apache 2.0) includes a patent grant to users of that project under the terms of the Apache 2.0 license.*

Post topics: [AI & ML](https://www.oreilly.com/radar/topics/ai-ml/ "AI & ML")