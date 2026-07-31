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

## Practice Boundaries

- Emit lifecycle hooks for session start, tool-surface changes, approvals, memory updates, verification steps, failure states, and completion.
- Treat lifecycle hooks as policy, logging, and observability surfaces rather than hidden prompt reminders.
- Join hook events with environment, approval, tool-call, and verification evidence when the workflow needs auditability.
- Keep hook handlers narrow enough that policy checks, logging, and recovery updates can be tested independently.
- Record hook failures as workflow evidence when they affect approval, audit, telemetry, or recovery guarantees.

## Authoritative Sources

- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
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
