---
type: "Context Architecture"
title: "Context Selection And Compaction"
description: "Context selection decides what evidence the model sees for a request."
tags: ["context-architecture"]
---

# Context Selection And Compaction

## Current Understanding

Context selection decides what evidence the model sees for a request. The model does not remember the repository; every step only knows the instructions, selected history, file excerpts, command output, tool results, and task details that the harness provides.

More context can reduce guessing, but it can also increase cost, latency, and distraction. Compaction summarizes, drops, or selects context so the useful evidence stays in view while unrelated history, stale files, and oversized tool output stay out of the request.

The [ADLC source](../../../raw/processed/ADLC Claude Code's New Lifecycle for AI Coding.md), [deep research workshop source](../../../raw/processed/Full Workshop Build Your Own Deep Research Agents - Louis-François Bouchard, Paul Iusztin, Samridhi.md), and [agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md) converge on the same operating rule: large context windows do not remove the need for selection. Context can rot before the nominal window is full, so the harness needs explicit context ownership, compaction rules, and source routing.

The [context engineering source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) reinforces the local production-infrastructure lens: scoped inputs, durable knowledge layers, retrieval rules, and context governance need to be designed before agents are allowed to run multi-step development or operations workflows. Broad context-engineering taxonomy stays upstream; this page keeps the local selection and compaction rule.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) add a bootstrapping case: when agents work against proprietary code, internal SDKs, custom frameworks, or technologies absent from model training, context selection starts with baseline evals, concise durable instructions, reference implementations, current API surfaces, and diagnostic errors. Public vendor identity stays upstream; locally, this is a rule for teaching unknown project reality without flooding the request.

The [lost-in-the-middle source](../../../raw/processed/So Long and Thanks for All the Context.md) adds a placement rule for long-context work. Larger context windows reduce some retrieval failures, but load-bearing instructions and source facts can still be ignored when buried in the middle of a long request. Important constraints should be externalized, curated into a short request package, placed near the beginning or near the point of use, and verified against disk state when the agent claims to know them.

The [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md) adds a compression-layer pattern for agentic workloads. Tool outputs, verbose JSON, web pages, code files, and repeated message history should not enter the model unchanged when a local or governed context layer can route, compress, cache-align, and preserve retrievable originals. The local rule is to make compression reversible or auditable when the removed detail may matter later.

The [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) adds structured-output and memory-control signals. Context selection should account for repeated tool-call shapes, JSON payloads, reasoning traces, metadata filters, hybrid search, TTL behavior, and update paths. The local practice is to select compact structured context when it preserves the task contract, while keeping exact originals recoverable for audit, repair, or access-control review.

The [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json) reinforces active-versus-durable context selection. A request package should assemble the smallest active working set from durable decisions, artifacts, memory records, and auditable storage while preserving enough origin and freshness evidence to avoid treating stale memory as current instruction.

The [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json) adds coding-agent context-loop and graph signals. Context selection should decide which instructions, repository knowledge, tool results, tests, runtime feedback, work items, decisions, dependencies, and customer or operational signals enter each generation step. The local rule is to retrieve current relevant context for the loop stage rather than throwing every available artifact into the model and hoping the agent finds the live constraint.

The [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json) adds context-engineering technique signals for compression, hierarchy, scoping, and state externalization. Context selection should classify task scope before broad retrieval, especially for simple tasks where repository-wide reading wastes tokens and can distract the model. Secondary summaries should be treated as pointers until the original source is verified.

The [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json) and [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json) add a context-distraction rule. Context engineering is not only about adding missing project knowledge; it also rejects irrelevant connectors, stale memories, oversized summaries, and attractive but unauthoritative snippets that distract the agent from the current work.

## Practice Boundaries

