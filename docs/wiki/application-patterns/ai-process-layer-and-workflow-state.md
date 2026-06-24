# AI Process Layer And Workflow State

## Current Understanding

The AI process layer is the application tier between user intent and backend systems. It chooses prompts, models, retrieval steps, tools, verifiers, and human gates while preserving workflow state that the model itself does not remember.

Workflow state includes conversation history, selected files, retrieved context, tool results, forks, checkpoints, approvals, failures, and compaction summaries. The process layer controls which state becomes model context, which state remains application state, and which state must be visible to users or auditors.

## Practice Boundaries

- Put an AI process layer between the interface and backend when the workflow needs tools, state, validation, or approvals.
- Treat the model as stateless across requests unless the harness resends or summarizes the required state.
- Store workflow state in deterministic application structures rather than only in conversation text.
- Use different context, tools, models, and validation checks for different workflow steps when that improves cost, latency, or accuracy.
- Preserve checkpoints and failure evidence when a long-running workflow needs review, retry, or handoff.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Application harness patterns](application-harness-patterns.md)
- [Orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)

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
