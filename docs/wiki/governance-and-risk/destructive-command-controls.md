---
type: "Governance And Risk"
title: "Destructive Command Controls"
description: "Destructive command controls treat file deletion, recursive mutation, path-crossing shell operations, and cleanup commands as high-risk agent actions."
tags: ["governance-and-risk"]
---

# Destructive Command Controls

## Current Understanding

Destructive command controls treat file deletion, recursive mutation, path-crossing shell operations, and cleanup commands as high-risk agent actions. The local rule is that a coding agent should not rely on model intent when a command can remove data, overwrite work, alter dependency state, or affect files outside the intended workspace.

The [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json) first routed destructive shell operations into local governance as a higher-risk action class. The [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) adds terminal-agent hardening evidence for broader forced-`rm` detection and clearer denial reasons. Broader shell-aware parsing, normalization, isolation, approval semantics, and audit controls are linked to the upstream-owned [shell command safety for coding agents](../../../upstream-ai-wiki/techniques/shell-command-safety-for-coding-agents.md) technique.

This page owns the downstream destructive-action enforcement rule. [Terminal agent workflows](../agent-workflows/terminal-agent-workflows.md) owns terminal-session workflow shape, [agent governance infrastructure](agent-governance-infrastructure.md) owns policy enforcement and audit, and [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md) owns the human decision boundary.

The [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) adds runtime approval-token evidence. Destructive-action controls should be enforced by the runtime as source-aware approval tokens or equivalent policy decisions, so untrusted context, retrieved logs, or model wording cannot silently authorize deletion, dependency mutation, network changes, or other side effects.

The [August 3 evening leaf update watch source](../../../raw/processed/2026-08-03/ai-dev-wiki-leaf-update-watch-2026-08-03T210231-0400.json) reinforces the same rule from an agent-security checklist lens. High-impact actions should keep authorization outside the model, reduce the available tool and data surface before access is granted, and record retest triggers when prompt, tool, retrieval, memory, policy, or model changes could alter command behavior.

The [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) adds containment and insider-threat evidence for agents with privileged or cross-system reach. Destructive-action controls should not stop at delete-command detection; they should also bound social actions, live security-test actions, lateral service calls, and chained individually legitimate operations that can produce harmful state changes when executed at agent speed.

The August 17 topic news collector adds a local sandbox example: commits, pushes, software installation, host credentials, and sensitive remote capabilities can be denied by environment design instead of repeatedly asking humans to confirm predictable high-risk actions. Locally, destructive-action controls should prefer capability denial and recoverable workspace design before relying on approval prompts.

The [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json) adds context-aware action-control evidence. Destructive command controls should judge whether a proposed high-impact action belongs to the current task and approved payload, not only whether the command, user, or tool is normally allowed.

The [August 29 leaf update watch source](../../../raw/processed/2026-08-29/ai-dev-wiki-leaf-update-watch-2026-08-29T210148-0400.json) adds a destructive-automation incident signal:

- Cleanup, reset, delete, migration, and generated-script workflows need dry-run evidence.
- Isolated fixtures, path allowlists, rollback or backup evidence, and human review should exist before execution outside a scratch workspace.
- Safety tests should not reuse production-adjacent paths without explicit containment evidence.

The [September 2 leaf update watch source](../../../raw/processed/2026-09-02/ai-dev-wiki-leaf-update-watch-2026-09-02T210149-0400.json) adds another destructive cleanup incident signal where a deletion-safeguard test reportedly affected a home directory. Locally, destructive-command controls should treat model downgrade, adversarial safety-check paths, variable reuse, and home-directory or production-adjacent fixtures as explicit risk inputs before any generated cleanup script runs.

The September 3 raw sources add cost, deployment, and infrastructure side-effect evidence:

- The [leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json) supports treating outbound spend, credential revocation, ERP risk zones, and infrastructure apply as high-impact action classes.
- The [topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json) reinforces governed execution for deployment-capable coding agents.

Locally, destructive-action controls should include spend exhaustion, cloud deployment, infrastructure mutation, and credential revocation alongside shell deletion.

## Practice Boundaries