- Orient from repository structure, relevant modules, tests, package boundaries, and existing conventions before selecting context.
- Attach compiler errors, failing tests, stack traces, screenshots, runtime logs, and recent diffs when they are the evidence for the next step.
- Keep stable rules, exact file excerpts, failing assertions, recent diffs, and rerun commands in the request package when they support the task.
- Avoid sending the whole policy manual, full history, or unrelated exports when a targeted excerpt is enough.
- Use summaries for prior turns when exact transcripts are less useful than the current decision state.
- Re-select context after tool calls or verification output changes the diagnosis.
- Treat context rot as an operating risk, not only a token-limit problem.
- Keep context ownership visible so stale examples, stale policies, and obsolete source files can be removed from the agent diet.
- Define context sources, retrieval rules, and compaction ownership before enabling recurring or multi-step agent workflows.
- For proprietary or unfamiliar technology, use baseline evals to find the model's wrong closest match, then add the smallest durable instructions, current API evidence, reference examples, and diagnostic feedback that correct that gap.
- Keep the working set small for critical actions; do not rely on a large middle section of accumulated context to carry the rule that matters now.
- Put load-bearing instructions, current progress, and source facts at the beginning of a session brief or directly beside the action that needs them.
- Use deterministic disk checks when an agent's claim about context, progress, or source content must be trusted.
- Treat context compression as a harness policy decision with routing, reversibility, cache behavior, provenance, and sensitive-field handling, not only as token trimming.
- Preserve a way to recover compressed originals when an agent may need exact JSON, source code, logs, identity fields, or access-control evidence.
- Select compact structured context for repeated tool-call or JSON shapes only when exact originals, metadata filters, retention rules, and update paths remain recoverable.
- Assemble active context from durable decisions, artifacts, memory records, and auditable storage with freshness and origin labels.
- Keep stale durable memory out of the active working set unless a current disk or source check confirms it still applies.
- Select context per loop step from instructions, repository knowledge, tool results, tests, runtime feedback, decisions, dependencies, and operational signals.
- Prefer current relevant context graphs and freshness checks over bulk loading when agent work depends on work-management, code, documentation, or customer signals.
- Classify task scope before repository-wide retrieval, and prefer narrow source checks when the task can be answered or edited from a small evidence set.
- Treat secondary summaries of context-selection research as pointers until original papers or source artifacts are verified.
- Keep durable instructions concise and source-backed; context expansion should be driven by task evidence needs, not by appending every prompt, ticket, or prior conversation.
- Pair context-engineering changes with task-matched evals so compression, routing, and retrieval do not silently remove rationale, constraints, or source provenance.
- Treat secondary commentary about vendor context-window changes as a routing signal until primary sources verify product behavior.
- Test context selection against mock or representative workflows that include both relevant sources and plausible distractors.
- Prefer source inventories, freshness labels, and exclusion notes over broad connector enablement when agents need work context.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Context router and knowledge layers](context-router-and-knowledge-layers.md)
- [Request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [ADLC source](../../../raw/processed/ADLC Claude Code's New Lifecycle for AI Coding.md)
- [Deep research workshop source](../../../raw/processed/Full Workshop Build Your Own Deep Research Agents - Louis-François Bouchard, Paul Iusztin, Samridhi.md)
- [Agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [Lost-in-the-middle source](../../../raw/processed/So Long and Thanks for All the Context.md)
- [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md)
- [context state externalization and rehydration](context-state-externalization-and-rehydration.md)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json)
- [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json)
- [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json)
- [July 22 topic news collector source](../../../raw/processed/2026-07-22/ai-dev-wiki-topic-news-collector-2026-07-22T203140-0400.json)
- [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json)
- [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [thin context router](thin-context-router.md)
- [rules and knowledge layers](rules-and-knowledge-layers.md)
- [ai process layer and workflow state](../application-patterns/ai-process-layer-and-workflow-state.md)
- [context state externalization and rehydration](context-state-externalization-and-rehydration.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on request context, token discipline, context windows, compaction, and evidence selection.
- Maintained on 2026-06-23 with public context-engineering guidance framed as production infrastructure for multi-step agents.
- Maintained on 2026-06-25 with proprietary-code bootstrapping guidance for baseline evals, concise instructions, reference examples, and current API evidence.
- Maintained on 2026-06-27 with lost-in-the-middle placement and disk-verification rules for long-context work.
- Maintained on 2026-06-30 with reversible context compression, cache-alignment, provenance, and sensitive-field handling guidance.
- Maintained on 2026-07-07 with structured-output selection, memory metadata filters, TTL behavior, update paths, and recoverable originals.
- Maintained on 2026-07-12 with active-versus-durable context selection, freshness labels, origin labels, and stale-memory checks.
- Maintained on 2026-07-15 with per-loop-step context selection, current-context graph signals, and freshness controls.
- Maintained on 2026-07-16 with task-scope classification, narrow-retrieval controls, and secondary-summary verification boundaries.
- Maintained on 2026-07-22 with concise durable-instruction, task-matched eval, and primary-source verification boundaries.
- Maintained on 2026-07-24 with context-distraction, source-inventory, freshness-label, and representative distractor-test guidance.
