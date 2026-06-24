# Agent Harness Components

## Current Understanding

An agent harness is the fixed runtime architecture that lets a model act, observe the result, and continue toward a goal. The [agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md) distinguishes a harness from a framework: a framework gives a human abstractions to assemble, while a harness ships an operating loop, tool registry, context control, persistence, hooks, and permission layer that an agent can use directly.

The local harness component model includes an iteration loop, context management and compaction, a tool and skill registry, subagent management, built-in primitives, session persistence, dynamic instruction assembly, lifecycle hooks, and dispatch-time permissions. These components support the broader [application harness patterns](application-harness-patterns.md) page by naming the runtime pieces that must be present before a model-backed application can safely do work.

## Practice Boundaries

- Treat the outer iteration loop as the runtime boundary that decides when to call tools, observe results, continue, or stop.
- Keep tool descriptors, permissions, and handlers in a registry so execution can be inspected and controlled.
- Persist session events in an append-only form when resume, audit, or crash recovery matters.
- Assemble durable instructions from stable project files without letting dynamic context break source authority.
- Use lifecycle hooks for policy, logging, and observability without putting every control in model instructions.
- Enforce permissions before tool execution, especially for file writes, shell commands, network access, and external systems.

## Authoritative Sources

- [Agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md)
- [application harness patterns](application-harness-patterns.md)
- [subagent coordination](../agent-workflows/subagent-coordination.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)

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
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold harness runtime components separately from broader application architecture.
