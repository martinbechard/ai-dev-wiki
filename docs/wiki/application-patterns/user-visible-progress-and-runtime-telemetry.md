# User-Visible Progress And Runtime Telemetry

## Current Understanding

Long-running AI workflows need visible progress so users can understand what the system is doing, where it is waiting, and which checks still matter. Token streaming can show generation, but useful progress also includes retrieved files, tool activity, approval waits, unresolved items, generated drafts, and runtime health.

Progress events are product signals, not proof of hidden reasoning. The harness should expose enough state for the user to judge whether the workflow is alive, blocked, waiting for approval, or ready for acceptance. Local and long-running model workflows also need operational telemetry such as latency, memory pressure, cache behavior, GPU or accelerator use, token counts, and quality drift signals.

## Practice Boundaries

- Stream progress when users need visible state during multi-step work.
- Separate user-visible progress from unsupported claims about hidden reasoning.
- Show tool activity, approval waits, generated artifacts, unresolved issues, and verification status when they affect user acceptance.
- Surface runtime metrics when latency, memory, cache behavior, or model operation can change the user experience.
- Keep progress and telemetry aligned with actual workflow state instead of smoothing over failures or blocked steps.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [Application harness patterns](application-harness-patterns.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [ai process layer and workflow state](ai-process-layer-and-workflow-state.md)
- [local model runtime harness](local-model-runtime-harness.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on progress events, agent UI updates, and runtime metrics for local or long-running AI workflows.
