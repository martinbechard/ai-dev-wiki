---
type: "Adoption And Operating Model"
title: "Agent Ownership Rosters"
description: "Every agentic workflow that reads important context, produces work people act on, touches shared workflows, or can affect external systems needs a named owner."
tags: ["adoption-and-operating-model"]
---

# Agent Ownership Rosters

## Current Understanding

Every agentic workflow that reads important context, produces work people act on, touches shared workflows, or can affect external systems needs a named owner. The [agent ownership source](../../../raw/processed/You Can't Run AI Agents Without This.md) frames ownership as the 2026 maintenance skill: the team should know the agent job, context diet, boundaries, review cadence, and known failure modes before relying on the work.

The local ownership roster is a lightweight operating artifact, not a governance theater exercise. It lists each meaningful agent, its owner, what it does, what it reads, what it can touch, what it cannot do, how review happens, and when it should be paused or decommissioned. This complements [human agent approval boundaries](human-agent-approval-boundaries.md), which owns the approval rule, and [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md), which owns enforcement.

The [June 27 leaf update watch source](../../../raw/processed/2026-06-27/ai-dev-wiki-leaf-update-watch-2026-06-27T210128-0400.json) reinforces ownership as a single-responsible-owner practice. An ownership card should name the owner, job definition, data sources, permissions, dependencies, known failure modes, review cadence, and decommission trigger so monitoring and handoff gaps are visible.

The [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json) adds governance-role evidence. Recurring agents should also record risk classification, deployer or owner obligations, gateway policy, logging and monitoring expectations, and human oversight evidence so the roster can support accountability rather than only inventory.

## Practice Boundaries

- Name one human owner for every recurring agentic job that affects team work.
- Record the agent job in one sentence so vague assistants do not become unmanaged workflows.
- Record the agent diet: source documents, tickets, examples, policies, repositories, and system connections it uses.
- Record boundaries: read, draft, write, send, delete, merge, update records, or touch external systems.
- Review the output on a cadence and update sources, examples, instructions, or permissions when failure modes appear.
- Decommission or pause agents that do important work but have no willing owner.
- Use an ownership card for recurring agents, including owner, job, data sources, permissions, dependencies, known failure modes, review cadence, and pause criteria.
- Treat shared ownership as a risk until one person is accountable for review, boundary updates, and decommissioning decisions.
- Add risk classification, gateway policy, logging, monitoring, and oversight evidence when an agent becomes part of a recurring team workflow.
- Record deployer or owner obligations clearly enough that compliance and operational reviews know who maintains the agent boundary.

## Authoritative Sources

- [Agent ownership source](../../../raw/processed/You Can't Run AI Agents Without This.md)
- [June 27 leaf update watch source](../../../raw/processed/2026-06-27/ai-dev-wiki-leaf-update-watch-2026-06-27T210128-0400.json)
- [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json)
- [human agent approval boundaries](human-agent-approval-boundaries.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption operating agreements](adoption-operating-agreements.md)
- [human agent approval boundaries](human-agent-approval-boundaries.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold agent roster and owner-card practice.
- Maintained on 2026-06-27 with single-responsible-owner and ownership-card fields from public practice updates.
- Maintained on 2026-07-05 with risk classification, gateway policy, logging, monitoring, oversight evidence, and deployer-obligation fields.
