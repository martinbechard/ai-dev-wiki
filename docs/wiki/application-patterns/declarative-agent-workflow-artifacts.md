---
type: "Application Pattern"
title: "Declarative Agent Workflow Artifacts"
description: "Declarative agent workflow artifacts make multi-step orchestration reviewable before runtime."
tags: ["application-patterns"]
---

# Declarative Agent Workflow Artifacts

## Current Understanding

The [October 2 topic news collector source](../../../raw/processed/2026-10-02/ai-dev-wiki-topic-news-collector-2026-10-02T003210Z.json) adds code-defined dynamic workflow evidence from upstream-owned GitHub Copilot surfaces. Locally, reusable agent workflows should treat staged steps, parallel lanes, structured handoffs, verification checkpoints, optional user input, and pause/resume points as reviewable workflow contract fields instead of burying those controls in one-off prompts.

The [October 3 topic news collector source](../../../raw/processed/2026-10-03/ai-dev-wiki-topic-news-collector-2026-10-03T003409Z.json) adds a second dynamic-workflow signal with commands, tools, services, parallel tasks, subagent verification, structured results, user input, checkpoints, and resume behavior. Locally, workflow-as-code artifacts should be source-reviewed like executable orchestration, including permission boundaries and handoff schemas.

Declarative agent workflow artifacts make orchestration state visible before an agent runs. The [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) records a workflow-artifact pattern for multi-agent orchestration, branching, tool calls, human approvals, checkpoints, and resume behavior.

The local practice is to treat the workflow artifact as source evidence, not as a framework catalog. Broad Microsoft Agent Framework background belongs upstream; this page owns the downstream review rule for workflow state that controls agent actions.

The [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json) adds a 1.0 workflow-definition signal. YAML or similar workflow definitions that coordinate agents, state changes, branch conditions, handoffs, checkpoints, resume, and Function, MCP, or HTTP tool steps should be reviewed as executable contracts before runtime.

The [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json) adds comment-triggered automation as a workflow-artifact signal. Trigger phrases in issues or pull requests, repository location, intended follow-up action, generated documentation scope, error-investigation behavior, and issue-creation rules should be reviewable before comments become recurring automation entry points.

The [August 27 leaf update watch source](../../../raw/processed/2026-08-27/ai-dev-wiki-leaf-update-watch-2026-08-27T210207-0400.json) adds updated declarative workflow evidence from an upstream-owned framework. Locally, YAML-defined actions, checkpoint and resume behavior, human input events, telemetry hooks, and serializer choices are executable workflow contract fields that should be source-reviewed before recurring agent workflows run.

The [September 8 leaf update watch source](../../../raw/processed/2026-09-08/ai-dev-wiki-leaf-update-watch-2026-09-08T210152-0400.json) adds loop and orchestration evidence for declarative workflows. Scheduled loops, squads, fleets, single/cascade/critique paths, validation checkpoints, and escalation behavior should be represented as reviewable workflow contract fields when they control recurring agent execution.

The [September 25 leaf update watch source](../../../raw/processed/2026-09-25/ai-dev-wiki-leaf-update-watch-2026-09-25T210020-0400.json) adds approval-risk and rewind-state evidence. Assisted approval rules, higher-risk prompts, redirect behavior, rewind state, conversation rollback, and file-change rollback should be represented as explicit workflow fields when an agent session can undo or redirect work.

The [October 5 topic news collector source](../../../raw/processed/2026-10-04/ai-dev-wiki-topic-news-collector-2026-10-05T003104Z.json) adds programmable workflow evidence. Locally, dynamic workflows should move orchestration control from free-form prompts into reviewable code or artifacts with stages, dependencies, parallel steps, structured handoffs, checkpoints, and human decision points.

The [October 7 leaf update watch source](../../../raw/processed/2026-10-07/ai-dev-wiki-leaf-update-watch-2026-10-07T210149-0400.json) adds dynamic-workflow availability as another signal for the same local contract. Reusable dynamic workflows should preserve:

- Step and tool definitions as source-reviewed artifacts.
- Parallel-agent lanes and structured result schemas.
- Peer verification, checkpoint, user-input, and resumability points.
- Release or CI gate ownership when the workflow can continue after the foreground turn.

## Practice Boundaries

