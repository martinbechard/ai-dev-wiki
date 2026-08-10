# Application Patterns

## Current Understanding

Application patterns covers the harness around AI models: structured output, workflow state, tool execution, progress streaming, process layers, agents, validators, and product controls. The local focus is design practice for AI-enabled applications and AI-assisted development tools.

This topic does not duplicate framework catalogs. It records reusable architecture patterns and links upstream when a named framework, SDK, model, or product is needed for background.

## Pattern Leaf Pages

- [application-harness-patterns.md](application-harness-patterns.md) is the overview for harness design boundaries.
- [agent-environment-readiness.md](agent-environment-readiness.md) records setup, isolation, secret scoping, restart, and persistence criteria for coding-agent environments.
- [harness-sizing-by-workflow-complexity.md](harness-sizing-by-workflow-complexity.md) records how harness controls scale with action risk and context complexity.
- [file-oriented-enterprise-builder-workflows.md](file-oriented-enterprise-builder-workflows.md) records source-controlled artifacts, local validation, Git review, and publish workflows for enterprise builders.
- [structured-output-and-drafter-patterns.md](structured-output-and-drafter-patterns.md) records schema, DSL, validation, execution, and audit boundaries for model-drafted artifacts.
- [agent-harness-components.md](agent-harness-components.md) records the fixed loop, registry, context, persistence, hooks, and permission components of a coding-agent harness.
- [agent-session-recovery.md](agent-session-recovery.md) records startup continuity checks, progress cursors, durable artifacts, and resumability evidence.
- [agent-lifecycle-hooks.md](agent-lifecycle-hooks.md) records hook points for session starts, tool-surface changes, approvals, memory updates, verification, failures, and completion.
- [ai-process-layer-and-workflow-state.md](ai-process-layer-and-workflow-state.md) records the process layer between user interface and backend systems, including workflow state and validation loops.
- [declarative-agent-workflow-artifacts.md](declarative-agent-workflow-artifacts.md) records reviewable orchestration artifacts for branching, approvals, checkpoints, and resume behavior.
- [user-visible-progress-and-runtime-telemetry.md](user-visible-progress-and-runtime-telemetry.md) records progress events, streaming signals, operational metrics, and visible runtime health.
- [local-model-runtime-harness.md](local-model-runtime-harness.md) records local model operation as a harness concern, including calibration, memory hierarchy, session state, and workflow-specific telemetry.
- [browser-agent-runtime-boundaries.md](browser-agent-runtime-boundaries.md) records browser sessions, search/fetch APIs, identity, proxies, and browser observations as governed agent runtime surfaces.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [Agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md)
- [Browserbase use-cases clipping](../../../raw/processed/Browserbase Use Cases Web Scraping & AI Agent Examples.md)
- [Leaf Update Watch](../source-workflows/leaf-update-watch.md) source: [raw artifact](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json)
- [federation.md](../federation.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [retrieval-and-tools](../retrieval-and-tools/index.md)
- [verification-and-evals](../verification-and-evals/index.md)
- [governance-and-risk](../governance-and-risk/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 as the local owner for AI application and harness patterns.
- Maintained on 2026-06-23 by splitting reusable harness concepts into durable leaf pages.
- Maintained on 2026-06-24 with harness taxonomy, TTFT, and visible progress signals from the leaf update watch.
- Maintained on 2026-07-27 with file-oriented enterprise builder workflows as a durable leaf.
- Maintained on 2026-07-28 with declarative workflow artifacts and harness sizing as durable leaves.
- Maintained on 2026-07-30 with agent environment readiness as a durable leaf.
- Maintained on 2026-07-30 with separate session recovery and lifecycle hooks durable leaves.
- Maintained on 2026-08-09 with browser-agent runtime boundaries as a durable leaf.
