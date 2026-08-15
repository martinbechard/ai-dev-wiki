---
type: "Retrieval And Tools"
title: "Progressive MCP Tool Discovery"
description: "Progressive MCP tool discovery keeps broad API catalogs out of active context until a task needs a specific operation."
tags: ["retrieval-and-tools"]
---

# Progressive MCP Tool Discovery

## Current Understanding

Progressive MCP tool discovery keeps broad API catalogs out of active context until a task needs a specific operation. The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) records an MCP server pattern where an agent starts with a small set of meta-tools and discovers task-specific API tools on demand. Broad MCP server and vendor coverage belongs upstream; this page owns the local context-budget and governance practice.

The [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) adds [remote MCP skill discovery and governance](remote-mcp-skill-discovery-and-governance.md) as a skill-loading variant. This page keeps the progressive-disclosure boundary; the remote-skill leaf owns package provenance, archive bounds, approval defaults, diagnostics, and central governance.

Discovery is useful only when it preserves both relevance and control. A discovered tool schema becomes dynamic context, so approval needs separate evidence for:

- Provenance of the discovered tool schema.
- Permission scope for the action surface.
- Field-level data scope for returned or writable data.
- Credential custody through managed OAuth or an equivalent control.
- Invocation logs for audit and replay.
- Remote skill-governance evidence when discovery loads reusable agent behavior rather than only a schema.

The [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json) adds a code-execution variant. Some tool-heavy workflows can keep full tool definitions and intermediate data out of active model context by letting the model write sandboxed code that calls tools through compact names or summaries. Locally, this remains a progressive-disclosure pattern only when sandbox limits, code-quality checks, token tradeoffs, and benchmark scope are recorded; limited benchmark gains should not be generalized across all MCP workloads.

## Practice Boundaries

- Use discovery when the full tool catalog would distract the model or exceed the useful context budget.
- Keep meta-tools narrow: discovery, selection, schema inspection, and request preparation should not silently perform high-impact actions.
- Require scoped permissions, field-level data limits, managed credential custody, and API logs for discovered tools.
- Record which tool schema was discovered, why it was selected, and which policy allowed invocation.
- Re-approve discovered tools when their schema, action scope, authentication, or returned-data authority changes.
- Route remotely discovered skill packages through [remote MCP skill discovery and governance](remote-mcp-skill-discovery-and-governance.md).
- Treat code-execution access to tool catalogs as a sandboxed progressive-disclosure variant, with explicit benchmark limits, output-token cost, code-quality review, and least-capability constraints.

## Authoritative Sources

- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json)
- [remote MCP skill discovery and governance](remote-mcp-skill-discovery-and-governance.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [context selection and compaction](../context-architecture/context-selection-and-compaction.md)
- [source reconciliation and routing](../source-workflows/source-reconciliation-and-routing.md)
- [upstream MCP server index](../../../upstream-ai-wiki/mcp-servers/index.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [context selection and compaction](../context-architecture/context-selection-and-compaction.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-27 from July 27 raw-source evidence about dynamic MCP mode, meta-tools, scoped permissions, managed OAuth, and API logs.
- Maintained on 2026-07-28 with remote skill discovery, package-provenance, archive-bound, approval-default, and central-governance controls.
- Maintained on 2026-08-14 with sandboxed code-execution as a progressive MCP discovery variant and benchmark-scope caveats.
