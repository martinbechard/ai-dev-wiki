---
type: "Application Pattern"
title: "Application Harness Patterns"
description: "The harness around the model is where an AI application becomes reliable product software."
tags: ["application-patterns"]
---

# Application Harness Patterns

## Current Understanding

The harness around the model is where an AI application becomes reliable product software. The harness coordinates user interface, server orchestration, model calls, context assembly, tools, workflow state, validation, progress display, and product output.

The detailed harness patterns live in sibling leaves. [Agent harness components](agent-harness-components.md) covers the loop, registry, persistence, hooks, and permission layer; [structured output and drafter patterns](structured-output-and-drafter-patterns.md) cover executable artifacts; [AI process layer and workflow state](ai-process-layer-and-workflow-state.md) covers orchestration and state; [user-visible progress and runtime telemetry](user-visible-progress-and-runtime-telemetry.md) covers progress and health signals; and [local model runtime harness](local-model-runtime-harness.md) covers local operation.

Named frameworks, SDKs, models, and products are upstream-owned entities. This page owns the local architecture pattern and points to local leaves for workflow-specific practice.

Use-compose-build selection is represented in [use compose build workflow selection](../agent-workflows/use-compose-build-workflow-selection.md) because the choice is made per workflow. This page keeps the application architecture boundary: the harness must expose enough control, validation, and telemetry for the selected workflow to be safe to run.

The [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json) adds implementation evidence for keeping harness concerns explicit: a product harness may need separate treatment for working state, execution substrate, protocols, evaluation, observability, guardrails, visible progress, and PR review evidence. Those concerns route to the leaves below instead of turning this overview into a framework catalog.

The [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) adds production runtime evidence. Harness design should model an agent runtime as a service with invocation contracts, session isolation, explicit state buckets, telemetry traces, retries, and human waits. Product and framework details remain upstream-owned; locally, these are harness obligations that make agent workflows operable after prototype stage.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) and [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json) add production-monitoring and harness-taxonomy signals. A product harness should separate model-output observability from application-runtime observability, preserve traces that distinguish retrieval, prompt, model, tool, and application failures, and treat reusable harness primitives as design surfaces for context delivery, tool interfaces, planning artifacts, verification loops, memory systems, permissions, sandboxes, and telemetry.

The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) adds [file-oriented enterprise builder workflows](file-oriented-enterprise-builder-workflows.md). This overview keeps the harness boundary: enterprise builder artifacts need source, validation, review, and publish evidence when AI agents can modify them.

The [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) adds persistent workspace evidence. Durable filesystem state paired with sandboxed command execution is a harness component, not only chat memory, when agents retain generated reports, working documents, and iterated code across runs.

## Pattern Leaves

- [structured-output-and-drafter-patterns.md](structured-output-and-drafter-patterns.md) owns model-drafted schemas, DSLs, validation, execution, retries, and audit.
- [agent-harness-components.md](agent-harness-components.md) owns the fixed runtime pieces of an agent harness.
- [ai-process-layer-and-workflow-state.md](ai-process-layer-and-workflow-state.md) owns workflow orchestration between interface and backend systems.
- [user-visible-progress-and-runtime-telemetry.md](user-visible-progress-and-runtime-telemetry.md) owns user-facing progress and operational visibility.
- [local-model-runtime-harness.md](local-model-runtime-harness.md) owns local inference operation as product harness design.

## Practice Boundaries

- Put harness control between the user interface, model calls, tools, and backend systems.
- Route detailed practice questions to the smallest local leaf that owns the pattern.
- Keep ecosystem facts in the upstream AI wiki unless the local page is describing a downstream practice lens.
- Treat harness design as a workflow tradeoff between control, latency, flexibility, validation cost, and operating burden.
- Keep custom runtime and model choices tied to workflow differentiation, validation evidence, and operating cost.
- Treat agent runtimes as deployed services with invocation contracts, session isolation, explicit state buckets, telemetry traces, retries, and human waits.
- Separate model-output quality monitoring from application-runtime monitoring so repair loops can distinguish retrieval, prompt, model, tool, and code-path defects.
- Treat harness primitives such as context delivery, permissions, memory, tool interfaces, planning artifacts, verification loops, sandboxes, and telemetry as explicit design surfaces.
- Route source-controlled low-code or enterprise builder artifacts through [file-oriented enterprise builder workflows](file-oriented-enterprise-builder-workflows.md).
- Pair [persistent agent workspaces](../agent-workflows/persistent-agent-workspaces.md) with sandbox execution and provenance when files survive across conversations, deploys, or restarts.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [Agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md)
- [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json)
- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [federation.md](../federation.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [retrieval and tools practice](../retrieval-and-tools/rag-tools-and-mcp-practice.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [use compose build workflow selection](../agent-workflows/use-compose-build-workflow-selection.md)
- [file-oriented enterprise builder workflows](file-oriented-enterprise-builder-workflows.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on structured output, drafter patterns, harness software, workflow state, progress, and AI process layers.
- Updated on 2026-06-23 with local-model harness telemetry, calibration, and workflow-level use-compose-build tradeoffs.
- Maintained on 2026-06-23 as the overview page for split application harness leaves.
- Maintained on 2026-06-24 with harness category and progress-telemetry signals from the [leaf update watch](../source-workflows/leaf-update-watch.md).
- Maintained on 2026-07-07 with production runtime, invocation-contract, session-isolation, state-bucket, and telemetry-trace obligations.
- Maintained on 2026-07-11 with model-output versus runtime observability and reusable harness primitive taxonomy.
- Maintained on 2026-07-27 with source-controlled enterprise-builder artifacts and persistent-workspace harness boundaries.
