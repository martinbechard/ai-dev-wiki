---
type: "Adoption And Operating Model"
title: "Human Agent Approval Boundaries"
description: "Human-agent approval boundaries define which work an agent can perform, which work requires review, and which decisions remain human-owned."
tags: ["adoption-and-operating-model"]
---

# Human Agent Approval Boundaries

## Current Understanding

Human-agent approval boundaries define which work an agent can perform, which work requires review, and which decisions remain human-owned. The local boundary is that humans own goals, tradeoffs, accountability, and final acceptance, while agents can inspect, draft, patch, verify, and report within the approved workflow.

Approval boundaries are both operating practice and governance control. The operating agreement names when a human must decide; [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md) owns the infrastructure controls that enforce permissions, least privilege, audit, and policy.

Consequential actions need explicit approval or policy gates. This includes actions affecting files, dependencies, credentials, external systems, production-like data, or externally visible output.

The [workspace agents source](../../../raw/processed/OpenAI Just Gave Every Team A Free Employee. Here's The Catch..md) and [agent ownership source](../../../raw/processed/You Can't Run AI Agents Without This.md) sharpen the local boundary for recurring team agents: the strongest first candidates are known-path workflows with a clear output, a human reviewer, and a measurable time-saving goal. Agents should not be evaluated first on novel, judgment-heavy, open-ended strategy work where failures cannot be attributed to workflow, context, connectors, rubric, or model behavior.

The [leaf update watch source](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json) adds a public security-control lens: autonomy should increase through verified behavior, sandboxing, monitoring, containment, and incremental permissions rather than one-time trust. Approval boundaries should distinguish low-risk drafting or inspection from actions that expand tool access, touch sensitive systems, or create external effects.

The [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json) adds runtime authorization and audit signals. Approval boundaries should include step-level guardrails, tool-call authorization, session monitoring, explicit block thresholds, and audit trails before risky actions execute. A team should treat those controls as part of the approval boundary itself, not as documentation after an agent has already acted.

The [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json) adds generated-code and gateway-control signals. Approval boundaries should separate execution isolation from capability isolation, grant host capabilities explicitly, preserve durable human pauses, and use per-agent gateway policy when recurring agents can cross from inspection into action.

The [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) adds managed approval-mode, mobile delegation, and review-dismissal signals. Teams should distinguish the ability to request an agent fix from authority to merge or dismiss reviews, and should make permission modes, bypass controls, and sensitive-operation approvals centrally visible when the same agent can run from editor, CLI, or mobile surfaces.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) and [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json) add explicit command-approval pressure for untrusted repositories and workspace customizations. Approval boundaries should block shell execution, dependency setup, credential access, and external-system actions until the repository, instruction files, and generated customization surfaces have passed trust review.

The [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json) adds misleading-approval and generated-source signals. Approval prompts should describe the actual write path, target workspace, data access, and side effect before action, and undo-after-write or post-hoc confirmation is not the same control as pre-action approval for symlink writes, package installs, repository fetches, or public output.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) adds accountable-ownership and production-control signals. Agents can coordinate milestones, implementation, tests, docs, and review, but humans retain approval for scope, production, security, migration, and customer-impacting decisions. Production coding-agent controls should make isolation, scoped permissions, monitoring, and audit trails enforce the approval boundary rather than relying on the agent to remember it.

The July 17 raw sources add approval-surface refinements. The [topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) records dependency remediation, autofix, terminal denial reasons, and build optimization as cases where the agent may prepare changes or experiments while the human retains merge, command, baseline, experiment, and application decisions. Destructive command approvals route to [destructive command controls](../governance-and-risk/destructive-command-controls.md), and optimization approvals route to [agent-assisted performance optimization gates](../verification-and-evals/agent-assisted-performance-optimization-gates.md).

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) adds issue-triage and draft-PR handoff evidence. Approval boundaries should show an agent rationale, confidence signal, proposed state change, progress evidence, and review request before suggested issue metadata, Linear handoffs, or generated pull requests become accepted workflow state.

## Practice Boundaries

