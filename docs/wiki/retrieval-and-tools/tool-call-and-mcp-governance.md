---
type: "Retrieval And Tools"
title: "Tool Call And MCP Governance"
description: "Tool calls turn model intent into software-mediated action."
tags: ["retrieval-and-tools"]
---

# Tool Call And MCP Governance

## Current Understanding

Tool calls turn model intent into software-mediated action. The model requests an action with arguments, the harness validates schema and permissions, software executes outside the model, and the result becomes context for a continuation or final answer.

Dynamic context tools sit between retrieval and action. They let a model request targeted additional information when the application cannot know all needed context upfront. Action tools perform governed operations such as reading, writing, scheduling, querying, transforming, or updating external systems.

MCP is the local practice boundary for standardized tool access. It exposes typed tools through a server and client arrangement while credentials remain in the connector or server. Broad MCP ecosystem coverage belongs to the upstream [AI wiki MCP server index](../../../upstream-ai-wiki/mcp-servers/index.md); this page owns how local AI-assisted workflows should treat MCP as a governed access layer.

The [topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) adds a governed-execution lens for MCP and agent tools: tool governance should account for the acting identity, policy version, execution environment, runtime inventory, tool-call transcript, and generated-output validation. Vendor-specific governed MCP products remain upstream-owned; the local rule is that tool access should produce reviewable evidence when it can change code, data, infrastructure, or external systems.

The [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) adds three tool-governance requirements. MCP gateway practice should include per-tool policy, per-user or per-group scope, hosted tool catalog change detection, centralized audit logs, and data protection before tool responses reach the model. Tool output from externally controlled systems should be treated as untrusted content that cannot authorize shell commands, dependency changes, credential use, or cloud actions by itself. Model or provider routing should be recorded when available because hidden routing can affect reproducibility and evaluation evidence.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) add two operating controls. First, tool installation sources and marketplaces should be governed before a tool appears in an agent environment. Second, MCP-connected external data must be treated as untrusted evidence even when the MCP server itself is approved, because the content flowing through the server can still steer a coding agent toward unsafe actions.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) and [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) add consent, denial, and deterministic-control-plane signals. Tool catalogs, plugins, compiled agent artifacts, content hashes, MCP exposure, permission-denial reasons, authentication notices, and tamper-evident logs should be inspectable control-plane evidence rather than invisible agent behavior.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) adds another MCP security-practice signal: least privilege, allowlists, audit trails, data boundaries, and explicit approval gates should be present before MCP tools can affect code, repositories, infrastructure, or external systems.

The [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json) and [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) add tool-metadata and catalog-governance signals. Tool descriptions, Team MCP catalogs, organization groups, agent pickers, CLI surfaces, and approved integration marketplaces are instruction-bearing supply-chain inputs. A critical agent should not consume changed tool metadata, new server entries, or newly available command surfaces without provenance review, group scope, and re-approval when the action surface changes.

The [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json) and [FastMCP research source](../../../raw/processed/project-wiki-research-2026-07-01-fastmcp.md) add two governed-MCP boundaries. Browser-driving tools and remote MCP servers that can administer accounts, audit-log streams, or production-adjacent systems should be classified as privileged action surfaces with explicit scope, approval, and evidence requirements. FastMCP-style OpenAPI or FastAPI conversion is useful implementation context, but the local practice is to review the resulting tool surface as a designed least-privilege interface rather than exposing every route because a framework can generate it.

## Practice Boundaries

- Describe tools with names, argument schemas, output contracts, and permission expectations.
- Validate tool arguments, user authority, workflow limits, and approval requirements before execution.
- Keep credentials in the harness, connector, or MCP server rather than exposing them in prompts.
- Log material tool requests, approvals, results, and failures when the workflow needs auditability.
- Prefer upfront retrieval when context is predictable and tool loops would add unnecessary cost.
- Use dynamic context tools when missing information is targeted and too large or uncertain for upfront context.
- Treat MCP servers as governed connectors, not as permission to bypass local approval rules.
- Record identity, policy, environment, approval, tool-call, and result evidence for high-impact agent tool use.
- Validate generated code or configuration outputs before they are accepted as tool results or committed artifacts.
- Default-deny high-impact MCP tools until policy, user scope, catalog change review, and audit logging are in place.
- Treat tool output and retrieved operational data as evidence, not as instructions that can expand agent authority.
- Record model routing or tool-provider routing metadata when it affects reproducibility, cost, or review evidence.
- Govern MCP server, plugin, and marketplace onboarding before they become available to agents.
- Apply untrusted-content handling to MCP-returned issue text, error reports, dependency metadata, and operational records, not only to open-web retrieval.
- Record plugin consent, permission denials, authentication notices, artifact hashes, and tool-log provenance when they affect trust or reproducibility.
- Require least privilege, explicit allowlists, data-boundary checks, audit trails, and approval gates for MCP tools that can change code, dependencies, infrastructure, or external records.
- Treat tool descriptions and MCP catalog metadata as live instructions that need review, provenance, and change detection before they reach acting agents.
- Govern IDE, CLI, cloud-agent, and marketplace tool availability with the same policy when they expose the same approved integration.
- Treat browser control, admin-capable remote MCP tools, and generated API-to-MCP surfaces as privileged tool categories that need allowlists, explicit approval, and auditable outcomes.
- Curate generated MCP tools for task fit, least privilege, schema clarity, and data exposure before allowing agents to use them.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [federation.md](../federation.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [RAG provenance ranking and chunking](rag-provenance-ranking-and-chunking.md)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json)
- [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json)
- [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json)
- [FastMCP research source](../../../raw/processed/project-wiki-research-2026-07-01-fastmcp.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [retrieval-and-tools](index.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [agent identity and delegated authority](../governance-and-risk/agent-identity-and-delegated-authority.md)
- [trajectory-level agent evaluation](../verification-and-evals/trajectory-level-agent-evaluation.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold dynamic context, action-tool, and MCP governance practice.
- Maintained on 2026-06-23 with public governed-MCP and runtime agent governance signals.
- Maintained on 2026-06-24 with MCP gateway policy, untrusted tool-output, and routing-aware evidence requirements.
- Maintained on 2026-06-25 with marketplace onboarding and MCP-returned content as explicit tool-governance boundaries.
- Maintained on 2026-06-26 with plugin consent, permission-denial evidence, deterministic control-plane artifacts, and tamper-evident tool logs.
- Maintained on 2026-06-27 with MCP least-privilege, allowlist, audit, data-boundary, and approval-gate practice.
- Maintained on 2026-07-01 with tool-description poisoning, Team MCP catalog, organization-scope, and native agent command-surface governance.
- Maintained on 2026-07-01 with browser-tool, admin-capable remote MCP, and generated API-to-MCP curation boundaries.
