---
title: "what does theo have to say about Codex ultra mode"
source: "https://www.perplexity.ai/search/b22cbc6c-41dd-4d4c-b9e1-8fe62e761416"
author:
published:
created: 2026-07-18
description: "Perplexity is a free AI-powered answer engine that provides accurate, trusted, and real-time answers to any question."
tags:
  - "clippings"
---
Theo’s take is that Codex “ultra” mode is kind of a trap right now: it burns a ton of tokens by cascading ultra-level effort into every subagent, without giving proportional gains over cheaper settings.[youtube](https://www.youtube.com/watch?v=t8hfOyF4ehw&list=WL) digg+1

## What he actually says

- In his recent “we need to talk about ultra mode in Codex” video, he calls Ultra “a mess” because one intensive run can chew through a five‑hour limit in under 20 minutes.[youtube](https://www.youtube.com/watch?v=t8hfOyF4ehw&list=WL)
- His core complaint is that Ultra is exposed as a “reasoning level,” but under the hood it behaves more like a skill that keeps spawning max‑reasoning sub‑agents repeatedly.[youtube](https://www.youtube.com/watch?v=t8hfOyF4ehw&list=WL)

## Subagents inheriting Ultra

- Theo points out that if you set `gpt‑5.6‑sol` to Ultra in Codex, all subagents it spawns are also set to Ultra.digg+1
- He considers this “a fumble” because it causes “massive token burn for no good reason” and argues he should be able to hard‑set subagent effort to something like *medium* (e.g., Terra/Luna tiers).explainx+1

## How he actually works around it

- Theo’s practical guidance is to avoid blanket Ultra and instead use programmatic orchestration and workflows to route which pieces of work really need high effort.digg+1
- He notes that using `gpt‑5.6‑sol` via other harnesses (like Claude Code / Claudex) can yield better designs and lower token usage than Codex Ultra, for the same or better quality.[explainx](https://explainx.ai/blog/gpt-5-6-sol-claude-code-claudex-setup-guide-july-2026)
- His broader pattern: keep the “max”/Ultra tiers as an escalation path when cheaper modes miss the bar, not as the default.[zeronoise](https://zeronoise.ai/posts/harnesses-demo-loops-and-routing-rules-cjehkefgma/download/pdf)

## Implications for your own use

- Treat Ultra as a surgical tool: reserve it for genuinely hard reasoning or critical code changes, not entire workflows with lots of spawned agents.[digg](https://digg.com/tech/pbldkjj3) [youtube](https://www.youtube.com/watch?v=t8hfOyF4ehw&list=WL)
- Where possible, route sub‑tasks (tests, refactors, boilerplate, migrations) to lower‑tier models and only escalate the tricky design/architecture pieces.digg+2

If you tell me how you’re using Codex (IDE plugin vs CLI, solo dev vs team), I can sketch a concrete routing/limits strategy that aligns with Theo’s advice but fits your setup.

what's the difference between max and ultra

Max is “one model thinking as deeply as it can,” while Ultra is “a small team of maxed‑out agents working in parallel on one job.”llm-agent+2

## Conceptual difference

- Max is the top single‑agent reasoning level on the normal scale (Light → Medium → High → Extra High → Max) and just gives one agent more time and budget to plan, check, and revise.distk+1
- Ultra is not on that scale at all: it’s a multi‑agent mode that splits a task across several coordinated agents (by default around four) and runs them in parallel.readinsightvault+2

## How they behave in Codex

- With Max, Codex keeps one agent on the task and lets it take more “passes” internally, so you pay for extra depth but not for a swarm of agents.llm-agent+1
- With Ultra, Codex delegates sub‑tasks to separate agents at max‑level reasoning, which is why people complain about token burn and rate‑limit hits when Ultra is left on by default.[youtube](https://www.youtube.com/watch?v=t8hfOyF4ehw&list=WL) daily+1

## When to use which

- Use Max when you have a single, hard, relatively linear problem that benefits from deeper thought (e.g., a tricky algorithm change, complex refactor, or architecture decision).readinsightvault+2
- Use Ultra only when the work can be decomposed into meaningful, semi‑independent pieces (e.g., big repo‑wide changes, multi‑service feature work, large documentation or test‑generation sweeps), and you explicitly want parallelism enough to justify the extra cost.u7buy+2

One useful mental model from the docs: **Max is depth, Ultra is width.**[u7buy](https://www.u7buy.com/blog/gpt-5-6-reasoning-modes-explained/)

Follow-ups

SearchComputer

Model