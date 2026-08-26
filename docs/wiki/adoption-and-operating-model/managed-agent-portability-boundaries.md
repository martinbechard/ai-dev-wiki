---
type: "Adoption And Operating Model"
title: "Managed Agent Portability Boundaries"
description: "Managed agent portability boundaries evaluate which layers can move across providers and which remain tied to a vendor control plane."
tags: ["adoption-and-operating-model"]
---

# Managed Agent Portability Boundaries

## Current Understanding

Managed agent portability boundaries evaluate which layers can move across providers and which remain tied to a vendor control plane. Vertical integration means one provider supplies adjacent layers such as model, agent loop, hosted state, tools, sandbox, telemetry, and operations; it does not automatically mean every edge is closed.

The [managed agent vertical integration query source](../../../raw/processed/query/2026-08-05-managed-agent-vertical-integration.md) uses Claude Managed Agents as the motivating example. Broad Claude, Anthropic, MCP, and SDK coverage stays upstream-owned; locally, the durable rule is to evaluate portability layer by layer. A platform may expose custom tools, MCP servers, or self-hosted execution while keeping model choice, session semantics, agent versions, event streams, hosted state, and operational control plane proprietary.

The practical adoption test is whether the organization can move prompts and skills, tools and protocols, execution environments, durable state, telemetry, and control-plane policies separately. Self-hosted sandbox execution can reduce data exposure or satisfy infrastructure placement needs, but it is not the same as self-hosted orchestration state or a provider-neutral agent runtime.

Domain state, business records, and audit-critical workflow state should remain outside vendor session state when provider substitution, long-term audit, or cross-tool continuity matters. Vendor-managed state can still be useful, but it should be treated as runtime state with export and retention questions, not as the only durable system of record.

The August 17 [leaf update watch](../source-workflows/leaf-update-watch.md) adds cross-client packaging and compliance evidence. Agent Plugins, managed plugin/MCP settings, persistent memory, local model routing, debug visibility, local-session compliance endpoints, and workspace identity show that portability is constrained by more than prompt text. Locally, a managed-agent workflow should record which package manifest, skill files, MCP declarations, memory surfaces, transcript exports, and enterprise policy controls must move or be re-created before switching tools.

The [August 25 afternoon leaf update watch source](../../../raw/processed/2026-08-25/ai-dev-wiki-leaf-update-watch-2026-08-25T144100-0400.json) adds admin-plugin evidence for managed-agent portability. Admin-facing tools for workspace activity, credit usage, access, permissions, usage limits, spend requests, and supported actions are part of the managed control plane. Locally, portability review should record whether admin workflows, permission-aware tools, cost controls, recurring tasks, and action evidence can be exported, reproduced, or replaced when moving between managed agent environments.

## Practice Boundaries

- Evaluate managed-agent portability separately for models, prompts, tools, execution, state, telemetry, and control-plane semantics.
- Treat MCP and custom JSON-schema tools as tool-interoperability evidence, not proof that the agent runtime is model-neutral.
- Distinguish self-hosted execution from self-hosted orchestration state before classifying a managed platform as portable.
- Keep domain records, approval evidence, and workflow state in organization-owned systems when audit or provider substitution matters.
- Require export, retention, versioning, and trace semantics before relying on vendor session history as durable memory.
- Record portability gaps as selection criteria rather than flattening vertical integration into either open or closed.
- Record package manifests, skill files, MCP declarations, memory surfaces, transcript exports, workspace identity, and enterprise policy controls before claiming a managed-agent workflow can move between tools.
- Include admin workflow surfaces, permission-aware action tools, usage limits, spending controls, recurring tasks, and evidence receipts in portability reviews.

## Authoritative Sources

- [managed agent vertical integration query source](../../../raw/processed/query/2026-08-05-managed-agent-vertical-integration.md)
- [August 17 leaf update watch source](../../../raw/processed/2026-08-17/ai-dev-wiki-leaf-update-watch-2026-08-17T210257-0400.json)
- [August 25 afternoon leaf update watch source](../../../raw/processed/2026-08-25/ai-dev-wiki-leaf-update-watch-2026-08-25T144100-0400.json)
- [portable agent skills and runbooks](portable-agent-skills-and-runbooks.md)
- [durable instructions and skill files](durable-instructions-and-skill-files.md)
- [agent harness components](../application-patterns/agent-harness-components.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [portable agent skills and runbooks](portable-agent-skills-and-runbooks.md)
- [human agent approval boundaries](human-agent-approval-boundaries.md)
- [hybrid agent infrastructure economics](hybrid-agent-infrastructure-economics.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)

## Open Questions

- Which managed-agent providers export agent, session, trace, memory, and sandbox artifacts in provider-neutral formats?
- Which self-hosted modes relocate only execution, and which also relocate orchestration state and the control plane?

## Maintenance Notes

- Created on 2026-08-05 from a query fragment about managed-agent vertical integration, tool interoperability, and control-plane portability.
- Maintained on 2026-08-17 with Agent Plugins, managed plugin/MCP settings, memory, local model routing, debug visibility, compliance transcript, and workspace-identity portability boundaries.
- Maintained on 2026-08-25 with admin-plugin, usage, permission, spending, recurring-task, and action-evidence portability boundaries.
