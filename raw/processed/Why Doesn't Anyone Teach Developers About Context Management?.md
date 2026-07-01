---
title: "Why Doesn't Anyone Teach Developers About Context Management?"
source: "https://www.oreilly.com/radar/why-doesnt-anyone-teach-developers-about-context-management/"
author:
  - "[[Andrew Stellman]]"
published: 2026-05-14
created: 2026-06-27
description: "We overestimate what AI can remember and underestimate what it can orchestrate."
tags:
  - "clippings"
---
> *This is the sixth article in a series on agentic engineering and AI-driven development. Read part one [here](https://www.oreilly.com/radar/the-accidental-orchestrator/), part two [here](https://www.oreilly.com/radar/keep-deterministic-work-deterministic/), part three [here](https://www.oreilly.com/radar/the-toolkit-pattern/), part four [here](https://www.oreilly.com/radar/ai-is-writing-our-code-faster-than-we-can-verify-it/), and part five [here](https://www.oreilly.com/radar/ai-code-review-only-catches-half-of-your-bugs/).*

I think context management is one of the most important skills in AI-driven development, and it’s weird that compared to other AI-related topics, almost nobody talks about it. We talk about prompt engineering, about which model to use, about agentic workflows and tool use. But more than anything else, the thing that actually determines whether your AI session produces good work or mediocre work is how well you manage context (or if you even do it at all!).

A lot of developers using AI tools treat all this “context” talk as AI jargon that can be dismissed, and it’s not hard to understand why. AI development tools have gotten so easy that an experienced developer can be incredibly effective by just combining vibe coding with critical thinking (that’s the central idea behind [the Sens-AI Framework](https://www.oreilly.com/radar/the-sens-ai-framework/)), and not really think about context at all. That’s ironic, because despite all the “I’m functionally illiterate but I just vibe coded an entire multitenant SaaS platform” articles, and despite everyone’s general concern that AI will put all developers out of work, the development skills you’ve been working on for years make you especially effective at writing code with AI—and context management is where those skills really shine.

Just to make sure we’re all on the same page, **context** is (basically) everything the AI is thinking about right now: your prompt, the conversation so far, the files it’s read, the decisions you’ve made together. When you start a fresh session with an AI, its context is wiped clean, and it starts fresh with just the initial instructions it’s been given. Managing context is central for building AI agents and skills. But it’s also really important when you’re using tools like Claude Code, Cursor, or Copilot for day-to-day development work. Context is typically measured in tokens, and there’s a finite amount of it. When the **context window**, or the maximum amount of information (input and output tokens) an AI model can process and retain at once, fills up, the AI starts losing track of things, and that’s when you start to see it give wrong and weird answers.

Unfortunately a lot of developers read paragraphs like the last one and their eyes glaze over. Somehow it gets classified in the same part of our brains as learning how our build systems work: boring stuff we somehow don’t really want to think about because it takes us away from “real” programming. That’s a shame, because when we don’t understand the basics of how context works we waste a lot of time.

For example, here’s something I see developers do all the time that they absolutely shouldn’t. They’re deep into an AI coding session, and the AI has built up a detailed understanding of their codebase (e.g., it’s noticed patterns, it’s making good decisions, etc.). Then they start seeing “Compacting conversation” messages, or they notice the little context usage indicator in Cursor or Copilot filling up, and they don’t really know what that means. But they learned that closing the session and starting a new one seems to fix the problem. Unfortunately, all they’ve done is trade compaction for total amnesia. The new session just keeps going, producing output that looks fine, but it’s giving worse answers and generating worse code because it’s working from incomplete information.

The really weird thing is that I was writing about something really similar all the way back in 2006, long before AI was around, in [*Applied Software Project Management*](https://learning.oreilly.com/library/view/applied-software-project/0596009488/): Missing requirements are especially insidious because they’re difficult to spot. I was writing about requirements, not AI context, but the problem is the same. I’ve [written about how prompt engineering is requirements engineering](https://www.oreilly.com/radar/prompt-engineering-is-requirements-engineering/), and this is another place where the parallel holds up. When a requirement is missing, there’s no artifact to flag it, you just end up with code that doesn’t do what it’s supposed to do. When context is missing from an AI session, there’s no error message telling you what the AI forgot; you just end up with worse answers.

The cost of poor context management is actually measurable. A developer on [Microsoft’s Dev Blog](https://devblogs.microsoft.com/all-things-azure/i-wasted-68-minutes-a-day-re-explaining-my-code-then-i-built-auto-memory/) recently timed his own reorientation overhead and found he was spending over an hour a day just reexplaining things to his AI that it had known in a previous session. He’s not alone. There are now entire frameworks and managed services dedicated to giving agents persistent memory, from lightweight CLIs that query Copilot’s local session database to managed memory services from Cloudflare. Some of these tools are genuinely useful, but they’re solutions you need to evaluate, integrate, and maintain before they help you.

My goal in this article and the next is to give you four specific things you can do today, using whatever AI tools you’re already working with. This article covers the problem: why context management matters and how context loss affects the quality of your AI’s output. The next article covers the specific practices that emerged from building the [Quality Playbook](https://github.com/andrewstellman/quality-playbook) and [Octobatch](https://github.com/andrewstellman/octobatch), things you can bring back to your own prompts, skills, and agents immediately. I’ll use real examples from those projects, because I think they’ve got some good examples that you can draw on.

## We get AI wrong in both directions

I think the through line through all of this is that developers both overestimate and underestimate AI. We overestimate how much it can hold in its memory and its ability to remember things and make decisions for us. So we’ll just stuff a whole bunch of stuff in the context window and assume the AI will work it out, and then get annoyed when it hallucinates or forgets.

On the other hand, we massively underestimate its ability as an orchestrator. Your prompt doesn’t just have to ask a question or ask the AI to generate something. You can give it a multistep workflow where each step writes its results to files, and the AI will coordinate the whole thing, spinning off subtasks and picking up where it left off if something breaks.

When developers don’t take either of those things seriously, context management or orchestration, you get a specific cycle. They treat the context window as infinite and cram everything in. Then when the session gets too long and the AI starts losing track, they throw it all away and start fresh. They never consider the alternative, which is designing the workflow so the AI works from externalized files across independent sessions.

I discovered this while building the [Quality Playbook](https://github.com/andrewstellman/quality-playbook). The context management was working so well inside my sessions that I realized the sessions themselves were the bottleneck. I was running the playbook in a single prompt. I think I had a record of over 15 million tokens in a single Copilot GPT-5.4 session that ran for hours, and I did eight of them in parallel. Which incidentally is why I got rate-limited for 54 hours from Copilot, which is completely fair.

The playbook was writing everything down to files as it went, which is why those runs could last that long at all. But I didn’t want that behavior. Running 15 million tokens in a single session is expensive, and if you’re on pay-as-you-go API tokens instead of a flat-rate plan like Copilot or Claude Max or Cursor, that kind of usage can be a real shock. I wanted to make the playbook available to developers who don’t want to burn that much at once. And because the context was already externalized to files, splitting into independent phases turned out to be easy.

## Ask the AI to write its context down along the way

Before I get into how the pipeline splits things up, I want to talk about the practice that made the split possible in the first place: storing development context in files as you go.

I don’t mean asking the AI to export its notes at the end of a session, or writing up a “lessons learned” document after the fact. I mean baking it into the actual instructions you give the AI from the start, so it’s continually writing and updating context as it works. For Octobatch, the batch LLM orchestrator that was my first experiment in agentic engineering (I wrote about the development process in “ [The Accidental Orchestrator](https://www.oreilly.com/radar/the-accidental-orchestrator/) ”), I had the AI write developer context in every folder, and that really made it easy to spin up a new session.

Here’s what that looks like in practice. Every new Claude Code session on Octobatch starts with a single line: “Read ai\_context/DEVELOPMENT\_CONTEXT.md and bootstrap yourself to continue development.” That file contains a loading sequence: read this first, then fan out to component-level CONTEXT.md files in scripts/, tui/, pipelines/, each describing its own subsystem at the right level of detail. By the time the AI finishes reading, it knows what the project is, how it’s built, what’s currently in progress, and what the active bugs are.

I think of this as shifting left. Instead of putting constraints in every prompt (don’t use additionalProperties: false, always test with –limit 3), those rules live in the CONTEXT.md files. The prompt stays clean because the documentation does the heavy lifting.

And updating context files is part of every task. Before we commit anything, I have the AI review the context files and make sure they reflect what we just did. If we added a feature or fixed a bug, the context file should reflect that before we commit. Stale context causes the same kinds of problems as stale documentation, except it’s worse because the AI is actually relying on it to make decisions.

I want to be clear exactly what I mean by “development context.” Specifically, it’s the information a new AI session needs to get up to speed: what the project is, how it’s built, and what decisions have been made along the way. Tools like Claude Code read development context from files like [AGENTS.md](http://agents.md/) (and you can actually go to that website to learn more) at the start of every session, and if you do a thorough enough job of building up your development context and keeping it up-to-date, you can get them fully bootstrapped. They’re the blueprints for your AI sessions. I wrote in *Applied Software Project Management* that building software without requirements is similar to building a house without blueprints. Running AI sessions without externalized context is the same mistake. You’re relying on what’s in someone’s head instead of what’s written down. And when you’re working with AI, “someone’s head” is a context window that’s going to get compacted or thrown away.

The most important thing is that what’s in my head matches what’s in the AI’s head. The context file is just a convenient way to help us figure out whether or not we agree. When I start a new Claude Code session on a folder that has a good DEVELOPMENT\_CONTEXT.md, the AI reads it and we’re immediately aligned. When I start a session without one, the AI has to rediscover everything from scratch, and it always misses things. Rediscovery is always lossy.

If you’re not already writing context files as part of your workflow, none of the fancier techniques I’m about to describe matter. This is the foundation.

## Include the why, or the AI will undo your decisions

There’s a specific thing that has to go into these context files, and it took me a while to learn why it matters so much: the reasoning behind every decision.

Octobatch’s DEVELOPMENT\_CONTEXT.md has a section called “Key Technical Learnings” with 49 entries, each in a specific format: What happened, Why it matters, When we discovered it, and Where in the code it applies. At the top of that section is a note in bold: “IMPORTANT: Always include the REASONING (the ‘Why’) for each learning. This prevents future sessions from ‘refactoring’ a deliberate decision.”

That note is there because without it, the AI will do exactly that. I had a case with Octobatch where we used recursive set\_timer() instead of set\_interval() for auto-refresh because Textual’s set\_interval() callbacks aren’t reliably serviced on pushed screens. Without the “Why” in the context file, a future session would look at that code, see a “cleaner” alternative, and helpfully refactor it right back to the broken approach.

The same principle applies to quality standards. Don’t just say “90% coverage for core logic.” Say “90% coverage for core logic, because expression evaluation touches randomness and seeding, where subtle bugs produce plausible-but-wrong output. The drunken sailor reseeding bug passed all visual inspection. Only statistical verification caught that sequential seeds created correlation bias (77.5% fell in water instead of a theoretical 50/50).” Without the “why,” a future AI session will argue the coverage target down. Any standard or architectural decision or unusual code pattern that doesn’t have its rationale attached is vulnerable to being optimized away by an AI that doesn’t know what problem it was solving.

## The garbage collection problem

A lot of people like to talk about the context window as your AI’s short-term or working memory, and context that’s persisted to disk as long-term memory. Personally, I’m not sure those analogies to human memory work all that well. I think it’s a lot more useful to find ways to think about context that are similar to how we manage memory in our code.

I find it especially helpful to compare context compaction to garbage collection—again, not a perfect analogy but a useful one. When you look at a GC graph in Java, you see the memory slowly fill up and then suddenly drop after each GC. That drop is the runtime figuring out what’s still being referenced and freeing everything else.

The context window does the same thing. Your conversation accumulates tokens, the AI’s context window fills up, and then compaction happens. The tool (or the model) decides what to keep and what to throw away. Compaction is lossy and automatic, and you don’t control what survives.

Java developers spent decades learning to design their allocation patterns so garbage collection wouldn’t destroy anything important. AI developers need to learn the same thing, and the learning curve should be shorter because the concepts transfer directly.

When you ask the AI to write important state to files, you’re promoting it out of that volatile space. It’s surprisingly easy to do this. Just pass the AI to write its context to a Markdown file. For example, you can put all of the context related to a specific domain into a particular file, like if the AI noticed a behavioral contract, you could have it write all the related context to a file called CONTRACTS.md. If it made a design decision, that could go into DEVELOPMENT\_CONTEXT.md—that’s a pattern I use all the time to write down all the important contacts needed to bootstrap a new AI session to work on the code. Those files live on disk, outside the context window, and compaction can’t touch them. But if you start a new session without externalizing any of this, you’re shutting down the application and losing everything that was in memory.

The first time I built Octobatch’s batch orchestrator, it was a Python script with in-memory state and a lot of hope. It worked for small batches but fell apart at scale, which is pretty much what most developers are doing with their AI context right now: keeping everything in the context window and hoping it holds together, even though that stops working once sessions get long and codebases get complex.

## It’s way too easy to fall into one context management extreme or the other

The Quality Playbook exists in part because of this problem. When I was building the requirements pipeline, I discovered that single-pass requirement generation runs out of attention after about 70 requirements. The model forgets behavioral contracts it noticed earlier. And it’s completely invisible. You don’t get a stack trace or an error message or any kind of warning, just incomplete output and no way to know what’s missing.

The longer a defect goes uncorrected, the more entrenched it becomes and the more things get built on top of it. Context drift works the same way. When the AI loses track of a design decision early in a session, everything built on that lost context compounds the error. And just like a late-discovered defect, you don’t know what went wrong because the original context is gone.

I had a concrete example when I was running the playbook against virtio-win. Version 1.3.32 found four bugs. Version 1.3.33, after some changes, found only one. That regression was only diagnosable because I had EXPLORATION.md, an externalized intermediate state file that captures what the AI observed during its exploration phase. Without it, the only observable output would have been “fewer bugs this time.” I had no way to tell whether the playbook was worse, or the bugs were harder, or it had just missed something. Without externalized state, I couldn’t have answered any of those questions.

The contracts file in the pipeline exists specifically to solve this. When the model forgets about a behavioral contract it noticed earlier, that forgetting is normally invisible. But with a contracts file, every observation is written down before any requirements work begins. If a contract is in the file but has no corresponding requirement, that’s a visible, greppable gap. You can see what was forgotten and fix it.

But it’s just as easy to overcompensate. If the LLM has to constantly hop between eight different reference files, its context window fragments and you start getting hallucinations. I’ve seen this happen. You load all your context files and requirements documents and design docs into the session, and the AI gets worse, not better. It spends all its attention navigating between reference files instead of thinking about the problem.

I hit this with the Quality Playbook when I expanded the scope of a run against virtio-win from 10 files to about 60. The result was 6x more files analyzed but 75% fewer bugs found. The model burned its context on device drivers instead of going deep on the transport layer where the bugs actually were. Wider scope meant shallower analysis.

The goal isn’t to save everything. You have to decide what to externalize, what to keep in context, and what to let go. The best context file contains exactly what the AI needs for this session and nothing more.

## Helping your AI manage its context helps you too

The interesting thing about all of this is that good context management really makes use of your development expertise, and it’s one of those things that makes you a better developer the more you do it. Every practice I’ve described in this article, writing down your decisions, recording why you made them, being deliberate about what goes into a session and what doesn’t, is something developers have always been told to do. We write ADRs and design docs and inline comments explaining nonobvious choices, and we all know we should do more of it. When you’re working with AI, the cost of not doing it becomes immediate and visible. Your context files end up being the project documentation you should have been writing all along, except now there’s something on the other end that will actually go wrong if you skip it.

And once you start thinking about context as something you actively manage, you can start designing your workflows around it. That’s what happened with the Quality Playbook, when it went from a single 15-million-token session to a set of independent phases with clean handoffs between them, and the whole split worked on the first try because the context was already externalized to files.

In the next article, I’ll get into the specific techniques you can use today in your AI agents, but also in your day-to-day AI development work.

*The* [*Quality Playbook*](https://github.com/andrewstellman/quality-playbook) *is open source and works with GitHub Copilot, Cursor, and Claude Code. It’s also available as part of* [*awesome-copilot*](https://awesome-copilot.github.com/#file=skills%2Fquality-playbook%2FSKILL.md)*.*

---

*Disclosure: Aspects of the approach described in this article are the subject of US Provisional Patent Application No. 64/044,178, filed April 20, 2026 by the author. The open-source Quality Playbook project (Apache 2.0) includes a patent grant to users of that project under the terms of the Apache 2.0 license.*

Post topics: [AI & ML](https://www.oreilly.com/radar/topics/ai-ml/ "AI & ML")