- Define which tasks can be delegated, which require review, and which require human execution.
- Require an explicit done signal with evidence, not only a fluent summary.
- Keep approval points visible inside the workflow so the human can stop, redirect, or accept the work.
- Treat approval requirements as stronger when the workflow touches security, privacy, costs, credentials, dependencies, or irreversible external state.
- Start recurring team agents on known-path work with a visible reviewer and a clear output standard.
- Reject or redesign agents whose workflow is too ambiguous for the owner to describe in one paragraph.
- Escalate permissions progressively from observed behavior, verification evidence, and sandbox results.
- Define block thresholds, approval checkpoints, audit trails, and session monitoring before agents can cross from inspection into mutation.
- Treat tool-call authorization as a runtime approval boundary when an action can affect code, data, costs, or external systems.
- Separate execution isolation from capability isolation when agents run generated code or delegated tools.
- Preserve durable human pauses and explicit host capability grants before unattended agents mutate code, data, or external systems.
- Keep permission modes and bypass controls centrally visible for recurring team agents.
- Separate request, repair, review, dismissal, merge, and release authority even when all actions are reachable from one agent-enabled surface.
- Require trust review before repo-local instructions, generated customization files, or untrusted source content can authorize shell commands, dependency setup, credential use, or external-system actions.
- Make approval prompts expose actual target paths, external systems, data classes, and side effects before action.
- Treat undo-after-write prompts and post-hoc confirmations as insufficient for symlink writes, public output, package installs, source fetching, or credential-adjacent access.
- Keep scope, production, security, migration, and customer-impacting decisions human-owned even when an agent coordinates the project workflow.
- Enforce approval boundaries through isolation, scoped permissions, monitoring, and audit trails for production coding agents.
- Keep agent-generated remediation, optimization, and security findings in reviewable packets until a human accepts the merge, command execution, experiment, or production action.
- Attach approval prompts to measurable baselines, sandbox boundaries, permission scopes, and generated workflow packages instead of asking for one broad autonomy grant.
- Route destructive-command and performance-optimization approvals through their focused control pages when command risk or measurement evidence changes the decision.

## Authoritative Sources

- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [Workspace agents source](../../../raw/processed/OpenAI Just Gave Every Team A Free Employee. Here's The Catch..md)
- [Agent ownership source](../../../raw/processed/You Can't Run AI Agents Without This.md)
- [Leaf Update Watch](../source-workflows/leaf-update-watch.md) source: [raw artifact](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json)
- [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json)
- [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json)
- [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption operating agreements](adoption-operating-agreements.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [delegated coding handoffs](../agent-workflows/delegated-coding-handoffs.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [agent ownership rosters](agent-ownership-rosters.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [destructive command controls](../governance-and-risk/destructive-command-controls.md)
- [agent-assisted performance optimization gates](../verification-and-evals/agent-assisted-performance-optimization-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-07-23 with rationale, confidence, proposed-change, progress, and draft-PR approval evidence for issue-to-agent workflows.
- Created on 2026-06-23 from source-backed approval, delegation, and human-accountability guidance.
- Maintained on 2026-06-23 with public AI control guidance on progressive permissions, sandboxing, monitoring, and containment.
- Maintained on 2026-07-01 with runtime tool authorization, block thresholds, monitoring, and audit trails as approval boundaries.
- Maintained on 2026-07-05 with execution isolation, capability isolation, durable human pauses, explicit host capabilities, and gateway policy signals.
- Maintained on 2026-07-08 with managed permission modes, bypass controls, mobile repair delegation, and review-dismissal authority separation.
- Maintained on 2026-07-09 with untrusted-repository, AGENTS.md, and generated customization command-approval boundaries.
- Maintained on 2026-07-13 with pre-action approval clarity for symlink writes, package installs, repository fetches, public output, and credential-adjacent access.
- Maintained on 2026-07-14 with accountable-ownership decisions and production-agent approval enforcement controls.
- Maintained on 2026-07-17 with remediation, command, sandbox, permission-scope, and performance-optimization approval routing.
