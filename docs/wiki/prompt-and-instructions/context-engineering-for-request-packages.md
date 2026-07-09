---
type: "Prompt And Instructions"
title: "Context Engineering For Request Packages"
description: "Context engineering is the local practice of selecting project data, coding conventions, documentation, source labels, and verification expectations for a specific request."
tags: ["prompt-and-instructions"]
---

# Context Engineering For Request Packages

## Current Understanding

Context engineering is the local practice of selecting project data, coding conventions, documentation, source labels, and verification expectations for a specific request. It is broader than prompt wording because it decides which evidence and rules the model can see while doing the work.

The request package should carry enough context for the model to act with less ambiguity without loading unrelated history. The AI-assisted coding deck frames repository understanding as request packaging, context assembly, retrieval, and verification evidence. The Hypervelocity Engineering source describes context engineering as supplying project data, conventions, and documentation so AI work becomes more accurate and can use smaller or task-specialized models.

The local boundary is practical: context engineering decides what to include, [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md) decide where stable guidance lives, and [request packages and file boundaries](request-packages-and-file-boundaries.md) decide how the selected material is labeled inside the request.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) add a scaling rule: when coding agents become default, context packages need stronger written artifacts such as issues, RFCs, concise instructions, reference implementations, current API evidence, and verification expectations. Compaction and handoffs should preserve the current decision state instead of only preserving chat history.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) adds a story-file and semantic-layer signal. Spec-driven agent workflows need context packages that bind requirements, architecture, role responsibilities, and implementation story state into a handoff artifact. Data-agent and analytics workflows need governed semantics, source truth, and execution monitoring so retrieved business data does not become unsupported model guesswork.

The [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json) adds governed sensitive-code request constraints. A request package for sensitive-code work should include approved runtime, network posture, credential boundary, audit expectation, and human approval checkpoints instead of relying only on ordinary task context.

## Practice Boundaries

- Start from the task, then select the smallest source set that can support the decision.
- Prefer exact files, nearby call sites, failing assertions, logs, and recent diffs over broad repository dumps.
- Keep stable rules in durable instructions and load them by reference when the harness supports it.
- Trim stale conversation history and long logs so current evidence remains visible.
- Attach verification evidence to the next request when it changes the next action.
- Treat context selection as part of workflow design, not as a late prompt-writing detail.
- For long-running or multi-agent workflows, make the request package machine-readable enough that another agent or reviewer can continue from the same source authorities and current decision state.
- Use story-level context packages when planning, architecture, and implementation are split across agent roles or sessions.
- Include governed semantic definitions and source-truth labels when agents retrieve business metrics or analytics context.
- Include runtime, network, credential, audit, and approval constraints when the request asks an agent to work on sensitive code.
- Label setup commands, repository metadata, and tool context as evidence unless the task authority explicitly permits acting on them.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Hypervelocity engineer source](../../../raw/processed/Hypervelocity engineer @edandersen.md)
- [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md)
- [request packages and file boundaries](request-packages-and-file-boundaries.md)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [prompt-and-instructions](index.md)
- [retrieval-and-tools](../retrieval-and-tools/index.md)
- [verification-and-evals](../verification-and-evals/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold the request-package side of context engineering.
- Maintained on 2026-06-25 with issue, RFC, instruction, reference, API, verification, and handoff evidence for default coding-agent use.
- Maintained on 2026-07-04 with story-file handoffs and governed semantic context for data-agent workflows.
- Maintained on 2026-07-08 with sensitive-code runtime, network, credential, audit, approval, and setup-command request constraints.
