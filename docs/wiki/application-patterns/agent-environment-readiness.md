---
type: "Application Pattern"
title: "Agent Environment Readiness"
description: "Agent environment readiness treats the execution substrate, setup state, secrets boundary, and restart behavior as first-class workflow design inputs."
tags: ["application-patterns"]
---

# Agent Environment Readiness

## Current Understanding

Agent environment readiness treats the execution substrate, setup state, secrets boundary, and restart behavior as first-class workflow design inputs. A coding agent cannot be evaluated only by prompt quality when its computer, dependencies, credentials, network posture, and durable files determine what it can safely do.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds a fast-start environment signal: teams should capture setup latency, dependency availability, secret isolation, long-job durability, restart semantics, and build-versus-buy criteria before treating an agent workflow as reliable. Broad platform and vendor identities stay upstream-owned; this page owns the downstream readiness checklist.

Readiness is a harness concern. [Agent harness components](agent-harness-components.md) owns the broader loop, tool registry, persistence, and permissions; this page owns the narrower question of whether the environment can be provisioned, constrained, resumed, and inspected well enough for the intended workflow.

The [July 31 leaf update watch source](../../../raw/processed/2026-07-31/ai-dev-wiki-leaf-update-watch-2026-07-31T210319-0400.json) adds sponsored but relevant evidence that runtime placement, privacy controls, local workhorse capacity, and cost-per-outcome expectations are readiness inputs. Because the source is vendor-positioned, the local rule is cautious: use it to ask whether local, managed, or cloud execution changes privacy, latency, cost, and verification evidence, not to assume one substrate is automatically better.

The August 13 raw sources add readiness evidence for managed agents, MCP incidents, operational-data access, and lifecycle controls. The [topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json) records MCP observability, transport-security findings, operational-data tool access, and escalation or kill-switch expectations. The [leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json) records managed-agent budget caps, inference geography, repository-loaded skills, workspace identity, and status incidents. Locally, environment readiness should include service health, geography, budget, skill-loading, transport security, and operational-data risk before unattended or recurring work runs.

The [August 14 leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json) adds prebuilt cloud-agent environment evidence. Readiness should include snapshot age, setup recipe, dependency cache, failed-build fallback behavior, warm-copy availability, commit SHA, build logs, and run-to-build mapping before a cloud or terminal agent claims its environment is ready for real work.

The August 26 raw sources add operation-scoped and WebMCP readiness evidence. The [leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json) records bounded operation authority and agent-ready site signals; the [topic news collector source](../../../raw/processed/2026-08-27/ai-dev-wiki-topic-news-collector-2026-08-27T003207Z.json) records browser-agent runtime controls. Locally, environment readiness includes whether the site, browser, tool server, or workspace exposes explicit agent-facing tools, identity boundaries, approval affordances, and reviewable interaction evidence.

The September 1 raw sources add runtime-profile and worktree-readiness evidence. The [topic news collector source](../../../raw/processed/2026-09-01/ai-dev-wiki-topic-news-collector-2026-09-02T003202Z.json) records named sandbox runtime profiles, migration fixers that avoid changing security intent, default no-sudo isolated-network Docker behavior, explicit gVisor or hypervisor isolation choices, and pre-run sandbox/network validation practices. The same source records worktree-aware run configurations and policy-aware model selection for IDE agents. Locally, environment readiness should require named runtime intent, migration evidence, runnable worktree configuration, model-policy eligibility, and boundary monitors before a coding agent starts.

## Practice Boundaries

- Define the runtime boundary before agents receive file, shell, network, package, or credential access.
- Record setup commands, dependency caches, environment variables, and known host assumptions when they affect reproducibility.
- Scope secrets to the task and keep secret availability separate from general workspace access.
- Check startup time, long-job survival, restart behavior, and artifact persistence before scheduling unattended agent work.
- Preserve logs, generated artifacts, and verification output where a resumed agent or human reviewer can inspect them.
- Prefer managed or reusable environment substrates when standard setup, isolation, recovery, identity, telemetry, and policy requirements are already provided.
- Reserve custom environment orchestration for workflows whose setup, security, latency, or integration needs cannot be met by an existing managed harness.
- Compare local, managed, and cloud execution substrates by privacy boundary, setup readiness, runtime telemetry, verification evidence, and cost per accepted outcome.
- Treat vendor-positioned infrastructure claims as prompts for local readiness checks rather than as direct substrate-selection rules.
- Check service health, inference geography, budget caps, skill-loading behavior, transport security, operational-data reach, and emergency-stop path before recurring or unattended agent work runs.
- Check prebuilt environment freshness, failed-build fallback behavior, setup provenance, dependency cache state, commit SHA, build logs, and agent-run build mapping before relying on hosted agent environments.
- Check operation-scoped authority, WebMCP or tool-boundary declarations, browser identity, trusted-site scope, approval affordances, and interaction evidence before treating a site or workspace as agent-ready.
- Record runtime profile, sudo and network posture, migration result, worktree run/debug target, model-policy eligibility, and boundary-monitor evidence before execution.

## Authoritative Sources

- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [July 31 leaf update watch source](../../../raw/processed/2026-07-31/ai-dev-wiki-leaf-update-watch-2026-07-31T210319-0400.json)
- [August 13 topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json)
- [August 13 leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json)
- [August 14 leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json)
- [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json)
- [August 27 topic news collector source](../../../raw/processed/2026-08-27/ai-dev-wiki-topic-news-collector-2026-08-27T003207Z.json)
- [September 1 topic news collector source](../../../raw/processed/2026-09-01/ai-dev-wiki-topic-news-collector-2026-09-02T003202Z.json)
- [agent harness components](agent-harness-components.md)
- [persistent agent workspaces](../agent-workflows/persistent-agent-workspaces.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent harness components](agent-harness-components.md)
- [harness sizing by workflow complexity](harness-sizing-by-workflow-complexity.md)
- [persistent agent workspaces](../agent-workflows/persistent-agent-workspaces.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-30 from public evidence about fast-start coding-agent environments, secret isolation, long-job durability, and managed-versus-custom substrate selection.
- Maintained on 2026-07-31 with sponsored runtime-placement, privacy, local-capacity, and cost-per-outcome readiness signals.
- Maintained on 2026-08-13 with managed-agent budget, inference-geography, repository-skill, service-health, MCP transport, and operational-data readiness checks.
- Maintained on 2026-08-14 with prebuilt environment snapshots, setup provenance, dependency-cache, failed-build fallback, commit-SHA, build-log, and run-to-build readiness checks.
- Maintained on 2026-08-26 with operation-scoped authority, WebMCP/tool-boundary declarations, browser identity, trusted-site scope, approval affordances, and interaction evidence for agent-ready environments.
- Maintained on 2026-09-01 with runtime-profile, migration-fixer, network-isolation, worktree-run-configuration, model-policy, and boundary-monitor evidence.
