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

The [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json) adds coding-fleet and verification-capacity signals. Parallel agent execution can increase candidate output faster than human or automated verification capacity, so the coordinator should assign owners, define merge-conflict controls, queue verification work, and stop fan-out when review capacity rather than generation is the bottleneck.

The July 18-21 raw sources add effort-routing and graph-control signals. The [Codex ultra-mode clipping](../../../raw/processed/what does theo have to say about Codex ultra mode.md) frames high-effort multi-agent mode as an escalation path rather than a default when subagents inherit expensive reasoning settings. The [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json) and [July 21 topic news collector source](../../../raw/processed/2026-07-21/ai-dev-wiki-topic-news-collector-2026-07-21T203101-0400.json) add loop and graph-engineering evidence: subagent systems should make routers, joins, human checkpoints, budgets, policies, trace identifiers, and stop rules visible before parallelism is treated as reliability.

The [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) adds agent-manager and multi-surface execution criteria. Subagent coordination should account for IDE, CLI, cloud, worktree, and terminal multiplexer surfaces as different supervision and handoff channels, and it should treat built-in agent teams as coordination overhead that still needs role boundaries, shared-state rules, and review capacity checks.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds cross-environment UI automation evidence. When subagents are specialized by planning, browser, desktop, automation, or summarization role, [supervised cross-environment handoffs](supervised-cross-environment-handoffs.md) owns the environment boundary and summary artifact while this page owns role separation and coordinator accountability.

The [CLI multi-agent orchestration research source](../../../raw/processed/project-wiki-research-2026-08-05-cli-multi-agent-orchestration.md) adds a terminal-native fleet distinction. The focused selection rule lives in [terminal-native agent fleet orchestration](terminal-native-agent-fleet-orchestration.md); this page keeps the coordination rule that in-process subagents, communicating agent teams, terminal multiplexers, and external worktree fleets need different isolation, shared-state, handoff, and review-capacity controls.

The August 13 sources add managed-agent and multiagent-hierarchy evidence. The [topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json) distinguishes agents used as tool-like calls from long-lived peers without clear hierarchy. The [leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json) records managed-agent budget caps, advisor roster entries, inference geography, and repository-loaded skills. Locally, subagent coordination should declare whether a worker is a bounded tool call, a peer actor, an advisor, or a managed long-running executor before delegation begins.

The [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json) adds task-queue and side-channel supervision evidence. When a CLI or app can create subagent tasks, queue prompts or shell commands, and ask the human questions without blocking the main turn, the coordinator still needs explicit ownership of queued work, approval timing, command scope, and returned evidence before integrating the result.

The [August 16 topic news collector source](../../../raw/processed/2026-08-16/ai-dev-wiki-topic-news-collector-2026-08-16T203133-0400.json) adds role-specialized software-development education evidence. Planner, coder, tester, reviewer, and manager roles are useful only when each role has an authority boundary, expected artifact, verification duty, handoff criterion, and human oversight point. Locally, a role label is not a delegation contract unless it also states what the coordinator will accept or reject when the subagent returns.

The [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-30T003150Z.json) adds a cost-aware model-routing signal for subagents:

- A stronger orchestrating model can reserve judgment, decomposition, and acceptance work.
- Cheaper implementation subagents are appropriate only for well-scoped mechanical changes.
- The task package, verification gate, and accepted-change metric should remain inspectable before cheaper routing is treated as lower-cost engineering.

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
- Pair multi-agent fan-out with owner assignment, merge-conflict control, verification queues, review-capacity limits, and explicit stop conditions.
- Route high-effort or high-cost subagents deliberately; do not let a parent mode silently cascade expensive reasoning, tool budgets, or autonomy into every delegated worker.
- Represent multi-agent graphs with explicit routers, joins, human checkpoints, identities, budgets, traces, and stop conditions before making them recurring workflow infrastructure.
- Compare IDE, CLI, cloud, worktree, and terminal-multiplexer coordination by supervision, isolation, handoff, and review-capacity evidence before choosing a subagent surface.
- Keep role separation, shared state, and summary artifacts explicit when subagents specialize by UI surface.
- Distinguish in-process subagents, vendor-managed agent teams, terminal multiplexers, and worktree-based fleets before applying one coordination rule to all of them.
- Classify each delegated agent as a bounded tool call, peer actor, advisor, or managed executor, then attach hierarchy, authority, budget, geography, skill-loading, and conflict-resolution rules to that class.
- Treat queued subagent prompts, queued shell commands, and side-channel questions as delegated work that needs owner, scope, approval state, and completion evidence before synthesis.
- Require each planner, coder, tester, reviewer, or manager subagent role to declare authority, expected artifact, verification responsibility, handoff criterion, and human oversight point.
- Reject returned subagent work when the evidence does not match the role contract, even if the role label sounds appropriate.
- Route cheaper subagents only for well-scoped mechanical work when the coordinator retains judgment, acceptance, and verification responsibility.

