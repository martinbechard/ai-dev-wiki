---
type: "Topic"
title: "Delegated Coding Handoffs"
description: "Delegated coding handoffs define how an agent returns work to the human or coordinator for review."
tags: ["agent-workflows"]
---

# Delegated Coding Handoffs

## Current Understanding

Delegated coding handoffs define how an agent returns work to the human or coordinator for review. The handoff needs to state what changed, which evidence supports completion, what could not be verified, and which decisions still require human acceptance.

The [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md) treats delegated coding as an execution-control workflow: the agent reads, edits, runs code, reports results, and leaves visible planning, tool output, verification evidence, and human-control checkpoints. The [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md) generalizes the same concern into a product process-layer pattern: progress, approvals, traces, costs, tool calls, failures, and validation stay visible while work runs. Together, the sources make delegated coding handoffs both an engineering-control problem and a product-observability problem; the handoff is not complete until the next human or agent can see what changed, why it is acceptable, and which controls remain active.

This page owns the handoff pattern. [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md) owns the operating rule for what the human must approve.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) frames delegated agent work as increasingly longer-horizon and cross-functional. The handoff therefore needs to include progress state and remaining oversight, not only a final diff summary. Product-specific Codex and platform history belongs upstream; this page keeps the local acceptance and transition contract for delegated work.

The [context loss source](../../../raw/processed/Your AI Agent Already Forgot Half of What You Told It.md) and [context collapse source](../../../raw/processed/When Context Collapses Teaching Agents to Detect and Recover from Lost Memory.md) make the handoff a context-management artifact as well as a human review artifact. A handoff should let a fresh session rehydrate without chat history: current state, changed files, progress cursor, source artifacts, decisions, verification evidence, unresolved discrepancies, and the next acceptance criterion.

The [June 27 leaf update watch source](../../../raw/processed/2026-06-27/ai-dev-wiki-leaf-update-watch-2026-06-27T210128-0400.json) adds a remote-agent supervision signal: delegated work should name execution context, intervention mode, review loop, and narrow permissions when the work runs in a remote or long-running environment. Broad Codex product details stay upstream.

The [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) adds a mobile and remote-control signal for delegated engineering work. A handoff should say how work was started, steered, reviewed, and organized when the execution surface is outside the primary terminal, and it should leave enough state for the next reviewer to intervene without reconstructing the run from chat history.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) and [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) add accountable-ownership and proof-loop signals. An agent may coordinate planning, implementation, tests, docs, and review, but the handoff should preserve the accountable human owner, approval boundaries, integration ordering for shared schema or platform work, and proof artifacts that let an independent verifier confirm the completion claim.

The [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json) adds issue-tracker and project-filter signals. When tickets, project boards, or issue trackers become the control plane for agentic engineering work, the handoff should carry acceptance criteria, assigned human owner, review-state filter, governance fields, audit evidence, and whether the agent-authored pull request is blocked, review-ready, or merge-ready. Broad Jira, GitHub Projects, and coding-agent product coverage remains upstream-owned.

The [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) adds execution-boundary and agent-manager criteria. Handoffs should state whether work ran locally, in managed worktrees, in a cloud session, through repository-native delegation, or through a browser-agent surface because file access, credential location, supervision, review loop, and reproducible setup differ by boundary.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds [supervised cross-environment handoffs](supervised-cross-environment-handoffs.md) as a focused handoff leaf. When work spans browser, desktop, terminal, repository, or cloud surfaces, the handoff should identify the surface boundary and the evidence that lets the next reviewer inspect progress outside the original UI.

The [CLI multi-agent orchestration research source](../../../raw/processed/project-wiki-research-2026-08-05-cli-multi-agent-orchestration.md) adds issue, pull-request, CI, review-comment, and merge-queue feedback routing as handoff evidence for coding-agent fleets. The fleet-selection practice lives in [terminal-native agent fleet orchestration](terminal-native-agent-fleet-orchestration.md); this page keeps the rule that a handoff must identify which worker owns each feedback item and what evidence makes the result review-ready.

## Practice Boundaries

- Report changed files, verification commands, relevant outputs, and unresolved evidence gaps.
- Distinguish verified completion from blocked or unverified claims.
- Carry human-owned decisions into the handoff instead of silently resolving them.
- Keep handoff summaries tied to source evidence, tests, lint, build output, runtime checks, or review findings.
- Include progress state, tool or environment assumptions, and remaining supervision needs when the delegated task took multiple steps or ran across a longer horizon.
- Include enough state for a fresh session to resume from disk without relying on prior chat memory.
- Record the progress cursor, last completed artifact, source-of-truth files, unresolved discrepancies, and next acceptance criterion when the handoff is part of a multi-step workflow.
- Name execution context, intervention mode, review loop, and narrow permissions for remote or long-running delegated work.
- Include start, steering, review, organization, and intervention evidence when delegated work runs through a remote or mobile control surface.
- Name the accountable owner separately from the coordinating or implementing agent when a task spans planning, tests, docs, or review.
- Include specifications, evidence artifacts, independent verification results, and integration-order notes when the handoff claims delegated work is complete.
- Preserve ticket, board, pull-request review state, human owner, audit fields, and approval status when project-management tools coordinate agentic engineering work.
- Record execution location, file and credential boundary, supervision surface, review loop, and reproducible setup evidence when a task moves between local, worktree, cloud, repository-native, or browser-agent environments.
- Route browser, desktop, terminal, repository, or cloud boundary transitions through [supervised cross-environment handoffs](supervised-cross-environment-handoffs.md).
- Preserve issue, pull-request, CI, review-comment, merge-queue, and worker-owner state when a terminal fleet manager coordinates delegated coding work.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [Context loss source](../../../raw/processed/Your AI Agent Already Forgot Half of What You Told It.md)
- [Context collapse source](../../../raw/processed/When Context Collapses Teaching Agents to Detect and Recover from Lost Memory.md)
- [June 27 leaf update watch source](../../../raw/processed/2026-06-27/ai-dev-wiki-leaf-update-watch-2026-06-27T210128-0400.json)
- [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json)
- [context state externalization and rehydration](../context-architecture/context-state-externalization-and-rehydration.md)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)
- [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [CLI multi-agent orchestration research source](../../../raw/processed/project-wiki-research-2026-08-05-cli-multi-agent-orchestration.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md)
- [subagent coordination](subagent-coordination.md)
- [supervised cross-environment handoffs](supervised-cross-environment-handoffs.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [context state externalization and rehydration](../context-architecture/context-state-externalization-and-rehydration.md)
- [terminal-native agent fleet orchestration](terminal-native-agent-fleet-orchestration.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed delegated coding, visible progress, and evidence-handoff guidance.
- Maintained on 2026-06-25 with longer-horizon delegated-work handoff requirements.
- Maintained on 2026-06-27 with handoffs as rehydration artifacts and remote-agent supervision evidence.
- Maintained on 2026-06-28 with remote-control steering, review, organization, and intervention evidence.
- Maintained on 2026-07-14 with accountable-owner boundaries, proof artifacts, independent verification, and integration-order handoff requirements.
- Maintained on 2026-07-16 with issue-tracker control-plane, PR review-state, governance-field, and audit-evidence handoff requirements.
- Maintained on 2026-07-27 with local, managed-worktree, cloud, repository-native, and browser-agent execution-boundary handoff criteria.
- Maintained on 2026-07-30 with supervised cross-environment handoff routing.
- Maintained on 2026-08-05 with issue, PR, CI, review-comment, merge-queue, and worker-owner handoff evidence for terminal agent fleets.
