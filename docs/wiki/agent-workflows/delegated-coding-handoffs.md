# Delegated Coding Handoffs

## Current Understanding

Delegated coding handoffs define how an agent returns work to the human or coordinator for review. The handoff needs to state what changed, which evidence supports completion, what could not be verified, and which decisions still require human acceptance.

The [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md) treats delegated coding as an execution-control workflow: the agent reads, edits, runs code, reports results, and leaves visible planning, tool output, verification evidence, and human-control checkpoints. The [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md) generalizes the same concern into a product process-layer pattern: progress, approvals, traces, costs, tool calls, failures, and validation stay visible while work runs. Together, the sources make delegated coding handoffs both an engineering-control problem and a product-observability problem; the handoff is not complete until the next human or agent can see what changed, why it is acceptable, and which controls remain active.

This page owns the handoff pattern. [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md) owns the operating rule for what the human must approve.

## Practice Boundaries

- Report changed files, verification commands, relevant outputs, and unresolved evidence gaps.
- Distinguish verified completion from blocked or unverified claims.
- Carry human-owned decisions into the handoff instead of silently resolving them.
- Keep handoff summaries tied to source evidence, tests, lint, build output, runtime checks, or review findings.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md)
- [subagent coordination](subagent-coordination.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed delegated coding, visible progress, and evidence-handoff guidance.
