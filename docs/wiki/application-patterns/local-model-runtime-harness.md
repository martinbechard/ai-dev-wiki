# Local Model Runtime Harness

## Current Understanding

Local model operation is a harness design question, not only a model-selection question. The harness must decide how local inference affects latency, memory, privacy, tool-call reliability, session continuity, validation, and visible runtime health.

The Dwarf Star source illustrates local runtime concerns that matter for application design: selective quantization, SSD-backed expert caching, resumable session state, distributed prefill tradeoffs, and real-time runtime metrics. [Representative workflow calibration](../verification-and-evals/representative-workflow-calibration.md) owns calibration prompts, drift checks, and workflow-specific eval coverage. This page owns the application harness lens: how local operation affects product latency, memory, privacy, tool-call reliability, session continuity, validation, and visible runtime health.

## Practice Boundaries

- Treat local inference as a product harness choice with operational costs, validation needs, and user-visible behavior.
- Link calibration and drift-check decisions to [representative workflow calibration](../verification-and-evals/representative-workflow-calibration.md).
- Expose telemetry for latency, memory, cache behavior, token throughput, accelerator use, and session state when those values affect workflow trust.
- Preserve resumable state when long sessions would otherwise require expensive reprocessing.
- Treat RAM, SSD, and distributed prefill as latency and capacity tradeoffs rather than as pure capability claims.
- Re-check tool-call reliability and long-context behavior whenever runtime, model, or quantization choices change.

## Authoritative Sources

- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Representative workflow calibration](../verification-and-evals/representative-workflow-calibration.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Application harness patterns](application-harness-patterns.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [user-visible progress and runtime telemetry](user-visible-progress-and-runtime-telemetry.md)
- [representative workflow calibration](../verification-and-evals/representative-workflow-calibration.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [federation.md](../federation.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from the local model operations source and local verification guidance for representative calibration.
- Upstream durable leaves for Dwarf Star, DeepSeek V4, selective quantization, SSD expert caching, and distributed prefill are Not yet identified; this page treats them as source-specific runtime examples, not local entity or technique coverage.