- Review branching, tool-call, approval, checkpoint, and resume semantics before runtime execution.
- Keep human-approval and checkpoint state in the application process layer, even when a framework loads the workflow definition.
- Version workflow artifacts when they determine recurring team behavior.
- Require source review and verification before a declarative workflow can change code, dependencies, credentials, or external systems.
- Review tool-step definitions, state transitions, and branch conditions with the same care as code when they control agent execution.
- Version and review comment trigger phrases, allowed repositories, generated-output scope, and follow-up actions before event-triggered automations run from issues or pull requests.
- Treat declarative action definitions, checkpoint stores, human-input events, telemetry hooks, and persistence serializers as reviewable workflow fields when they affect agent execution or recovery.
- Record orchestration pattern, validation checkpoint, escalation rule, and fleet or squad role boundaries as workflow fields when recurring loops coordinate several agents.
- Review code-defined agent workflows for staged steps, parallel work, structured result schemas, handoff shape, verification gates, optional human input, and pause/resume semantics before teams reuse them.
- Preserve tool, service, subagent, user-input, checkpoint, resume, structured-result, and permission-boundary fields when code-defined workflows become reusable team artifacts.
- Record approval risk class, redirect target, rewind point, conversation rollback, and file rollback semantics when agent sessions can revise or undo prior work.
- Represent stages, dependencies, parallel lanes, structured handoffs, checkpoints, and human decisions as reviewable workflow fields rather than implicit prompt text.
- Treat dynamic-workflow availability as source evidence for workflow design, not as proof that the workflow's CI, release, or peer-verification gate is adequate.

## Authoritative Sources

- [October 2 topic news collector source](../../../raw/processed/2026-10-02/ai-dev-wiki-topic-news-collector-2026-10-02T003210Z.json)
- [October 3 topic news collector source](../../../raw/processed/2026-10-03/ai-dev-wiki-topic-news-collector-2026-10-03T003409Z.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json)
- [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json)
- [August 27 leaf update watch source](../../../raw/processed/2026-08-27/ai-dev-wiki-leaf-update-watch-2026-08-27T210207-0400.json)
- [September 8 leaf update watch source](../../../raw/processed/2026-09-08/ai-dev-wiki-leaf-update-watch-2026-09-08T210152-0400.json)
- [September 25 leaf update watch source](../../../raw/processed/2026-09-25/ai-dev-wiki-leaf-update-watch-2026-09-25T210020-0400.json)
- [October 5 topic news collector source](../../../raw/processed/2026-10-04/ai-dev-wiki-topic-news-collector-2026-10-05T003104Z.json)
- [October 7 leaf update watch source](../../../raw/processed/2026-10-07/ai-dev-wiki-leaf-update-watch-2026-10-07T210149-0400.json)
- [AI process layer and workflow state](ai-process-layer-and-workflow-state.md)
- [application harness patterns](application-harness-patterns.md)
- [upstream Microsoft Agent Framework](../../../upstream-ai-wiki/agentic-frameworks/microsoft-agent-framework.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [AI process layer and workflow state](ai-process-layer-and-workflow-state.md)
- [application harness patterns](application-harness-patterns.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-10-02 with code-defined dynamic workflow, structured handoff, verification checkpoint, user-input, and pause/resume evidence.
- Maintained on 2026-10-03 with commands, tools, services, subagent-verification, structured-result, checkpoint, resume, and permission-boundary evidence.
- Created on 2026-07-28 from July 28 raw evidence about reviewable workflow artifacts, branching, tool calls, approval points, checkpoints, and resume behavior.
- Maintained on 2026-07-29 with 1.0 declarative workflow definition, state-transition, and tool-step review guidance.
- Maintained on 2026-08-04 with comment-triggered automation boundaries for issues, pull requests, documentation generation, error investigation, and follow-up issue creation.
- Maintained on 2026-08-27 with declarative action, checkpoint, human-input, telemetry, and serializer fields as source-reviewable workflow contract evidence.
- Maintained on 2026-09-08 with scheduled loop, squad/fleet role, orchestration-pattern, validation-checkpoint, and escalation-rule evidence.
- Maintained on 2026-09-25 with assisted-approval risk classes, redirect, rewind, conversation-rollback, and file-rollback workflow evidence.
- Maintained on 2026-10-05 with programmable workflow stages, dependencies, parallel lanes, structured handoffs, checkpoints, and human-decision evidence.
- Maintained on 2026-10-07 with dynamic-workflow step, parallel-agent, structured-result, peer-verification, checkpoint, and resumability evidence.
