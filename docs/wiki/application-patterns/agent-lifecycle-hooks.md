---
type: "Application Pattern"
title: "Agent Lifecycle Hooks"
description: "Agent lifecycle hooks expose session and workflow events that policy, logging, observability, and recovery systems can inspect."
tags: ["application-patterns"]
---

# Agent Lifecycle Hooks

## Current Understanding

Agent lifecycle hooks expose session and workflow events that policy, logging, observability, and recovery systems can inspect. Hooks are useful when a harness needs to record session start, tool-surface changes, approvals, memory updates, verification steps, failures, and completion separately from model output.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) reinforces phase gates, sandbox permissions, and managed harness selection as runtime-control concerns. This page keeps the lifecycle-hook lens: hook points should make those transitions auditable instead of hiding them in prompt instructions or final summaries.

The [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json) and [August 20 leaf update watch source](../../../raw/processed/2026-08-20/ai-dev-wiki-leaf-update-watch-2026-08-20T210330-0400.json) add continuous-governance and startup-operating-practice signals. Hooks should fire when managed settings are applied, skills or files are loaded, browser action begins, approval mode changes, verification runs, credentials are revoked, or a human handoff is required. Locally, the hook contract should expose these state changes to policy and audit systems instead of leaving them as provider-specific product behavior.

## Practice Boundaries

- Emit lifecycle hooks for session start, tool-surface changes, approvals, memory updates, verification steps, failure states, and completion.
- Treat lifecycle hooks as policy, logging, and observability surfaces rather than hidden prompt reminders.
- Join hook events with environment, approval, tool-call, and verification evidence when the workflow needs auditability.
- Keep hook handlers narrow enough that policy checks, logging, and recovery updates can be tested independently.
- Record hook failures as workflow evidence when they affect approval, audit, telemetry, or recovery guarantees.
- Emit hooks for managed-policy application, skill or file loading, browser-action start, sandbox execution, approval-mode changes, credential revocation, and human handoff points.
- Use hooks to support continuous agent inventory and permission review when prompts, memory, models, tools, or access can change between runs.

## Authoritative Sources

- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json)
- [August 20 leaf update watch source](../../../raw/processed/2026-08-20/ai-dev-wiki-leaf-update-watch-2026-08-20T210330-0400.json)
- [agent harness components](agent-harness-components.md)
- [user-visible progress and runtime telemetry](user-visible-progress-and-runtime-telemetry.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent harness components](agent-harness-components.md)
- [user-visible progress and runtime telemetry](user-visible-progress-and-runtime-telemetry.md)
- [agent session recovery](agent-session-recovery.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-30 from public evidence about phase gates, sandbox permissions, managed harness controls, and auditable runtime transitions.
- Maintained on 2026-08-20 with managed-policy, skill/file loading, browser-action, approval-mode, credential-revocation, and continuous-governance hook points.
