---
type: "Retrieval And Tools"
title: "Portable Agent Plugin Packaging And Governance"
description: "Portable agent plugin packaging governs how reusable skills, MCP servers, manifests, and client-specific extensions travel across agent clients."
tags: ["retrieval-and-tools"]
---

# Portable Agent Plugin Packaging And Governance

## Current Understanding

Portable agent plugin packaging governs how reusable skills, MCP servers, manifests, and client-specific extensions travel across agent clients. The [portable agent plugin classification query source](../../../raw/processed/query/2026-08-12-portable-agent-plugin-classification.md) records the local classification rule: Agent Plugins packaging is broader than MCP. MCP servers are one portable component inside the package, while skills, manifests, installation, distribution, permissions, authentication, and client-specific extensions need their own review.

The August 12 raw sources add public adoption evidence without moving broad standard ownership into this wiki. The [topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json) and [leaf update watch source](../../../raw/processed/2026-08-12/ai-dev-wiki-leaf-update-watch-2026-08-12T210257-0400.json) record Agent Plugins support across several client surfaces, with shared packages, plugin manifests, skills, MCP server configuration, managed settings, allowlists, marketplace installation, and client-specific namespaces. Broad Agent Plugins, GitHub Copilot, VS Code, Google, Vercel, OpenAI, Microsoft, AWS, and Anysphere coverage belongs upstream; locally, the practice is to review the package as a capability bundle before it enters a development workflow.

The August 13 raw sources add follow-on adoption and supply-chain evidence. The [topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json) and [leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json) reinforce that portable packages need manifest review, managed availability policy, MCP allowlist evidence, client-specific namespace checks, and repository provenance before bundled skills or MCP servers become team defaults. Broad vendor and product coverage routes upstream; locally, repository-hosted skills and MCP declarations remain governed capability bundles.

Portable packages should not erase artifact boundaries. [Portable agent skills and runbooks](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md) owns reusable procedure design; [remote MCP skill discovery and governance](remote-mcp-skill-discovery-and-governance.md) owns skills discovered through MCP; [tool call and MCP governance](tool-call-and-mcp-governance.md) owns runtime tool authorization; this page owns the packaging review that binds those components together.

## Practice Boundaries

- Treat the plugin manifest as a governed capability declaration, not only install metadata.
- Review bundled skills, MCP server declarations, client-specific extension folders, marketplace source, managed settings, and allowlist requirements before installation.
- Keep portable components separate from client-specific behavior so teams know which parts should work across clients and which parts depend on one agent surface.
- Require ownership, version, source registry, compatibility target, credential assumptions, permission classes, and rollback path before approving a shared package.
- Do not treat an Agent Plugins package as an MCP-only artifact; route MCP server details through MCP governance and skill procedure details through portable skill governance.
- Preserve client enforcement evidence when package availability, MCP allowlists, or permission-bypass settings differ across IDE, CLI, app, or cloud-agent surfaces.
- Treat repository-hosted skills, plugin packages, and MCP server declarations as supply-chain inputs until provenance, namespace, managed-availability policy, and allowlist evidence are recorded.

## Authoritative Sources

- [portable agent plugin classification query source](../../../raw/processed/query/2026-08-12-portable-agent-plugin-classification.md)
- [August 12 topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json)
- [August 12 leaf update watch source](../../../raw/processed/2026-08-12/ai-dev-wiki-leaf-update-watch-2026-08-12T210257-0400.json)
- [August 13 topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json)
- [August 13 leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json)
- [remote MCP skill discovery and governance](remote-mcp-skill-discovery-and-governance.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [portable agent skills and runbooks](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md)
- [federation.md](../federation.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [remote MCP skill discovery and governance](remote-mcp-skill-discovery-and-governance.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md)
- [portable agent skills and runbooks](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md)

## Open Questions

- Should the upstream AI wiki create a broad Agent Plugins specification entity page so this local practice leaf can link to an upstream owner?

## Maintenance Notes

- Created on 2026-08-12 from the portable Agent Plugins classification query and August 12 public Agent Plugins adoption evidence.
- Maintained on 2026-08-13 with portable package policy, repository-skill provenance, MCP allowlist, and client-namespace review evidence.
