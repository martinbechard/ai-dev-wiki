---
type: "Application Pattern"
title: "Agent Session Recovery"
description: "Agent session recovery preserves enough durable state for a long-running agent workflow to resume without trusting a chat summary."
tags: ["application-patterns"]
---

# Agent Session Recovery

## Current Understanding

The [September 24 leaf update watch source](../../../raw/processed/2026-09-24/ai-dev-wiki-leaf-update-watch-2026-09-24T210226-0400.json) adds managed-runtime pause, resume, fork, checkpoint, conversation-history, and working-state evidence. Session recovery should verify the runtime state that will be restored, the checkpoint or fork point used, the permission and credential envelope that survives resume, and the artifacts proving the resumed agent continued the intended task rather than merely restarting with a plausible summary.

The [September 19 topic news collector source](../../../raw/processed/2026-09-19/ai-dev-wiki-topic-news-collector-2026-09-20T003157Z.json) adds cross-tool session recovery evidence. A recovered session should prove not only that text context transferred, but also that referenced attachments, local files, generated artifacts, and provenance anchors are still present or explicitly missing before work continues.

Agent session recovery preserves enough durable state for a long-running agent workflow to resume without trusting a chat summary. The recovery surface should include startup continuity checks, progress cursors, last material outputs, generated artifacts, verification evidence, and unresolved blockers.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) reinforces long-job durability and restart behavior as coding-agent environment criteria. The [July 30 leaf update watch source](../../../raw/processed/2026-07-30/ai-dev-wiki-leaf-update-watch-2026-07-30T210230-0400.json) adds file-backed wiki and recovery-feature evidence. Locally, a recoverable session needs both a trustworthy environment and durable evidence that a resumed human or agent can inspect.

The [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json) adds long-horizon harness evidence: state should survive fresh executor contexts, and auditor observations should remain inspectable without being overwritten by the next model step. Recovery records should therefore separate task plan, execution memory, verifier or auditor findings, and final artifact evidence.

The [August 20 leaf update watch source](../../../raw/processed/2026-08-20/ai-dev-wiki-leaf-update-watch-2026-08-20T210330-0400.json) adds token-type revocation and audit-log evidence. When recovery follows a credential, tool, or agent incident, the recovery record should name affected credential classes, deauthorization action, user notice, audit event, residual access, and whether unrelated trusted credentials were intentionally preserved.

The [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json) adds model-to-model continuation evidence. A recovered session should not assume that another model or agent can safely inherit the full prior trajectory; recovery records should separate durable repository state, accepted plan, unresolved blockers, trajectory summary, and verification evidence so a resumed agent can choose the minimum context needed for the handoff direction.

The [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) adds persistent-agent recovery evidence. Recovery should include wake or sleep state, self-created follow-up tasks, memory sources, sparse notification records, and external-change approvals before a resumed agent continues work.

The [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-30T003150Z.json) adds IDE and shared-agent recovery evidence:

- Interrupted-session restore should preserve the task cursor.
- Cross-application continuation should preserve permission mode and tool configuration.
- Shared session state should preserve review evidence so resumed work does not silently widen authority or lose human steering context.

The September 1 raw sources add prompt-timeline and queue recovery evidence. The [leaf update watch source](../../../raw/processed/2026-09-01/ai-dev-wiki-leaf-update-watch-2026-09-01T210240-0400.json) records prompt timelines tied to file changes, external-session continuation, and multiple windows connected to one session. The [topic news collector source](../../../raw/processed/2026-09-01/ai-dev-wiki-topic-news-collector-2026-09-02T003202Z.json) records editable queued prompts that sync to connected hosts, task identifiers, and active working-time visibility. Locally, recovery should compare queued intent, prompt timeline, changed files, host sync state, and active run state before sending more instructions.

The [September 6 topic news collector source](../../../raw/processed/2026-09-06/ai-dev-wiki-topic-news-collector-2026-09-07T003131Z.json) adds reply-recovery and context-preservation evidence. Recovery records should separate conversation memory, transport state, tool health, and unfinished human input before a resumed agent continues.

The [September 7 leaf update watch source](../../../raw/processed/2026-09-07/ai-dev-wiki-leaf-update-watch-2026-09-07T210258-0400.json) adds runtime reconnect and history evidence. Recovery records should preserve completed commands, patch history, Guardian review history, account-scoped MCP approval history, compressed rollout state, uncertain queued submissions, and service-drop recovery markers so a resumed agent can tell which actions are durable and which submissions still need confirmation.

The [September 17 leaf update watch source](../../../raw/processed/2026-09-17/ai-dev-wiki-leaf-update-watch-2026-09-17T210120-0400.json) adds coordinated cloud-thread recovery evidence. When a project runs multiple agent threads, recovery should preserve coordinator memory, shared goals, shared files, each thread's branch or repository copy, overlap detection, merge-conflict status, and the human review needed before parallel work is combined.

## Practice Boundaries

- Preserve checkpoint, fork, conversation-history, working-state, approval-policy, and credential-scope evidence before resuming a managed coding-agent session.
- Treat pause or fork APIs as recovery surfaces that need source-of-truth state checks, not as proof that the recovered agent still has correct context.

