---
type: "Topic"
title: "Persistent Agent Workspaces"
description: "Persistent agent workspaces preserve enough state for coding-agent work that spans multiple prompts, sessions, or branches."
tags: ["agent-workflows"]
---

# Persistent Agent Workspaces

## Current Understanding

Persistent agent workspaces preserve enough state for coding-agent work that spans multiple prompts, sessions, or branches. The local pattern is to keep goals, plan state, active files, verification evidence, unresolved blockers, and handoff notes in durable project surfaces instead of relying on a single chat transcript.

The [Codex-maxxing source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) frames long-running Codex work around preserved context, verifiable steps, continuity across workstreams, and human oversight boundaries. Broad Codex product coverage belongs to the upstream AI wiki; this page owns the local workflow practice for any persistent coding-agent workspace.

Persistent workspaces do not remove the need for fresh orientation. Each resumed pass should re-check the repository state, current instructions, active goals, and verification evidence before editing. The workspace is useful because it makes continuity inspectable, not because it lets an agent assume earlier context is still correct.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) adds worktree practice evidence. Desktop-level worktree support and assisted conflict handling make isolated parallel workspaces easier to create, but the local rule remains that each workspace needs clear branch intent, changed-file accounting, and merge evidence before handoff.

The [July 2 topic news collector source](../../../raw/processed/2026-07-02/ai-dev-wiki-topic-news-collector-2026-07-02T203134-0400.json) adds background-agent handoff signals. Persistent workspaces need completion, input-needed, draft-PR, inherited-configuration, and subagent-state cues so background coding sessions can be recovered and reviewed without guessing from a chat transcript.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) adds a coordinator-worker signal. Recurring or parallel coding-agent work benefits from stable coordinator state, queues, callbacks, locks, session history, and handoff messages, while worker sessions should still start fresh with scoped instructions and current repository evidence.

The [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json) and [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json) add worktree-orchestration and resumable-run evidence. Parallel coding-agent platforms should keep branch, worktree, terminal, PR, CI, review, and preview state separated, while long-running scanners and evaluators should preserve analyzed-file state and skip completed work after interruption. The local rule is to make persistence observable enough that a human can recover the workspace without trusting a transcript summary.

The [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) adds merge-concurrency evidence from agent-authored pull requests. Persistent workspaces need coordination rules for temporal overlap, cross-agent branch ownership, PR scheduling, merge ownership, and intent-level conflict review because exact textual conflict checks do not capture all ways concurrent agents can collide.

## Practice Boundaries

- Store goal state, active plan, source links, changed files, verification commands, and unresolved questions where the next human or agent can inspect them.
- Split long-running work into verifiable steps with explicit acceptance evidence before moving to the next step.
- Re-orient from the live repository and current instructions at each resume point.
- Keep human-owned tradeoffs, approvals, and external side effects visible in the workspace state.
- Use handoff notes when a persistent workspace pauses, branches, or transfers to another agent.
- Archive or reset stale workspace state when it no longer reflects the live repository or accepted plan.
- Use worktrees for parallel human and agent work only when branch purpose, ownership, and merge evidence are visible.
- Record background-agent completion state, input-needed state, draft PR links, inherited reasoning or configuration settings, and subagent state when a workspace continues without direct supervision.
- Use coordinator state for queues, callbacks, locks, session history, and cross-project handoffs when many coding-agent sessions run in parallel.
- Keep worker sessions scoped and freshly oriented even when a coordinator preserves long-lived operational state.
- Separate branch, worktree, terminal, PR, CI, review, and preview state when multiple agents operate on the same project.
- Preserve resumable-run state for expensive scans and evals so recovery can skip completed work without losing audit evidence.
- Treat concurrent agent PRs as a managed queue with branch ownership, overlap visibility, merge sequencing, and intent-level conflict review.

## Authoritative Sources

- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md)
- [delegated coding handoffs](delegated-coding-handoffs.md)
- [AI process layer and workflow state](../application-patterns/ai-process-layer-and-workflow-state.md)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [July 2 topic news collector source](../../../raw/processed/2026-07-02/ai-dev-wiki-topic-news-collector-2026-07-02T203134-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json)
- [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)

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
- Maintained on 2026-06-26 with worktree isolation and assisted-conflict workflow implications for persistent agent workspaces.
- Maintained on 2026-07-02 with background-agent notification, draft-PR handoff, inherited-configuration, and subagent-state signals.
- Maintained on 2026-07-04 with coordinator-worker queues, callbacks, locks, session history, and handoff state.
- Maintained on 2026-07-06 with worktree-orchestration and resumable scan or eval workspace evidence.
- Maintained on 2026-07-07 with concurrent agent PR overlap, merge sequencing, and intent-level conflict review guidance.
