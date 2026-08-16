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

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds environment-readiness criteria to harness sizing. When setup latency, secrets, dependency caches, network posture, or long-running jobs dominate the risk, the harness size should include managed environment provisioning, restart checks, artifact persistence, and policy evidence rather than only more prompt or orchestration logic.

The [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json) adds adjustable reasoning-depth as a runtime sizing control. A complex task can justify stronger reasoning, but the harness should expose the setting, expected task complexity, token or credit budget, and acceptance evidence instead of silently raising effort for every run.

The [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) adds production-failure readiness evidence. Harness sizing should grow when a workflow needs durable execution, checkpoint recovery, scoped MCP access, component identity, behavior baselines, containment testing, activity logging, and memory inspection; a demo-complete harness is undersized when it cannot survive failure or explain recovery.

## Practice Boundaries

- Size harness controls to action risk, context complexity, duration, and need for recovery.
- Use lighter harnesses for low-risk drafting or inspection workflows with clear human review.
- Require loop control, state, approvals, telemetry, persistence, compaction, and rollback evidence for long-running or mutating workflows.
- Revisit harness size when a workflow gains tools, credentials, external effects, or unattended execution.
- Include managed environment provisioning, restart checks, and artifact persistence when environment readiness is the limiting factor for unattended work.
- Treat reasoning depth, model effort, and credit budget as harness controls that should scale with task complexity and verification need.
- Avoid inheriting high-effort settings into routine or low-risk workflows without an explicit cost and quality reason.
- Include checkpointing, recovery, behavior baselines, scoped access, activity logging, containment tests, and memory inspection when workflow risk moves beyond assisted drafting.

## Authoritative Sources

- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [application harness patterns](application-harness-patterns.md)
- [agent harness components](agent-harness-components.md)
- [agent environment readiness](agent-environment-readiness.md)

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
- Maintained on 2026-07-30 with environment-readiness criteria for setup latency, secrets, restart checks, and artifact persistence.
- Maintained on 2026-08-04 with adjustable reasoning-depth and credit-budget controls as harness sizing inputs.
- Maintained on 2026-08-15 with durable execution, checkpoint recovery, scoped access, component identity, behavior-baseline, containment, activity-log, and memory-inspection sizing inputs.