## Authoritative Sources

- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-30T003150Z.json)
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
- [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json)
- [Codex ultra-mode clipping](../../../raw/processed/what does theo have to say about Codex ultra mode.md)
- [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json)
- [July 21 topic news collector source](../../../raw/processed/2026-07-21/ai-dev-wiki-topic-news-collector-2026-07-21T203101-0400.json)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [CLI multi-agent orchestration research source](../../../raw/processed/project-wiki-research-2026-08-05-cli-multi-agent-orchestration.md)
- [August 13 topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json)
- [August 13 leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json)
- [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json)
- [August 16 topic news collector source](../../../raw/processed/2026-08-16/ai-dev-wiki-topic-news-collector-2026-08-16T203133-0400.json)

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
- [supervised cross-environment handoffs](supervised-cross-environment-handoffs.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [agent cost telemetry](../adoption-and-operating-model/agent-cost-telemetry.md)
- [terminal-native agent fleet orchestration](terminal-native-agent-fleet-orchestration.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-08-29 with cost-aware orchestrator/subagent model-routing and accepted-change evidence.
- Created on 2026-06-23 from source-backed subagent, specialist-agent, and integration guidance.
- Maintained on 2026-06-23 with public loop-design guidance on recurring subagent loops, independent validation, and stop conditions.
- Maintained on 2026-06-28 with typed delegation contracts for subagent configuration.
- Maintained on 2026-07-04 with coordinator-served roles, tool budgets, return shapes, and role-versus-skill boundaries.
- Maintained on 2026-07-05 with dynamic-dispatch partitioning, typed intermediate results, and coordinator coverage reconciliation.
- Maintained on 2026-07-07 with repo-derived role hypotheses, process-log privacy boundaries, and validation-before-delegation guidance.
- Maintained on 2026-07-09 with multi-agent modernization role, gate, cost, and administration boundaries.
- Maintained on 2026-07-13 with legacy-modernization subagent roles, source-system constraints, verification gates, cost attribution, and escalation paths.
- Maintained on 2026-07-14 with built-in multi-agent role boundaries, shared-state rules, cache/tool budget accounting, and programmatic filtering verification.
- Maintained on 2026-07-16 with coding-fleet verification capacity, owner assignment, merge-conflict control, and fan-out stop conditions.
- Maintained on 2026-07-22 with effort-routing, graph-control, trace, budget, and inherited-subagent mode boundaries.
- Maintained on 2026-07-27 with IDE, CLI, cloud, worktree, and terminal-multiplexer coordination criteria.
- Maintained on 2026-07-30 with cross-environment role separation and handoff-summary routing.
- Maintained on 2026-08-05 with terminal-native fleet orchestration boundaries and coordination-surface distinctions.
- Maintained on 2026-08-13 with managed-agent budgets, advisor rosters, inference geography, repository-loaded skills, and peer-versus-tool hierarchy boundaries.
- Maintained on 2026-08-14 with queued subagent prompt, queued shell command, side-channel question, approval-timing, and returned-evidence guidance.
- Maintained on 2026-08-16 with role-specialized subagent authority, artifact, verification, handoff, and oversight criteria.