- Classify forced removal, recursive delete, overwrite, cleanup, forced checkout, generated-script execution, dependency mutation, and path-crossing shell commands as destructive or high-risk unless policy proves otherwise.
- Preserve the proposed command, detected risk class, denial reason, terminal session, current workspace, and operator-visible decision in the run record.
- Deny or escalate destructive commands when the local harness cannot explain the target scope, intended side effect, or recovery path.
- Route shell-aware parsing, normalization, sandboxing, approval semantics, and command-audit architecture to the upstream shell command safety technique.
- Require runtime-held approval evidence for destructive or high-impact actions; prompt text and retrieved context are not approval tokens.
- Rerun destructive-action and high-impact approval tests after prompt, tool, retrieval, memory, policy, model, or permission-surface changes.
- Treat live security actions, public contact, service-to-service mutation, and chained high-speed operations as high-impact action classes when an agent's privileges make the combined effect destructive.
- Prefer sandbox-level denial for commits, pushes, installs, host credentials, and sensitive remote actions when the workflow does not require those capabilities.
- Block destructive or confidential-data actions when the command is individually valid but the action sequence, task context, or approved payload does not justify it.
- Require dry-run evidence, isolated fixtures, path allowlists, rollback or backup evidence, and human review before generated cleanup or deletion scripts run outside scratch workspaces.
- Reject destructive-safety tests that target home directories, production-adjacent paths, ambiguous variables, or model-dependent guard conditions unless an isolated fixture and recovery proof are already in place.
- Treat infrastructure apply, cloud deployment, outbound spend escalation, high-volume API use, and credential revocation as high-impact actions that need policy evidence, blast-radius scoring, and rollback or kill-switch paths.
- Prefer behavior-specific throttles or 429-style denials when a session exceeds an approved cost or request envelope before allowing the same credential to continue.

## Authoritative Sources

- [August 29 leaf update watch source](../../../raw/processed/2026-08-29/ai-dev-wiki-leaf-update-watch-2026-08-29T210148-0400.json)
- [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [August 3 evening leaf update watch source](../../../raw/processed/2026-08-03/ai-dev-wiki-leaf-update-watch-2026-08-03T210231-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [August 17 topic news collector source](../../../raw/processed/2026-08-17/ai-dev-wiki-topic-news-collector-2026-08-17T203101-0400.json)
- [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json)
- [September 2 leaf update watch source](../../../raw/processed/2026-09-02/ai-dev-wiki-leaf-update-watch-2026-09-02T210149-0400.json)
- [September 3 leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json)
- [September 3 topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json)
- [upstream shell command safety for coding agents](../../../upstream-ai-wiki/techniques/shell-command-safety-for-coding-agents.md)
- [governance controls for agents](governance-controls-for-agents.md)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance-and-risk](index.md)
- [terminal agent workflows](../agent-workflows/terminal-agent-workflows.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-08-29 with dry-run, isolated-fixture, path-allowlist, rollback, backup, and human-review evidence for destructive generated scripts.
- Created on 2026-07-17 from public raw artifacts about terminal-agent forced-removal detection and denial reasons, with broader command-safety controls routed to the upstream AI wiki.
- Maintained on 2026-07-28 with runtime approval-token guidance for destructive and high-impact agent actions.
- Maintained on 2026-08-03 with high-impact authorization, tool-surface reduction, and retest-trigger evidence.
- Maintained on 2026-08-15 with containment, insider-threat, live security-action, public-contact, service-mutation, and chained-operation risk evidence.
- Maintained on 2026-08-17 with sandbox-level denial for commits, pushes, installs, host credentials, and sensitive remote actions.
- Maintained on 2026-08-29 with task-context and approved-payload checks for high-impact actions.
- Maintained on 2026-09-02 with destructive cleanup incident evidence for model downgrades, adversarial safety checks, variable reuse, and home-directory fixture denial.
- Maintained on 2026-09-03 with spend-envelope, outbound-meter, behavior-specific kill-switch, credential-revocation, ERP risk-zone, infrastructure-blast-radius, and governed-deployment evidence.
