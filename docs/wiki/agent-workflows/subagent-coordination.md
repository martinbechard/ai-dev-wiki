---
type: "Topic"
title: "Subagent Coordination"
description: "Subagent coordination delegates independent investigations to separate agent contexts while the main agent keeps ownership of the plan, decisions, integration, and final..."
tags: ["agent-workflows"]
---

# Subagent Coordination

## Current Understanding

Subagent coordination delegates independent investigations to separate agent contexts while the main agent keeps ownership of the plan, decisions, integration, and final verification. Subagents are useful when detailed investigation can stay separate until the evidence returns.

The [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md) describes subagents as specialized agents with their own context. The [gen AI application deck](../../../raw/processed/gen-ai-app-complete.md) describes user-facing agents and internal specialist agents such as planners, retrievers, workers, verifiers, writers, analysts, or tool specialists coordinated by software.

The local rule is that delegation does not transfer accountability. The main agent integrates returned evidence, checks conflicts, keeps unrelated changes out of scope, and verifies the combined result.

The [leaf update watch source](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json) captures public loop-design practice where heartbeat, cron, hook, and goal loops can coordinate subagents. The local implication is that recurring subagent loops need explicit state, stop conditions, evidence contracts, cost boundaries, and an independent validation role when one agent writes while another checks.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) treats coding subagent configuration as an explicit engineering activity. The local pattern is a typed delegation agreement: role boundary, context budget, allowed sources, handoff contract, completion criteria, and validation owner are set before the subagent starts work.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) adds role-and-skill separation for subagent systems. Specialized workers should have role definitions, objectives, tool budgets, return shapes, and moderation or validation loops, while reusable skills provide procedure. A coordinator may serve both, but local workflow design should keep the artifacts and accountability separate.

The [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json) adds dynamic-dispatch coverage signals. Subagent fan-out should be generated from explicit partitions, tracked through typed intermediate results, and reviewed by the main coordinator so broad delegated work can prove coverage instead of relying on conversational assurances.

The [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) adds a repo-derived role-design signal. Process mining over repository event logs can suggest project-specific agent roles, but local workflow design should treat those roles as hypotheses that need scope review, privacy checks, coordination-cost analysis, and validation against human expectations before they become standing subagents.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) adds enterprise multi-agent and modernization workflow signals. Multi-agent development platforms should define role separation, modernization workflow gates, cost telemetry, and administration boundaries before subagent fan-out becomes a standing operating surface.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) reinforces multi-agent modernization as a coordinated operating model. Subagent packages for COBOL, IBM i, Java, or other legacy modernization work should name role responsibilities, source-system constraints, verification gates, cost attribution, and human escalation paths before they are treated as reusable workflows.

The [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) adds model-native multi-agent and programmatic-tool signals. When a model or desktop surface supports multiple agents, the coordinator still needs role boundaries, shared-state rules, cache and tool-budget accounting, and evidence reconciliation. Programmatic tool calling can reduce intermediate context volume, but it also creates software-owned filtering decisions that the coordinator must log or verify before accepting subagent results.

## Practice Boundaries

- Use subagents for independent investigations with clear scope and evidence expectations.
- Keep the main agent responsible for synthesis, edit ownership, and final verification.
- Ask subagents to return evidence, findings, and risks rather than hidden intermediate context.
- Avoid overlapping file edits unless a coordinator explicitly assigns ownership and integration.
- Give recurring subagent loops a durable state record, retry or stop rule, budget boundary, and validation expectation.
- Use a separate verifier when a subagent performs broad generation, security-sensitive analysis, or recurring unattended work.
- Define subagent role boundaries, context budgets, source access, handoff fields, and completion criteria as a delegation contract.
- Keep worker roles, objectives, tool budgets, return shapes, and validation loops explicit when delegating through a coordinator.
- Do not let reusable skill content substitute for a role boundary or validation owner.
- Partition broad delegated work explicitly and preserve typed intermediate results for each partition.
- Require the coordinator to reconcile coverage, conflicts, failures, and skipped partitions before accepting subagent fan-out.
- Treat repository-derived agent roles as candidate delegation contracts, not automatic authority to mine or expose private process data.
- Validate proposed roles against observed workflow evidence, human expectations, coordination overhead, and privacy boundaries.
- Define modernization-workflow roles, gates, ownership, and cost telemetry before turning multi-agent platform packages into recurring team practice.
- Require source-system constraints, role responsibilities, verification gates, cost attribution, and escalation paths for legacy modernization subagent packages.
- Preserve coordinator ownership for role boundaries, shared state, cache use, tool budgets, and evidence reconciliation even when multi-agent support is built into the model or desktop surface.
- Log or verify programmatic filtering and intermediate-result decisions before accepting subagent outputs as complete evidence.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md)
- [Leaf Update Watch](../source-workflows/leaf-update-watch.md) source: [raw artifact](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json)
- [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent workflows](index.md)
- [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md)
- [delegated coding handoffs](delegated-coding-handoffs.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [agent cost telemetry](../adoption-and-operating-model/agent-cost-telemetry.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed subagent, specialist-agent, and integration guidance.
- Maintained on 2026-06-23 with public loop-design guidance on recurring subagent loops, independent validation, and stop conditions.
- Maintained on 2026-06-28 with typed delegation contracts for subagent configuration.
- Maintained on 2026-07-04 with coordinator-served roles, tool budgets, return shapes, and role-versus-skill boundaries.
- Maintained on 2026-07-05 with dynamic-dispatch partitioning, typed intermediate results, and coordinator coverage reconciliation.
- Maintained on 2026-07-07 with repo-derived role hypotheses, process-log privacy boundaries, and validation-before-delegation guidance.
- Maintained on 2026-07-09 with multi-agent modernization role, gate, cost, and administration boundaries.
- Maintained on 2026-07-13 with legacy-modernization subagent roles, source-system constraints, verification gates, cost attribution, and escalation paths.
- Maintained on 2026-07-14 with built-in multi-agent role boundaries, shared-state rules, cache/tool budget accounting, and programmatic filtering verification.
