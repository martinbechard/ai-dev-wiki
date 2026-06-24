# Agent Cost Telemetry

## Current Understanding

Agent cost telemetry tracks model and tool consumption at the workflow level so teams can decide whether an agent loop is useful, wasteful, or mis-scoped. The local pattern is to measure cost by run, step, model, tool loop, subagent fan-out, context growth, and outcome instead of treating a monthly spend cap as the only control.

The [tokenomics source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) argues that coding-agent spend should be traced by session, step, model, and outcome, and that more token use does not automatically mean better engineering results. Broad vendor, product, and company coverage belongs upstream; this page owns the local operating-model implication.

Cost telemetry is not only finance reporting. It is feedback for workflow design: a loop that repeatedly expands context, calls tools without new evidence, or fans out subagents without acceptance criteria should be redesigned before it becomes a standing automation.

## Practice Boundaries

- Track model, token, tool, runtime, and subagent costs by workflow run and step when the work is recurring or expensive.
- Pair cost records with outcome evidence such as accepted patch, failed verification, useful research, rejected draft, or blocked handoff.
- Bound subagent fan-out, retry loops, and long context growth with explicit budget or stop rules.
- Compare cost against workflow value and review burden, not against model capability claims alone.
- Treat high spend without better acceptance evidence as a workflow smell.
- Feed cost findings back into workflow-before-model-selection decisions.

## Authoritative Sources

- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [workflow before model selection](workflow-before-model-selection.md)
- [subagent coordination](../agent-workflows/subagent-coordination.md)
- [user-visible progress and runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [AI process layer and workflow state](../application-patterns/ai-process-layer-and-workflow-state.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from public source guidance on coding-agent token economics, step-level cost tracing, subagent fan-out, and outcome-linked telemetry.
