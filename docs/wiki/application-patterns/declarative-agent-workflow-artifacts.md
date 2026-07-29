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

## Practice Boundaries

- Review branching, tool-call, approval, checkpoint, and resume semantics before runtime execution.
- Keep human-approval and checkpoint state in the application process layer, even when a framework loads the workflow definition.
- Version workflow artifacts when they determine recurring team behavior.
- Require source review and verification before a declarative workflow can change code, dependencies, credentials, or external systems.

## Authoritative Sources

- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
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
