---
type: "Agent Workflow"
title: "Event-Triggered Agent Workflows"
description: "Event-triggered agent workflows turn alerts, issues, CI signals, schedules, or webhook events into controlled agent runs."
tags: ["agent-workflows"]
---

# Event-Triggered Agent Workflows

## Current Understanding

Event-triggered agent workflows turn alerts, issues, CI signals, schedules, or webhook events into controlled agent runs. The local practice is to treat each trigger as a workflow contract: what event started the agent, what repository or environment it may inspect, which actions are allowed, where approvals appear, and which evidence proves the run stayed inside scope.

The [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) records governed GitLab automation and issue-to-autofix flows as product evidence for this local pattern. Broad product coverage belongs upstream in the [AI coding agents hub](../../../upstream-ai-wiki/developer-tools/ai-coding-agents-and-autonomous-engineering-platforms.md); locally, event-triggered agents need bounded triggers, explicit allowed actions, run evidence, and handoff points before they can mutate code, dependencies, external systems, or shared workflow state.

This page owns the trigger-driven workflow shape. [Governance controls for agents](../governance-and-risk/governance-controls-for-agents.md) owns the control model, [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md) owns identity, authorization, monitoring, and audit enforcement, and [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md) owns decisions that remain human-owned.

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) adds issue-to-agent handoff evidence from GitHub Issues and Linear-backed Copilot cloud agent workflows. Locally, event-triggered issue agents should preserve the source issue, rationale, confidence, proposed metadata changes, isolated execution environment, progress stream, draft pull request, and human review point before the workflow mutates backlog state or code.

The [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json) refines the issue-to-agent pattern. CI repair from a failed check should create a separate reviewable repair proposal when the platform supports it, and issue-tracker assignment should carry branch controls, progress streaming, model or agent choice, steering comments, and an explicit review request.

The [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) adds scheduled and host-driven agent execution evidence. Event-triggered workflows should distinguish scheduled worktrees, agent-host sessions, and CI or issue-triggered runs because each trigger changes inherited context, approval timing, progress visibility, and review handoff.

The August 18 raw sources add channel-trigger and queued-work signals. The [leaf update watch source](../../../raw/processed/2026-08-18/ai-dev-wiki-leaf-update-watch-2026-08-18T210146-0400.json) records agents responding automatically to Slack channel messages without an explicit mention and coding-agent surfaces that accept queued prompts or shell commands during a running task. The [topic news collector source](../../../raw/processed/2026-08-18/ai-dev-wiki-topic-news-collector-2026-08-18T203320-0400.json) adds fire-and-track process receipts for long-running MCP-triggered work. Locally, passive channel events and queued steering are event triggers too; they need trigger scope, owner, noise controls, approval timing, and receipt evidence before they become standing automation.

The August 25 raw sources add connector-trigger and reviewable-workflow evidence. The [evening topic news collector source](../../../raw/processed/2026-08-25/ai-dev-wiki-topic-news-collector-2026-08-25T203315-0400.json) records event-triggered scheduled tasks from Gmail, Slack, and GitHub events plus Runme and WebMCP notebook workflows for recurring Codex work, while the [evening leaf update watch source](../../../raw/processed/2026-08-25/ai-dev-wiki-leaf-update-watch-2026-08-25T210131-0400.json) records MCP roadmap and PR-review automation signals. Locally, connector-triggered workflows should preserve app authorization, watched resource scope, trigger coalescing, pending-event review, notebook or command evidence, and GitHub activity provenance before an event starts or mutates coding work.

The [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) adds AI-native orchestration evidence. Event-triggered agent workflows should record the event source, business rule, agent role, human approval point, automation dependency, application boundary, and completion evidence before recurring triggered actions are allowed.

## Practice Boundaries

- Name the event, issue, alert, CI signal, schedule, or webhook that started the agent run.
- Bind the trigger to repository, branch, workspace, environment, service, and data-scope limits before tools execute.
- Define allowed actions separately for inspection, drafting, patching, dependency changes, external-system calls, and public output.
- Keep human approval visible when the agent crosses from diagnosis into mutation, merge, release, external response, or production-adjacent action.
- Preserve trigger payload, target scope, tool arguments, policy decisions, handoff notes, and verification evidence in the run record.
- Route recurring event-triggered agents through owner rosters, revocation paths, monitoring, and audit storage.
- Prefer reviewable PR-on-PR or draft-PR repair handoffs for CI failures instead of mutating the original branch without a separate review surface.
- Record branch selection, working branch, model or agent selection, steering comments, and progress-stream evidence for issue-triggered coding agents.
- Distinguish schedule, CI, issue, host-session, and manual triggers when inherited context, approval timing, or review handoff differs.
- Define channel, thread, mention, and passive-message trigger scope before allowing an agent to respond from collaboration events.
- Preserve queued prompt, queued command, receipt, owner, and cancellation evidence when an event starts or steers long-running agent work.
- Preserve connector authorization, watched-resource scope, pending-event review state, and source event provenance for Gmail, Slack, GitHub, CI, and notebook-driven triggers.

## Authoritative Sources

- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
- [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [source reconciliation and routing](../source-workflows/source-reconciliation-and-routing.md)
- [upstream AI coding agents hub](../../../upstream-ai-wiki/developer-tools/ai-coding-agents-and-autonomous-engineering-platforms.md)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [August 18 leaf update watch source](../../../raw/processed/2026-08-18/ai-dev-wiki-leaf-update-watch-2026-08-18T210146-0400.json)
- [August 18 topic news collector source](../../../raw/processed/2026-08-18/ai-dev-wiki-topic-news-collector-2026-08-18T203320-0400.json)
- [August 25 evening topic news collector source](../../../raw/processed/2026-08-25/ai-dev-wiki-topic-news-collector-2026-08-25T203315-0400.json)
- [August 25 evening leaf update watch source](../../../raw/processed/2026-08-25/ai-dev-wiki-leaf-update-watch-2026-08-25T210131-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent-workflows](index.md)
- [delegated coding handoffs](delegated-coding-handoffs.md)
- [persistent agent workspaces](persistent-agent-workspaces.md)
- [terminal agent workflows](terminal-agent-workflows.md)

## Open Questions

- The upstream AI wiki does not yet have a local GitLab entity leaf to link for the July 17 GitLab product signals.

## Maintenance Notes

- Maintained on 2026-08-29 with AI-native event-source, business-rule, approval-point, automation-dependency, boundary, and completion-evidence signals.
- Maintained on 2026-07-23 with issue-to-agent handoff evidence, rationale, confidence, progress streams, isolated execution, and review gates.
- Maintained on 2026-07-24 with CI repair PR-on-PR, branch-control, progress-stream, steering-comment, and review-request guidance.
- Created on 2026-07-17 from public raw artifacts about governed event-triggered automation and issue-to-agent handoffs.
- Maintained on 2026-07-27 with scheduled-worktree, agent-host, CI, issue, and manual trigger distinctions.
- Maintained on 2026-08-18 with passive channel-trigger, queued-steering, long-running receipt, owner, and noise-control evidence.
- Maintained on 2026-08-25 with connector-triggered task, GitHub event, notebook workflow, and PR-review automation evidence.
