---
title: "When Context Collapses: Teaching Agents to Detect and Recover from Lost Memory"
source: "https://www.oreilly.com/radar/when-context-collapses-teaching-agents-to-detect-and-recover-from-lost-memory/"
author:
  - "[[Andrew Stellman]]"
published: 2026-06-11
created: 2026-06-27
description: "Or, how I learned to stop worrying about compaction and love the file system"
tags:
  - "clippings"
---
> *This is the eighth article in a series on agentic engineering and AI-driven development. Read part one [here](https://www.oreilly.com/radar/the-accidental-orchestrator/), part two [here](https://www.oreilly.com/radar/keep-deterministic-work-deterministic/), part three [here](https://www.oreilly.com/radar/the-toolkit-pattern/), part four [here](https://www.oreilly.com/radar/ai-is-writing-our-code-faster-than-we-can-verify-it/), part five [here](https://www.oreilly.com/radar/ai-code-review-only-catches-half-of-your-bugs/)*, *part six [here](https://www.oreilly.com/radar/why-doesnt-anyone-teach-developers-about-context-management/), and part seven [here](https://www.oreilly.com/radar/your-ai-agent-already-forgot-half-of-what-you-told-it/).*

*“640K ought to be enough for anybody.”—Bill Gates (allegedly)*

If you’re building AI agents that do complex, multistep work, you’re going to run into context loss. The agent’s working memory fills up, older information gets silently dropped or compressed, and the agent keeps going without realizing it’s forgotten something. This article, the third in my Radar article trilogy about context management, walks through a pattern I’ve been refining for detecting and recovering from that problem, which I call the **externalize-recognize-rehydrate pattern** (or **ERR**, which I think is actually a pretty good acronym for an error recovery pattern): save your agent’s state to files on disk, detect when context has degraded, and reload from those files to recover. The individual techniques are standard practice in agent and skill engineering—checkpointing, progress files, state verification—but the real power comes from combining them into a coherent workflow that you can use live or build into your agents. I’ll walk through each step with specific prompts you can adapt for your own agents and coding sessions.

Which brings me to memory. Gates has said on multiple occasions that he never actually said that quote at the top of this article, but it endures because it captures one of the core limitations of that era, one that people struggled with constantly, in a way that we can laugh about now. Around that time I was using a 286 with 1 MB of RAM. That’s megabytes, not gigabytes. MS-DOS 3.3 gave me 640K of conventional memory plus 384K of upper memory, and I spent a lot of time figuring out how to use every bit of it. I configured memory managers, loaded device drivers high, used (and wrote!) terminate-and-stay-resident programs that moved themselves out of conventional memory to free up space, and generally treated memory as a resource that required active, deliberate engineering. There was a lot I wanted to do that didn’t fit into 640K, and like most people at the time, I went to some lengths to compensate for the memory limitations.

We’re at the 640K stage of AI development. The context window is the new RAM ceiling. Most of today’s models give you somewhere between 200K and 2M tokens of working memory (and, like memory in the late 1980s and early 1990s, those numbers are growing all the time), and if you’re building agents that do complex multistep work, you will hit that ceiling. When you do, the AI starts compacting: compressing or dropping older parts of the conversation to make room. And just like running out of conventional memory on a 286, things stop working right and you’re not sure why.

In 20 years we’ll be looking back at today’s puny context windows and wondering how developers in the 2020s managed to get anything done with just a few million tokens. Because none of this is new. In case you don’t believe me, here’s a photo of my dad at Princeton in the early 1970s working on an Evans and Sutherland LDS-1 graphics computer, the first commercial vector graphics machine, connected to a PDP-10 mainframe:

![Keep on truckin](https://www.oreilly.com/radar/wp-content/uploads/sites/3/2026/06/image-12.png)

Keep on truckin

The actual LDS-1 is in the large cabinet in the background, directly behind the monitor. Sitting next to it, just out of the picture, is an even larger cabinet that holds a memory unit with *16K of magnetic core memory* (technically 8K words).

So you can imagine that just a decade later, 640K in a tiny PC that fit on your desktop seemed extravagant.

In the last two articles in this series (“ [Why Doesn’t Anyone Teach Developers About Context Management?](https://www.oreilly.com/radar/why-doesnt-anyone-teach-developers-about-context-management/)” and “ [Your AI Agent Already Forgot Half of What You Told It](https://www.oreilly.com/radar/your-ai-agent-already-forgot-half-of-what-you-told-it/) ”), I talked about what context is and why context management matters, and I shared practical techniques and prompts for keeping important information in files instead of leaving it in the AI’s context window. This article gets more technical. I want to build on those strategies and talk about how to build agents that can detect when they’ve lost context and recover from it on their own.

## Brute-forcing my way through context loss

I’ve been doing this kind of context management for a while now, long before the specific tools I’m about to describe existed. But a recent crash gave me a clean example of what the process looks like in its most brute-force form.

I was working in Copilot with a seven-step plan, going through it one step at a time, having another AI review each step before moving on. Steps one and two went fine. When it came time to do step three and I gave it the prompt, it jumped straight to step four. This kind of thing can be really frustrating, because it seems like an AI smart enough to implement a complex feature in code should be able to (ahem) count to four.

The key to not getting frustrated when the AI loses track of steps or can’t seem to count from prompt to prompt is to remember what it’s good at and how it remembers things. If the AI you’re using does that, check the conversation history. You’ll probably see something like “summarizing conversation history” or “compacting conversation” somewhere above your last message. That’s telling you that the AI lost track of where it was because that count was literally purged from its memory.

AIs are good at carrying out an instruction. They’re bad at keeping track of their own state over a long conversation, and the way they manage their memory is a big part of that. This article is about finding ways to build your AI tools so you’re not relying on them to do the thing they’re worst at.

But compaction isn’t the only way your AI loses context. A few weeks ago I was deep into a long session with Copilot, working through a multiphase code review. I’d spent a while building up context with the AI about my codebase and the decisions we’d made together. I was about to move on to the next phase, and then I got this:

![Phase B](https://www.oreilly.com/radar/wp-content/uploads/sites/3/2026/06/image-13.png)

The entire context was wiped, which could have been a really frustrating problem, since I had a long history with the session, and it had built up a lot of knowledge about what we were doing. This turned out to be a bug in Opus 4.6’s interaction with Copilot’s conversation history, and I’ve seen other people hit the same thing. I was staring at a fresh prompt with nothing in it.

So I did something that, in retrospect, is a pretty good brute-force version of what this whole article is about. I recognized the context was gone (hard to miss when the whole conversation disappears). I copied the entire conversation out of Copilot and pasted it into a text file. Then I gave the new session a prompt:

> We were in the middle of a long conversation, then I got an error and the entire context was wiped. I saved a copy of the conversation in #file:chat\_history.txt, read it and bring yourself back up to speed.

And it worked! This brought the new session back to where I needed it to be.

That simple error and recovery actually outlines a pretty good pattern for dealing with context loss:

1. **Externalize the state.** Get the important information out of the conversation and into a file on disk, where it won’t disappear when the context window reshuffles.
2. **Recognize the loss.** Notice that the agent’s working context has been wiped or degraded, whether that’s obvious (like a crash) or subtle (like output that quietly stops making sense).
3. **Rehydrate from the file.** Point a new session at that file and let it rebuild its understanding from what’s written down.

The individual mechanics are well-documented across cognitive science (cognitive offloading, task resumption), software engineering (the Memento pattern, React hydration), and knowledge management (the SECI model). I’m not claiming to have invented any of them. But the specific abstraction of these three phases into a unified, named pattern applied to AI context management is, as far as I can tell, new. It’s synthesis and codification, not invention.

In this case I did it with copy and paste, which isn’t particularly elegant, but it worked for me. But this is a blunt instrument, because a raw conversation dump is both too much and too little: it’s too much because it’s full of noise, like tool calls, dead ends, back-and-forth that doesn’t matter anymore; and it’s too little because the context that got silently compressed away during the session is already gone. When you build these mechanisms into agents and skills, you can do it in a much more subtle and automated way.

## Externalize: Add two layers of state to your agent

The idea behind **externalization**, or periodically saving your agent’s state, came out of a conversation I was having with an AI assistant while building the [Quality Playbook](https://github.com/andrewstellman/quality-playbook), an open source AI coding skill that runs structured code reviews. The playbook runs a structured code review as a single process, but that process could easily turn into a 15-million-token request if you tried to do it all in one shot. I described in the [previous article in this series](https://www.oreilly.com/radar/your-ai-agent-already-forgot-half-of-what-you-told-it/) how I broke it into six phases, and that was only possible because the context for each phase had already been externalized. Each phase reads its inputs from files, does its work, writes its outputs to files, and stops. The next phase picks up from the files, not from whatever the agent remembers. If this sounds like the familiar advice to ask the AI to plan before you ask it to implement, it’s the same principle applied to context management. Separating each step and persisting the output means you can inspect it, and the next step doesn’t depend on the agent’s memory.

But what should those files contain? I found that the AI is actually good at figuring that out. At some point I asked the assistant:

> Would it make sense for the agent to record more context in files as it progresses, to make sure nothing is dropped along the way? It should work even if you break it into separate prompts, because the result from each step is persisted. Plus, we can audit its reasoning for debugging and improvement.

That prompt was all it took. The assistant designed the file structure itself: a progress tracker that records which phase is active and what’s been completed, a JSONL artifact file (JSONL is just a file with a bundle of JSON objects, with one record per line) where each pass appends its output, and a set of brief documents describing the purpose of each phase. You don’t need to overengineer this. Tell the agent what you’re trying to preserve and let it figure out the file layout.

What emerged falls into two categories that I think of as execution continuity and task continuity:

- **Execution continuity** is the state the agent needs to resume work in the middle of a task: what step it’s on, what it’s completed, what decisions it’s made so far. These files change constantly as the agent works.
- **Task continuity** is the broader context that doesn’t change during execution: what the whole task is about, what success looks like, what the structural constraints are. These files are written once and read at every resumption.

When an agent needs to resume after suspected compaction, it reads back both layers. The task continuity files anchor it back to what the whole endeavor is about. The execution continuity files put it back in the middle of the work. Together, they give the agent enough information to continue without relying on anything that might have been compacted.

The key is that externalization isn’t something you do once at the beginning of a task. You want the agent saving its state at frequent checkpoints so that if compaction happens mid-run, the most recent checkpoint is close to where the agent was working. Here’s the kind of instruction I gave the agent for tasks that processed records one at a time:

> Update the progress file after every single record, not in batches. Write the output line first, then update the progress file with the new cursor and a fresh timestamp. If the progress file’s timestamp falls behind the output file’s, you’re batching and that’s wrong.

The frequency matters because context can compact at any point. If the agent only saves state at the end of a long run, compaction in the middle means losing everything since the start. If it checkpoints after every unit of work, the worst case is losing one unit.

Two-layer externalization survives context reshaping, not only outright context loss. Even if the agent’s context window isn’t full, if the context has been reorganized or reprioritized (a compression that reshapes without truncating), the agent can reload the external files and know for certain what the ground truth is.

## Recognize: Detecting loss from inside the agent

The second step in the pattern is to **recognize** that your agent has lost context, and it turns out to be the hardest part (at least with today’s AI technology). When the context window fills up, the AI compacts silently, and the agent keeps working without realizing it’s lost information. The agent can’t tell you it’s forgotten something, because it doesn’t know it forgot. Detecting that change turns out to be a nontrivial problem; I’ll walk you through an approach that helped me, and keep it general enough so you can do the same thing. The copy-and-paste approach works when the context loss is obvious, like a crash that wipes your whole conversation. But most context loss isn’t that visible.

I described context compaction in the [previous article](https://www.oreilly.com/radar/your-ai-agent-already-forgot-half-of-what-you-told-it/), but it’s worth restating the core problem from the agent’s perspective. Different tools handle context overflow differently: Some truncate older messages; some compress conversations into summaries; some use a sliding window. But they all have the same effect. Information disappears from the agent’s working context, and the agent doesn’t get notified.

This was a challenge when I built the Quality Playbook, because it runs multiple passes over a codebase, each one reading source files, extracting requirements, and checking coverage. Each pass can involve enough work that it fills the context window multiple times over. And when context compacts mid-pass, the agent doesn’t know it happened. It keeps working, but the output starts silently degrading. So I started building mechanisms for the agent to detect compaction and recover by reading back the files it had written earlier. The patterns that came out of that work are general enough to apply to anyone building agents that need to survive context pressure.

From the agent’s perspective, compaction is seamless. It’s tracking state, referencing decisions made earlier in the conversation, and then at some point the earlier context is gone. But the agent can’t tell the difference between “I never knew that” and “I knew it but lost it.” It tries to reference something and finds nothing, or finds a compressed version that lost the nuance. And because the agent doesn’t know it lost anything, it doesn’t know it needs to recover.

This invisibility is the core problem. But it turns out you can work around it, and the next two sections walk through how.

## Building a detection mechanism

Once you have files on disk, the question is what specifically to check and how to know when something has gone wrong. I landed on a mechanism while building the Quality Playbook’s requirement extraction pipeline. The playbook processes source documents in multiple passes, and each pass appends its output to a JSONL artifact file. After each unit of work, the agent also writes a progress record to a separate file: what it just finished, what it found, and where it should pick up next.

The detection mechanism comes from two rules I gave the agent. The idea is that the progress file tracks a cursor, which is just a position marker that tells the agent which record to process next. If the agent writes a record to the output file but then loses context before updating the progress file, those two files will be out of sync.

The agent didn’t need to understand any of that upfront; I just described the rules in plain language and let it figure out the implementation. The first rule establishes an invariant between the output file and the progress file:

> Cursor advances only after the line is on disk. Write the summary line to the output file first, then update the progress file. The cursor must always equal the index of the next record that still needs to be processed.

The second rule told the agent how to check that invariant on startup:

> On startup, read the progress file. Resume from its cursor value. Verify continuity: the last line in the output file should equal cursor minus one. If not, roll the cursor back to match disk state and report the discrepancy.

If the progress file says the cursor is at record 381, but the last line in the output file is record 379, something happened. The context compacted and the agent lost track of where it was. The divergence between the two files is the signal.

This worked because files on disk don’t change when context compacts. They’re written once and then read repeatedly. If what the agent thinks it knows doesn’t match what’s actually in the files, something shifted in the agent’s memory, not on disk. I ended up folding this check into a preamble that every session started with:

> If this session has experienced auto-compaction, re-read the pass specification from disk. Do not try to reconstruct it from the compacted summary. Read the progress file. Read the last record of the JSONL artifact and confirm its index equals the cursor minus one. If not, roll the cursor back to match disk state. Disk is the source of truth. The conversation is not.

That preamble ran at the top of every session. During one particularly intensive day of pipeline development, I ran over a hundred Claude Code sessions with that exact instruction. Most of them completed without hitting compaction. But the ones that did hit it recovered cleanly, because the preamble told the agent exactly what to check and exactly what to do when the check failed.

The specific prompts I used are tied to the Quality Playbook’s file structure, but the technique generalizes. If you’re building any agent that does multistep work, you can adapt the same approach. Here’s a version you could drop into a session preamble or an agent’s system prompt:

> Before continuing any task, read your progress file and your most recent output file. Compare them: does the progress file say you’ve completed work that isn’t reflected in the output? If so, trust the output file, roll back your progress to match, and note the discrepancy. Do not rely on what you remember from the conversation. The files on disk are the source of truth.

The wording doesn’t have to be precise. What matters is the structure: tell the agent where to look, what to compare, and which source to trust when they disagree.

## But didn’t you just say the AI can’t detect its own compaction?

Right, and it can’t. What I described above isn’t the agent detecting compaction. It’s the agent running a deterministic check against files on disk and finding a discrepancy. The agent doesn’t need to know that compaction happened. It just needs to notice that two files disagree. Think of the agent as an amnesiac clerk. You don’t ask the clerk to remember what they did yesterday. You make the clerk check the physical ledger every time they sit down at the desk. If their notes disagree with the ledger, they’re trained to trust the ledger.

If you saw Christopher Nolan’s breakout movie *Memento*, you can think of your agent as Leonard Shelby, the character played by Guy Pearce with anterograde amnesia. You couldn’t ask Leonard to remember what he did yesterday. He had to check his tattoos every time he woke up. If his tattoos disagreed with what he’s seeing, he trusts the tattoo (which leads to a major plot point, which I won’t spoil). Again, this isn’t a new idea either. I mentioned the [Memento pattern](https://en.wikipedia.org/wiki/Memento_pattern) earlier, which is literally named after this movie.

This is a classic distributed systems technique. In double-entry bookkeeping, you maintain two independent records of the same transaction and reconcile them regularly. If they disagree, you investigate. You don’t need to know why they diverged; the divergence itself is the signal. A two-phase commit works the same way: write the data first, then update the record that says the data was written. If you find data without a matching record, or a record without matching data, something went wrong between the two phases.

That’s exactly what the cursor invariant does. The agent writes the output line first, then updates the progress file. If those two files are out of sync, something happened between the two writes. The agent doesn’t detect compaction. It detects a broken invariant, and it’s been told that when the invariant breaks, the files on disk win.

Three things make this work. First, the check is purely deterministic: read two files, compare two numbers, act on the result. There’s no reasoning involved, no judgment call about whether the agent “feels” like it lost context. I wrote about this principle in “ [Keep Deterministic Work Deterministic](https://www.oreilly.com/radar/keep-deterministic-work-deterministic/) ”; you never want an AI making decisions that a file comparison can make for it. Second, the files on disk don’t change when context compacts. They’re the stable reference point that the agent’s memory gets checked against. Third, the instruction to run the check lives in the system prompt or preamble, which is generally preserved even when conversation context gets compacted. The check survives the thing it’s designed to detect.

## Rehydrate: Reading back the state

**Rehydration** is the process of reading back externalized state and rebuilding the agent’s working context. Once the agent detects compaction (or, more specifically and accurately, has enough evidence from the filesystem that compaction occurred), the recovery step is to read back the externalized files and rebuild. For the Quality Playbook, rehydration meant:

1. Read the phase brief to re-anchor the purpose of this pass
2. Read the progress file to know which unit is active and what’s been completed
3. Read the tail of the JSONL artifact to confirm the last successfully written record
4. Recompute the next unit of work from those files

This is different from just continuing without detection. Without detection, the agent tries to pick up where it left off and hopes it still has enough context. With detection, the agent knows something happened and deliberately reloads state before continuing.

You can make the rehydration process itself auditable. Instead of silently reading the files and resuming, have the agent write down what it learned:

> Read the progress file and the JSONL artifact. Write a summary of what you learned: what pass is running, what unit is active, what the cursor position is, and how many requirements have been extracted so far. Then continue from there.

Writing a rehydration summary serves two purposes. It gives you visibility into what the agent understood and whether it rehydrated correctly. And it forces the agent to process the external files explicitly rather than just loading them into context. Explicit processing is more reliable than silent loading because the agent has to commit to an interpretation, and you can read that interpretation and catch mistakes.

You can adapt this approach to any agent workflow where work happens in steps. The specific files and cursor values are particular to my pipeline, but the underlying technique is general: have the agent write its progress to a file after each step, and check that file against its output at the start of every session. And this advice isn’t just for writing agents or skills. Even in a live session with Claude Code, Cursor, or Copilot, you can tell the agent to periodically write a summary of what it’s done and what it plans to do next to a file on disk. If the session crashes or the context gets long enough to compact, you can point a new session at that file and pick up where you left off. The key is getting the state out of the conversation and onto disk before you need it.

## Context management is an architectural concern

Every technique I’ve described in these articles comes down to the same principle: Important information shouldn’t live only in the agent’s context window. The previous articles covered how to put that information on disk. This one covers how to make the agent aware of its own limitations so it can recover when context pressure gets too high.

An agent that can detect its own degradation and correct for it is fundamentally more reliable than one that just keeps going. When the agent knows how to stop, check itself against ground truth, and reload what it lost, context pressure becomes a recoverable event instead of a slow, silent failure.

This concludes my mini-series trilogy of articles about context management. The first article in this series was about understanding what context is and why it disappears. The second was about getting important information out of the conversation and onto disk before you need it. This one is about closing the loop: making the agent aware of its own limitations so it can detect degradation and recover from it. Together, they add up to treating context as an engineering problem rather than something you hope works out.

These are still early days. Context windows will get larger, compaction will get smarter, and some of the workarounds in this article will eventually be unnecessary. But the underlying principle won’t change: If your agent’s ability to do its job depends on information, that information needs to live somewhere more durable than working memory. That was true for my dad’s 32KB core memory at Princeton, it was true for my 640K of conventional RAM, and it’s true for today’s 200K-token context windows.

*The [Quality Playbook](https://github.com/andrewstellman/quality-playbook) and [Octobatch](https://github.com/andrewstellman/octobatch) are open source projects where these techniques are used in production. Both are built using AI-driven development and available for exploration if you want to see how this looks in practice.*

---

*Disclosure: Aspects of the approach described in this article are the subject of US Provisional Patent Application No. 64/044,178, filed April 20, 2026, by the author. The open source Quality Playbook project (Apache 2.0) includes a patent grant to users of that project under the terms of the Apache 2.0 license.*

Post topics: [AI & ML](https://www.oreilly.com/radar/topics/ai-ml/ "AI & ML")