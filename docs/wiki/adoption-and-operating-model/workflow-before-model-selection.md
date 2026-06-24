# Workflow Before Model Selection

## Current Understanding

Workflow before model selection means the team chooses the work shape before standardizing on a model, coding assistant, or harness. The useful first questions are autonomy level, context sources, allowed tools, approval points, verification expectations, and evidence required for completion.

The [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md) and [gen AI application deck](../../../raw/processed/gen-ai-app-complete.md) separate models, harnesses, and workflows. A model supplies capability, a harness decides how that capability reaches files and tools, and a workflow decides how the work is oriented, planned, edited, tested, reviewed, and handed back.

This operating rule keeps model choice from becoming a shortcut around process design. Model routing, product selection, and build-versus-buy decisions remain downstream of the workflow requirement.

The [leaf update watch source](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json) reinforces this rule from public coding-agent comparisons and loop-design sources: there is no single best agent outside the work shape, governance requirement, review burden, cost profile, and delivery goal. Leaderboards and product lists are upstream ecosystem material; the local decision is whether a workflow needs automation loops, worktrees, subagents, connectors, review gates, or a smaller human-led assist pattern.

## Practice Boundaries

- Choose the workflow shape before choosing the model or assistant product.
- Define the level of autonomy and the human review points before delegation begins.
- Use model choice as a harness design decision when the workflow requires different cost, latency, context, or verification behavior.
- Link per-workflow use, compose, or build decisions to [use-compose-build-workflow-selection.md](../agent-workflows/use-compose-build-workflow-selection.md).
- Compare agents by workflow fit, governance fit, review burden, context requirements, and measurable delivery impact before product preference.
- Treat recurring loops as a workflow design choice with state, budget, and validation requirements.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [Leaf update watch source](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption operating agreements](adoption-operating-agreements.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [use compose build workflow selection](../agent-workflows/use-compose-build-workflow-selection.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [agent cost telemetry](agent-cost-telemetry.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed workflow, harness, and model-selection guidance.
- Maintained on 2026-06-23 with public coding-agent selection guidance focused on workflow fit, governance burden, and loop design.
