# Persistent Agent Workspaces

## Current Understanding

Persistent agent workspaces preserve enough state for coding-agent work that spans multiple prompts, sessions, or branches. The local pattern is to keep goals, plan state, active files, verification evidence, unresolved blockers, and handoff notes in durable project surfaces instead of relying on a single chat transcript.

The [Codex-maxxing source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) frames long-running Codex work around preserved context, verifiable steps, continuity across workstreams, and human oversight boundaries. Broad Codex product coverage belongs to the upstream AI wiki; this page owns the local workflow practice for any persistent coding-agent workspace.

Persistent workspaces do not remove the need for fresh orientation. Each resumed pass should re-check the repository state, current instructions, active goals, and verification evidence before editing. The workspace is useful because it makes continuity inspectable, not because it lets an agent assume earlier context is still correct.

## Practice Boundaries

- Store goal state, active plan, source links, changed files, verification commands, and unresolved questions where the next human or agent can inspect them.
- Split long-running work into verifiable steps with explicit acceptance evidence before moving to the next step.
- Re-orient from the live repository and current instructions at each resume point.
- Keep human-owned tradeoffs, approvals, and external side effects visible in the workspace state.
- Use handoff notes when a persistent workspace pauses, branches, or transfers to another agent.
- Archive or reset stale workspace state when it no longer reflects the live repository or accepted plan.

## Authoritative Sources

- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md)
- [delegated coding handoffs](delegated-coding-handoffs.md)
- [AI process layer and workflow state](../application-patterns/ai-process-layer-and-workflow-state.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [context selection and compaction](../context-architecture/context-selection-and-compaction.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from public source guidance on long-running agent workspaces, continuity, step verification, and oversight checkpoints.
