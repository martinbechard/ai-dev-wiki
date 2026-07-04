---
type: "Application Pattern"
title: "User-Visible Progress And Runtime Telemetry"
description: "Long-running AI workflows need visible progress so users can understand what the system is doing, where it is waiting, and which checks still matter."
tags: ["application-patterns"]
---

# User-Visible Progress And Runtime Telemetry

## Current Understanding

Long-running AI workflows need visible progress so users can understand what the system is doing, where it is waiting, and which checks still matter. Token streaming can show generation, but useful progress also includes retrieved files, tool activity, approval waits, unresolved items, generated drafts, and runtime health.

Progress events are product signals, not proof of hidden reasoning. The harness should expose enough state for the user to judge whether the workflow is alive, blocked, waiting for approval, or ready for acceptance. Local and long-running model workflows also need operational telemetry such as latency, memory pressure, cache behavior, GPU or accelerator use, token counts, and quality drift signals.

The [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json) adds a latency boundary for user-facing agents: time to first token should be separated from total pipeline latency, and tool-call pauses should produce explicit progress states. A streaming model response is not enough when retrieval, tool use, pre-inference work, or approval waits can create silence before or between tokens.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) adds remote-startup and permission-telemetry signals. Remote agent provisioning should expose checklist progress, background-agent visibility, restart state, permission denials, telemetry controls, authentication notices, and resource cleanup when those states affect trust or user acceptance.

The [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) adds semantic-failure telemetry. A workflow can look healthy at the infrastructure layer while the agent is looping, using irrelevant evidence, or failing the task objective. Runtime telemetry should therefore include traces, tool-loop summaries, evaluation outcomes, retry reasons, and failure-attribution fields in addition to latency and resource metrics.

The [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md) adds context-layer telemetry. When a harness compresses or routes context, users and operators need visible signals for token savings, cache hits, retrieval fallbacks, compressor choice, provenance, latency, and drift checks so optimization remains inspectable.

The [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json) adds security and behavior telemetry. Agent observability should include tool calls, reasoning-loop state, state transitions, quality checks, verification results, and security posture signals so operators can distinguish healthy execution from unsafe, looping, or task-wrong behavior.

## Practice Boundaries

- Stream progress when users need visible state during multi-step work.
- Separate user-visible progress from unsupported claims about hidden reasoning.
- Show tool activity, approval waits, generated artifacts, unresolved issues, and verification status when they affect user acceptance.
- Surface runtime metrics when latency, memory, cache behavior, or model operation can change the user experience.
- Keep progress and telemetry aligned with actual workflow state instead of smoothing over failures or blocked steps.
- Track time to first token separately from total workflow latency when user perception matters.
- Show visible states for retrieval, pre-inference work, tool-call pauses, approval waits, retries, and verification.
- Surface remote provisioning, background-agent state, denial reasons, authentication notices, telemetry settings, and resource cleanup when they affect user trust.
- Record semantic failure signals, trace summaries, retry reasons, tool-loop patterns, and evaluation outcomes when agent behavior can appear operationally healthy but task-wrong.
- Expose context-optimization telemetry when compression, cache alignment, or retrieval fallback can change latency, cost, or task accuracy.
- Include behavior, verification, and security signals in operator telemetry when agents can call tools, cross trust boundaries, or continue across sessions.
- Track tool-call traces, state transitions, and quality metrics together so semantic failures are not hidden behind infrastructure health.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json)
- [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md)
- [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json)
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
- [trajectory-level agent evaluation](../verification-and-evals/trajectory-level-agent-evaluation.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on progress events, agent UI updates, and runtime metrics for local or long-running AI workflows.
- Maintained on 2026-06-24 with TTFT, pipeline latency, and tool-call pause state guidance.
- Maintained on 2026-06-26 with remote provisioning, background-agent visibility, permission-denial, authentication, telemetry, and cleanup states.
- Maintained on 2026-06-28 with semantic-failure telemetry, trace summaries, and evaluation outcomes.
- Maintained on 2026-06-30 with context-optimization telemetry for compression, cache hits, retrieval fallbacks, provenance, latency, and drift checks.
- Maintained on 2026-07-03 with behavior, verification, state-transition, and security-posture telemetry for agentic workflows.
