---
type: "Retrieval And Tools"
title: "Governed Database Agent Access"
description: "Governed database agent access exposes bounded, auditable data tools instead of arbitrary agent-generated queries."
tags: ["retrieval-and-tools"]
---

# Governed Database Agent Access

## Current Understanding

Governed database agent access exposes bounded, auditable data tools instead of arbitrary agent-generated queries. The [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json) records a downstream practice signal from [Oracle's production-database agent discussion](https://blogs.oracle.com/developers/what-we-learned-about-letting-agents-into-a-production-database):

- Prefer pre-approved reports or named data tools when the agent needs enterprise data.
- Scope query tools by role, data class, task purpose, and allowed side effects.
- Preserve audit evidence for the requester, tool, query or report, result class, and approval state.
- Route broad Oracle, database-product, MCP-server, and benchmark background to the upstream AI wiki.

This page owns the local retrieval and tool-use boundary for database access. [MCP scoped authorization and approval evidence](mcp-scoped-authorization-and-approval-evidence.md) owns the broader MCP approval package and stateful approval workflow.

The August 22 sources add two governed data-access refinements:

- The [topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json) records an Oracle SQLcl MCP workflow where saved connections, read-only validation, audit trails, durable memory tables, tool traces, retrieval evidence, and a validation notebook prove the database boundary before assistant use.
- The [leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json) adds governed semantic-layer and isolated-write practice: agents should select certified metrics or approved semantic objects before warehouse access, and write-capable data work should land in isolated branches or equivalent reviewable staging before publication.

## Practice Boundaries

- Prefer bounded reports, views, stored procedures, or role-scoped query tools over free-form SQL generation.
- Require source-of-truth ownership for each report or query tool before recurring agent use.
- Record requester identity, agent identity, role scope, data class, approved purpose, generated query or report name, and execution result.
- Treat write-capable database tools as consequential actions that require explicit authorization and post-action evidence.
- Keep database schema, credentials, customer data, and operational results out of raw artifacts unless the source workflow explicitly authorizes that capture.
- Validate database-agent workflows with saved-connection scope, read-only checks, audit trails, tool traces, retrieval evidence, and repeatable notebook or harness evidence before expanding access.
- Prefer certified metrics, semantic-layer permissions, lineage, row, column, tenant, and role restrictions over exposing raw tables to agent-generated query plans.
- Route write-capable data changes through isolated branches, publish gates, or equivalent staging so audit trails do not become the only control after production mutation.

## Authoritative Sources

- [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json)
- [Oracle production-database agent discussion](https://blogs.oracle.com/developers/what-we-learned-about-letting-agents-into-a-production-database)
- [MCP scoped authorization and approval evidence](mcp-scoped-authorization-and-approval-evidence.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [August 22 topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json)
- [August 22 leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [MCP scoped authorization and approval evidence](mcp-scoped-authorization-and-approval-evidence.md)
- [rag tools and MCP practice](rag-tools-and-mcp-practice.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-08-21 from raw-source evidence about bounded reports, role-scoped query tools, and audit evidence for database agents.
- Maintained on 2026-08-22 with saved-connection validation, semantic-layer restrictions, tool traces, retrieval evidence, and isolated-write controls for database agents.
