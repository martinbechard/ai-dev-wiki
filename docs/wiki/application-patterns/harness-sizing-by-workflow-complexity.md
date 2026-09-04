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

The August 25 clipping and raw sources add generated-code execution and loop-to-graph escalation evidence. The [Run SDK clipping](../../../raw/processed/Introducing Run SDK secure eval for your agents.md) shows a narrow host-function boundary for untrusted JavaScript or TypeScript, durable interruption for approval or authentication, replay-safe resume, and timeout or memory limits. The [evening topic news collector source](../../../raw/processed/2026-08-25/ai-dev-wiki-topic-news-collector-2026-08-25T203315-0400.json) frames simple agent, durable loop, graph, and orchestration as increasing architecture levels. Locally, a harness should grow from sandboxed computation to resumable loops and graph coordination only when host-function authority, state, recovery, approval, or multi-agent topology requires it.

The [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json) adds AI model harness, long-running runtime, and workspace-layer evidence. Harness sizing should explicitly account for the layer that owns business context, memory, token cost, model routing, parallel workspaces, reviewable commits, durable execution, checkpoints, retries, scoped permissions, observability, and recovery.

The September 3 raw sources add security-control-plane and interoperability evidence:

- The [leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json) supports adding pre-tool classifiers, hardened sandboxes, critic/review roles, runtime mediation, and information-flow controls for high-risk workflows.
- The [topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json) treats harness specs, drift checks, durable sessions, permissions, memory, cost, approvals, and sandbox settings as portable configuration evidence.

## Practice Boundaries

- Size harness controls to action risk, context complexity, duration, and need for recovery.
- Use lighter harnesses for low-risk drafting or inspection workflows with clear human review.
- Require loop control, state, approvals, telemetry, persistence, compaction, and rollback evidence for long-running or mutating workflows.
- Revisit harness size when a workflow gains tools, credentials, external effects, or unattended execution.
- Include managed environment provisioning, restart checks, and artifact persistence when environment readiness is the limiting factor for unattended work.
- Treat reasoning depth, model effort, and credit budget as harness controls that should scale with task complexity and verification need.
- Avoid inheriting high-effort settings into routine or low-risk workflows without an explicit cost and quality reason.
- Include checkpointing, recovery, behavior baselines, scoped access, activity logging, containment tests, and memory inspection when workflow risk moves beyond assisted drafting.
- Use narrow host functions, serialized boundaries, resource limits, and replay-safe interruption when generated programs need to compute over trusted application capabilities.
- Escalate from a simple agent to a loop or graph when state, recovery, approval timing, delegation topology, or operations evidence justifies the added harness machinery.
- Add pre-tool classifiers, sandbox hardening, critic/review roles, information-flow controls, persistent-state inspection, and runtime mediation when a workflow can probe, exploit, repair, deploy, or cross trust boundaries.
- Treat declared harness specs, drift checks, context handling, permission stance, memory behavior, cost controls, approvals, and sandbox configuration as sizing evidence when a harness must move across runtimes.

## Authoritative Sources

- [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [Run SDK clipping](../../../raw/processed/Introducing Run SDK secure eval for your agents.md)
- [August 25 evening topic news collector source](../../../raw/processed/2026-08-25/ai-dev-wiki-topic-news-collector-2026-08-25T203315-0400.json)
- [September 3 leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json)
- [September 3 topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json)
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

- Maintained on 2026-08-29 with model-harness, workspace-layer, durable-runtime, cost-control, and recovery-sizing inputs.
- Created on 2026-07-28 from July 28 raw evidence about matching harness responsibilities to action and context complexity.
- Maintained on 2026-07-30 with environment-readiness criteria for setup latency, secrets, restart checks, and artifact persistence.
- Maintained on 2026-08-04 with adjustable reasoning-depth and credit-budget controls as harness sizing inputs.
- Maintained on 2026-08-15 with durable execution, checkpoint recovery, scoped access, component identity, behavior-baseline, containment, activity-log, and memory-inspection sizing inputs.
- Maintained on 2026-08-25 with generated-program sandbox, host-function, interruption, replay, and loop-to-graph escalation evidence.
- Maintained on 2026-09-03 with pre-tool classifier, hardened-sandbox, critic-review, runtime-mediation, information-flow, harness-spec, drift-check, and interoperability sizing evidence.
