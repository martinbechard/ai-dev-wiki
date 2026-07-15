---
type: "Topic"
title: "Use Compose Build Workflow Selection"
description: "Use, compose, or build is a per-workflow selection rule for agentic AI work."
tags: ["agent-workflows"]
---

# Use Compose Build Workflow Selection

## Current Understanding

Use, compose, or build is a per-workflow selection rule for agentic AI work. A managed tool can be the right answer when differentiation is low, a composed harness can be the right answer when repository context and workflow control matter, and custom model or agent infrastructure should be reserved for work that truly differentiates the project.

The [agentic team-structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md) frames the decision around economics, differentiation, leverage, control, and speed. It warns against declaring a universal AI strategy before understanding the workflow. The [gen AI application deck](../../../raw/processed/gen-ai-app-complete.md) expresses the same product lens: harnesses coordinate workflow, state, tools, approvals, validation, and observability around the model.

The [Pi coding agent source](../../../raw/processed/Why I Quit Claude Code for Pi.md) adds a harness-control version of the same selection rule. Teams may use a managed coding agent when the default workflow is sufficient, compose around an extensible harness when they need custom planning, telemetry, subagents, MCP adapters, or model routing, and build deeper infrastructure only when those controls differentiate the work enough to justify maintenance. The source also reinforces that model choice and token economics are workflow decisions, not brand decisions.

The [Affordable AI Agents source](../../../raw/processed/The Affordable AI Agents.md) adds an infrastructure-cost version of the same rule. Managed APIs, enterprise subscriptions, self-hosted clusters, and local execution should be selected per workflow, not as a universal platform stance. Building or hosting deeper infrastructure needs predictable utilization, staffing, routing, observability, and governance evidence; otherwise the fixed baseline can erase apparent token savings.

This page owns the workflow-selection rule. [workflow before model selection](../adoption-and-operating-model/workflow-before-model-selection.md) owns the adoption rule that the workflow shape comes before model or tool choice.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) and [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) reinforce that shared governance, observability, model routing, reusable agent patterns, programmatic tool orchestration, and domain-owned MCP servers are compose-or-build considerations. The decision is not whether a model can call a tool; it is whether the workflow needs local control over identity, context, verification, audit, cost, and service boundaries.

## Practice Boundaries

- Decide use, compose, or build per workflow rather than per organization slogan.
- Prefer managed tools when leverage is high and local differentiation is low.
- Compose when repository context, workflow control, state, approvals, and audit create meaningful differentiation.
- Build custom model or agent infrastructure only when the workflow is truly differentiating and the organization can staff and govern it.
- Consider extensible harnesses when the team needs direct control over planning, session telemetry, model routing, or agent plugins.
- Keep token cost, context visibility, and subsidized vendor pricing in the workflow economics review.
- Treat self-hosted and local execution as build choices that need utilization, staffing, latency, telemetry, and governance justification.
- Choose compose or build when the workflow needs local control over identity, context routing, verification, audit, cost attribution, programmatic tool execution, or domain-owned service boundaries.

## Authoritative Sources

- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Pi coding agent source](../../../raw/processed/Why I Quit Claude Code for Pi.md)
- [Affordable AI Agents source](../../../raw/processed/The Affordable AI Agents.md)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent workflows](index.md)
- [workflow before model selection](../adoption-and-operating-model/workflow-before-model-selection.md)
- [senior led agentic execution pods](../adoption-and-operating-model/senior-led-agentic-execution-pods.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [hybrid agent infrastructure economics](../adoption-and-operating-model/hybrid-agent-infrastructure-economics.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed use, compose, and build workflow-selection guidance.
- Maintained on 2026-06-27 with hosting and local-execution choices as per-workflow build decisions.
- Maintained on 2026-07-14 with shared governance, observability, model routing, reusable agent patterns, programmatic tools, and domain-owned MCP service boundaries as compose-or-build inputs.
