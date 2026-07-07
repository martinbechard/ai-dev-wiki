---
type: "Application Pattern"
title: "AI Process Layer And Workflow State"
description: "The AI process layer is the application tier between user intent and backend systems."
tags: ["application-patterns"]
---

# AI Process Layer And Workflow State

## Current Understanding

The AI process layer is the application tier between user intent and backend systems. It chooses prompts, models, retrieval steps, tools, verifiers, and human gates while preserving workflow state that the model itself does not remember.

Workflow state includes conversation history, selected files, retrieved context, tool results, forks, checkpoints, approvals, failures, and compaction summaries. The process layer controls which state becomes model context, which state remains application state, and which state must be visible to users or auditors.

The [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json) adds operational-readiness and workflow-memory signals. Agentic applications need observable operational systems, trusted data connections, permission controls, approval checkpoints, citations, logging, state memory, and handoff paths before they can safely automate work. The process layer owns those state transitions even when the model, framework, or product supplies the language capability.

The [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md) adds a collaboration-channel process-layer pattern. Chat bots and agents need event intake, thread subscription state, platform adapters, response rendering, and durable workflow state around the model call. When agent responses stream into Slack, Teams, Discord, or similar surfaces, the process layer should preserve requester identity, thread context, generated artifacts, tool evidence, and follow-up state separately from the model transcript.

## Practice Boundaries

- Put an AI process layer between the interface and backend when the workflow needs tools, state, validation, or approvals.
- Treat the model as stateless across requests unless the harness resends or summarizes the required state.
- Store workflow state in deterministic application structures rather than only in conversation text.
- Use different context, tools, models, and validation checks for different workflow steps when that improves cost, latency, or accuracy.
- Preserve checkpoints and failure evidence when a long-running workflow needs review, retry, or handoff.
- Treat operational telemetry, approval checkpoints, citations, logs, state memory, and handoff records as process-layer state, not only UI or model context.
- Require healthy, observable upstream systems before letting an agent workflow automate across hybrid tools or business processes.
- Store collaboration-channel event, thread, adapter, requester, tool-evidence, and follow-up state outside the model transcript.
- Treat rich chat cards, streamed responses, and channel posts as workflow outputs that need the same provenance and approval handling as other agent artifacts.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Application harness patterns](application-harness-patterns.md)
- [Orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json)
- [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [structured output and drafter patterns](structured-output-and-drafter-patterns.md)
- [user-visible progress and runtime telemetry](user-visible-progress-and-runtime-telemetry.md)
- [context selection and compaction](../context-architecture/context-selection-and-compaction.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on AI process layers, workflow state, validation loops, tools, checkpoints, and compaction.
- Maintained on 2026-07-02 with operational-readiness, workflow-memory, citation, logging, approval, and handoff-state requirements.
- Maintained on 2026-07-06 with collaboration-channel event, thread, adapter, streamed-response, and follow-up state requirements.
