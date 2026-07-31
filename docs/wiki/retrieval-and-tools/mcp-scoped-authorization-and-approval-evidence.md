---
type: "Retrieval And Tools"
title: "MCP Scoped Authorization And Approval Evidence"
description: "MCP scoped authorization and approval evidence records who or what may call a tool, for which resource, under which task scope, and with which approved payload."
tags: ["retrieval-and-tools"]
---

# MCP Scoped Authorization And Approval Evidence

## Current Understanding

MCP scoped authorization and approval evidence records who or what may call a tool, for which resource, under which task scope, and with which approved payload. This keeps tool access as an enforceable control-plane decision rather than a prompt-level preference.

The [July 30 leaf update watch source](../../../raw/processed/2026-07-30/ai-dev-wiki-leaf-update-watch-2026-07-30T210230-0400.json) adds resource-scoped MCP authorization, read/write separation, and exact-payload approval evidence. The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds sandbox permission evidence for read, write, execute, and iterate workflows. Broad MCP protocol and vendor coverage remains upstream-owned; this page owns the local authorization evidence contract.

## Practice Boundaries

- Scope MCP authorization by resource, task, user or agent identity, capability, and read/write effect before the tool is callable.
- Store the policy decision, approver or policy owner, exact proposed payload, approved scope, and execution result for high-impact calls.
- Block execution when the executed payload, target resource, data class, or side-effect scope differs from the approved package.
- Treat read-only, write, execute, and external-system tools as separate permission classes even when they share one MCP server.
- Keep broad MCP protocol lifecycle and server catalogs upstream; keep local notes focused on authorization, approval, audit, and workflow impact.

## Authoritative Sources

- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [July 30 leaf update watch source](../../../raw/processed/2026-07-30/ai-dev-wiki-leaf-update-watch-2026-07-30T210230-0400.json)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [progressive MCP tool discovery](progressive-mcp-tool-discovery.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-30 from public evidence about MCP resource scoping, read/write capability separation, sandbox permission classes, and approval-to-execution payload matching.
