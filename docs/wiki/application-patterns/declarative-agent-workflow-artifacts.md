---
type: "Application Pattern"
title: "Declarative Agent Workflow Artifacts"
description: "Declarative agent workflow artifacts make multi-step orchestration reviewable before runtime."
tags: ["application-patterns"]
---

# Declarative Agent Workflow Artifacts

## Current Understanding

Declarative agent workflow artifacts make orchestration state visible before an agent runs. The [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) records a workflow-artifact pattern for multi-agent orchestration, branching, tool calls, human approvals, checkpoints, and resume behavior.

The local practice is to treat the workflow artifact as source evidence, not as a framework catalog. Broad Microsoft Agent Framework background belongs upstream; this page owns the downstream review rule for workflow state that controls agent actions.

The [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json) adds a 1.0 workflow-definition signal. YAML or similar workflow definitions that coordinate agents, state changes, branch conditions, handoffs, checkpoints, resume, and Function, MCP, or HTTP tool steps should be reviewed as executable contracts before runtime.

The [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json) adds comment-triggered automation as a workflow-artifact signal. Trigger phrases in issues or pull requests, repository location, intended follow-up action, generated documentation scope, error-investigation behavior, and issue-creation rules should be reviewable before comments become recurring automation entry points.

## Practice Boundaries

- Review branching, tool-call, approval, checkpoint, and resume semantics before runtime execution.
- Keep human-approval and checkpoint state in the application process layer, even when a framework loads the workflow definition.
- Version workflow artifacts when they determine recurring team behavior.
- Require source review and verification before a declarative workflow can change code, dependencies, credentials, or external systems.
- Review tool-step definitions, state transitions, and branch conditions with the same care as code when they control agent execution.
- Version and review comment trigger phrases, allowed repositories, generated-output scope, and follow-up actions before event-triggered automations run from issues or pull requests.

## Authoritative Sources

- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json)
- [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json)
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

- Created on 2026-07-28 from July 28 raw evidence about reviewable workflow artifacts, branching, tool calls, approval points, checkpoints, and resume behavior.
- Maintained on 2026-07-29 with 1.0 declarative workflow definition, state-transition, and tool-step review guidance.
- Maintained on 2026-08-04 with comment-triggered automation boundaries for issues, pull requests, documentation generation, error investigation, and follow-up issue creation.