- Mark transferred-but-missing attachments and local files as recovery blockers or rehydration tasks rather than assuming transcript context is complete.

- Run startup continuity checks before resuming from a persistent workspace or durable session record.
- Preserve progress cursors, last material outputs, generated artifacts, verification evidence, and unresolved blockers in durable locations.
- Treat recovered filesystem state as untrusted until current instructions, source files, and validation evidence are rechecked.
- Link recovery records to the environment, approval, tool-call, and verification evidence that made the prior work acceptable.
- Archive or reset recovery state when it no longer matches the live repository or accepted plan.
- Separate task plan, execution memory, auditor findings, and artifact evidence so resumed work can rehydrate needed state without rewriting audit history.
- For security recovery, preserve credential class, revocation or deauthorization action, affected-user notice, audit-log reference, residual-access review, and containment result before resuming agent work.
- For model or agent continuation recovery, separate repository state, accepted plan, unresolved blockers, trajectory summary, and verification evidence before deciding how much prior reasoning to reload.
- Preserve permission mode, tool configuration, shared-session context, and review evidence when recovery crosses IDE, chat, or application surfaces.
- Compare queued prompts, prompt timeline, changed files, host sync state, task identifier, and active working time before resuming a long-running agent.
- Separate durable notes, searchable prior context, unanswered questions, and reply-recovery status before treating a recovered session as ready to continue.
- Preserve MCP failure counts and latency diagnostics when tool health explains why a session needs recovery.
- Preserve command history, patch history, verifier history, approval history, compression state, and uncertain queued submissions when reconnecting after runtime or service interruption.
- Preserve coordinator state, shared goals, shared file artifacts, per-thread branches or repository copies, overlap detection, and merge-conflict review evidence before resuming or merging coordinated agent work.

## Authoritative Sources

- [September 24 leaf update watch source](../../../raw/processed/2026-09-24/ai-dev-wiki-leaf-update-watch-2026-09-24T210226-0400.json)

- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-30T003150Z.json)
- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [July 30 leaf update watch source](../../../raw/processed/2026-07-30/ai-dev-wiki-leaf-update-watch-2026-07-30T210230-0400.json)
- [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json)
- [August 20 leaf update watch source](../../../raw/processed/2026-08-20/ai-dev-wiki-leaf-update-watch-2026-08-20T210330-0400.json)
- [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json)
- [September 1 leaf update watch source](../../../raw/processed/2026-09-01/ai-dev-wiki-leaf-update-watch-2026-09-01T210240-0400.json)
- [September 1 topic news collector source](../../../raw/processed/2026-09-01/ai-dev-wiki-topic-news-collector-2026-09-02T003202Z.json)
- [September 6 topic news collector source](../../../raw/processed/2026-09-06/ai-dev-wiki-topic-news-collector-2026-09-07T003131Z.json)
- [September 7 leaf update watch source](../../../raw/processed/2026-09-07/ai-dev-wiki-leaf-update-watch-2026-09-07T210258-0400.json)
- [September 17 leaf update watch source](../../../raw/processed/2026-09-17/ai-dev-wiki-leaf-update-watch-2026-09-17T210120-0400.json)
- [agent harness components](agent-harness-components.md)
- [persistent agent workspaces](../agent-workflows/persistent-agent-workspaces.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent harness components](agent-harness-components.md)
- [persistent agent workspaces](../agent-workflows/persistent-agent-workspaces.md)
- [agent environment readiness](agent-environment-readiness.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-09-25 with managed-runtime pause/resume/fork, checkpoint, and working-state evidence.

- Maintained on 2026-09-19 with cross-tool session-transfer, attachment-rehydration, and provenance-check guidance.
- Maintained on 2026-08-29 with interrupted-session restore, cross-application continuation, permission-mode, tool-configuration, and review-evidence recovery guidance.
- Maintained on 2026-08-29 with persistent-agent wake/sleep, follow-up task, memory-source, notification, and approval recovery evidence.
- Created on 2026-07-30 from public evidence about long-job durability, restart behavior, file-backed recovery features, and durable session evidence.
- Maintained on 2026-08-08 with fresh-context executor, read-only auditor, execution-memory, and artifact-evidence recovery boundaries.
- Maintained on 2026-08-20 with credential-class revocation, deauthorization, user-notice, audit-log, residual-access, and containment recovery evidence.
- Maintained on 2026-08-26 with model-to-model continuation boundaries separating repository state, accepted plan, blockers, trajectory summaries, and verification evidence.
- Maintained on 2026-09-01 with prompt-timeline, queue-editing, host-sync, task-identifier, and active-working-time recovery evidence.
- Maintained on 2026-09-06 with context-note, searchable-history, async-question, reply-recovery, MCP-failure, and latency-diagnostic recovery evidence.
- Maintained on 2026-09-07 with command-history, patch-history, review-history, approval-history, compression-state, and uncertain-submission recovery evidence.
- Maintained on 2026-09-17 with coordinator-state, shared-goal, shared-file, per-thread-branch, overlap, merge-conflict, and parallel-work recovery evidence.
