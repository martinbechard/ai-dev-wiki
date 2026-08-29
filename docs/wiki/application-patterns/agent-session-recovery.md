---
type: "Application Pattern"
title: "Agent Session Recovery"
description: "Agent session recovery preserves enough durable state for a long-running agent workflow to resume without trusting a chat summary."
tags: ["application-patterns"]
---

# Agent Session Recovery

## Current Understanding

Agent session recovery preserves enough durable state for a long-running agent workflow to resume without trusting a chat summary. The recovery surface should include startup continuity checks, progress cursors, last material outputs, generated artifacts, verification evidence, and unresolved blockers.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) reinforces long-job durability and restart behavior as coding-agent environment criteria. The [July 30 leaf update watch source](../../../raw/processed/2026-07-30/ai-dev-wiki-leaf-update-watch-2026-07-30T210230-0400.json) adds file-backed wiki and recovery-feature evidence. Locally, a recoverable session needs both a trustworthy environment and durable evidence that a resumed human or agent can inspect.

The [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json) adds long-horizon harness evidence: state should survive fresh executor contexts, and auditor observations should remain inspectable without being overwritten by the next model step. Recovery records should therefore separate task plan, execution memory, verifier or auditor findings, and final artifact evidence.

The [August 20 leaf update watch source](../../../raw/processed/2026-08-20/ai-dev-wiki-leaf-update-watch-2026-08-20T210330-0400.json) adds token-type revocation and audit-log evidence. When recovery follows a credential, tool, or agent incident, the recovery record should name affected credential classes, deauthorization action, user notice, audit event, residual access, and whether unrelated trusted credentials were intentionally preserved.

The [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json) adds model-to-model continuation evidence. A recovered session should not assume that another model or agent can safely inherit the full prior trajectory; recovery records should separate durable repository state, accepted plan, unresolved blockers, trajectory summary, and verification evidence so a resumed agent can choose the minimum context needed for the handoff direction.

The [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) adds persistent-agent recovery evidence. Recovery should include wake or sleep state, self-created follow-up tasks, memory sources, sparse notification records, and external-change approvals before a resumed agent continues work.

## Practice Boundaries

- Run startup continuity checks before resuming from a persistent workspace or durable session record.
- Preserve progress cursors, last material outputs, generated artifacts, verification evidence, and unresolved blockers in durable locations.
- Treat recovered filesystem state as untrusted until current instructions, source files, and validation evidence are rechecked.
- Link recovery records to the environment, approval, tool-call, and verification evidence that made the prior work acceptable.
- Archive or reset recovery state when it no longer matches the live repository or accepted plan.
- Separate task plan, execution memory, auditor findings, and artifact evidence so resumed work can rehydrate needed state without rewriting audit history.
- For security recovery, preserve credential class, revocation or deauthorization action, affected-user notice, audit-log reference, residual-access review, and containment result before resuming agent work.
- For model or agent continuation recovery, separate repository state, accepted plan, unresolved blockers, trajectory summary, and verification evidence before deciding how much prior reasoning to reload.

## Authoritative Sources

- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [July 30 leaf update watch source](../../../raw/processed/2026-07-30/ai-dev-wiki-leaf-update-watch-2026-07-30T210230-0400.json)
- [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json)
- [August 20 leaf update watch source](../../../raw/processed/2026-08-20/ai-dev-wiki-leaf-update-watch-2026-08-20T210330-0400.json)
- [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json)
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

- Maintained on 2026-08-29 with persistent-agent wake/sleep, follow-up task, memory-source, notification, and approval recovery evidence.
- Created on 2026-07-30 from public evidence about long-job durability, restart behavior, file-backed recovery features, and durable session evidence.
- Maintained on 2026-08-08 with fresh-context executor, read-only auditor, execution-memory, and artifact-evidence recovery boundaries.
- Maintained on 2026-08-20 with credential-class revocation, deauthorization, user-notice, audit-log, residual-access, and containment recovery evidence.
- Maintained on 2026-08-26 with model-to-model continuation boundaries separating repository state, accepted plan, blockers, trajectory summaries, and verification evidence.
