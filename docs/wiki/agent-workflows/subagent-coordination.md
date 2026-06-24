# Subagent Coordination

## Current Understanding

Subagent coordination delegates independent investigations to separate agent contexts while the main agent keeps ownership of the plan, decisions, integration, and final verification. Subagents are useful when detailed investigation can stay separate until the evidence returns.

The [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md) describes subagents as specialized agents with their own context. The [gen AI application deck](../../../raw/processed/gen-ai-app-complete.md) describes user-facing agents and internal specialist agents such as planners, retrievers, workers, verifiers, writers, analysts, or tool specialists coordinated by software.

The local rule is that delegation does not transfer accountability. The main agent integrates returned evidence, checks conflicts, keeps unrelated changes out of scope, and verifies the combined result.

The [leaf update watch source](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json) captures public loop-design practice where heartbeat, cron, hook, and goal loops can coordinate subagents. The local implication is that recurring subagent loops need explicit state, stop conditions, evidence contracts, cost boundaries, and an independent validation role when one agent writes while another checks.

## Practice Boundaries

- Use subagents for independent investigations with clear scope and evidence expectations.
- Keep the main agent responsible for synthesis, edit ownership, and final verification.
- Ask subagents to return evidence, findings, and risks rather than hidden intermediate context.
- Avoid overlapping file edits unless a coordinator explicitly assigns ownership and integration.
- Give recurring subagent loops a durable state record, retry or stop rule, budget boundary, and validation expectation.
- Use a separate verifier when a subagent performs broad generation, security-sensitive analysis, or recurring unattended work.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md)
- [Leaf update watch source](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent workflows](index.md)
- [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md)
- [delegated coding handoffs](delegated-coding-handoffs.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [agent cost telemetry](../adoption-and-operating-model/agent-cost-telemetry.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed subagent, specialist-agent, and integration guidance.
- Maintained on 2026-06-23 with public loop-design guidance on recurring subagent loops, independent validation, and stop conditions.
