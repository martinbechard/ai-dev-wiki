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

The [July 31 topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json) adds two governed-MCP patterns. One pattern registers MCP servers through a central admin review flow with runtime blocking, declared-tool snapshots, and security telemetry. The other adds OAuth-mediated MCP access with resource-bound tokens and callback-domain allow lists. Broad Microsoft, UiPath, MCP, GitHub Copilot CLI, Claude Code, and Visual Studio Code background stays upstream-owned; locally, these sources strengthen the approval-evidence contract for registration, authorization, and runtime tool visibility.

## Practice Boundaries

- Scope MCP authorization by resource, task, user or agent identity, capability, and read/write effect before the tool is callable.
- Store the policy decision, approver or policy owner, exact proposed payload, approved scope, and execution result for high-impact calls.
- Block execution when the executed payload, target resource, data class, or side-effect scope differs from the approved package.
- Treat read-only, write, execute, and external-system tools as separate permission classes even when they share one MCP server.
- Require server-registration evidence, declared tool snapshots, runtime block status, OAuth scope, resource-bound token behavior, and callback-domain constraints before treating a remote MCP surface as approved for development workflows.
- Treat agent-scored tool-schema evaluation as a data-handling decision because schemas may be handed to a coding agent; deterministic schema checks and semantic scoring need separate evidence and review.
- Keep broad MCP protocol lifecycle and server catalogs upstream; keep local notes focused on authorization, approval, audit, and workflow impact.

## Authoritative Sources

- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [July 30 leaf update watch source](../../../raw/processed/2026-07-30/ai-dev-wiki-leaf-update-watch-2026-07-30T210230-0400.json)
- [July 31 topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json)
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
- Maintained on 2026-07-31 with MCP registration review, runtime blocking, declared-tool snapshots, OAuth token scoping, callback-domain allow lists, and tool-schema evaluation boundaries.
