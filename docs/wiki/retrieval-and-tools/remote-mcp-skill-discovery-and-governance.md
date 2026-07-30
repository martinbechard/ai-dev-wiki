---
type: "Retrieval And Tools"
title: "Remote MCP Skill Discovery And Governance"
description: "Remote MCP skill discovery treats discovered skills as governed tool packages, not just extra context."
tags: ["retrieval-and-tools"]
---

# Remote MCP Skill Discovery And Governance

## Current Understanding

Remote MCP skill discovery treats discovered skills as governed tool packages, not just extra context. The [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) records progressive skill loading from MCP servers, with package provenance, archive bounds, approval defaults, central governance, and remote-content trust boundaries.

Broad Model Context Protocol and framework background belongs upstream. This page owns the local downstream rule: a discovered skill can change what an agent knows how to do, so its publisher, package boundary, allowed tools, approval defaults, diagnostics, and policy owner need review before use.

The [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json) adds authenticated retrieval and package-limit evidence. Remote skills distributed as Markdown or archives should have publisher review, authenticated transport, archive size and file-count limits, blocked script execution, central publication ownership, approval defaults, and diagnostics before agents load them from MCP servers.

## Practice Boundaries

- Treat discovered skills as code-adjacent supply-chain inputs.
- Review publisher, package boundary, archive limits, allowed tools, and approval defaults before runtime use.
- Keep central policy ownership separate from the agent that discovers the skill.
- Require diagnostics and audit evidence when a remote skill changes available tools, actions, or context.
- Enforce package-size, file-count, script-execution, transport-authentication, and approval-default limits before remote skills become active.

## Authoritative Sources

- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json)
- [progressive MCP tool discovery](progressive-mcp-tool-discovery.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [upstream MCP server index](../../../upstream-ai-wiki/mcp-servers/index.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [progressive MCP tool discovery](progressive-mcp-tool-discovery.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-28 from July 28 raw evidence about remotely discovered MCP skills, package boundaries, approval defaults, diagnostics, and central governance.
- Maintained on 2026-07-29 with authenticated retrieval, archive-limit, blocked-script, central-publication, approval-default, and diagnostic guidance.
