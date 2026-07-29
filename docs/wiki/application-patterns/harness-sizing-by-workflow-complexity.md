---
type: "Application Pattern"
title: "Harness Sizing By Workflow Complexity"
description: "Harness sizing by workflow complexity matches runtime controls to action risk and context complexity."
tags: ["application-patterns"]
---

# Harness Sizing By Workflow Complexity

## Current Understanding

Harness sizing by workflow complexity matches runtime controls to the risk and shape of the work. The [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) records two complementary signals: production harnesses need loop execution, planning, memory, context management, approvals, telemetry, history persistence, compaction, skills, and search, while harness complexity should still match the workflow's action and context complexity.

The local rule is to avoid both underbuilt and overbuilt harnesses. A low-risk drafting workflow can use lighter state and review. A long-running action workflow needs explicit loop control, tool execution, memory, approval, telemetry, persistence, compaction, and recovery evidence.

## Practice Boundaries

- Size harness controls to action risk, context complexity, duration, and need for recovery.
- Use lighter harnesses for low-risk drafting or inspection workflows with clear human review.
- Require loop control, state, approvals, telemetry, persistence, compaction, and rollback evidence for long-running or mutating workflows.
- Revisit harness size when a workflow gains tools, credentials, external effects, or unattended execution.

## Authoritative Sources

- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [application harness patterns](application-harness-patterns.md)
- [agent harness components](agent-harness-components.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [application harness patterns](application-harness-patterns.md)
- [AI process layer and workflow state](ai-process-layer-and-workflow-state.md)
- [user-visible progress and runtime telemetry](user-visible-progress-and-runtime-telemetry.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-28 from July 28 raw evidence about matching harness responsibilities to action and context complexity.
