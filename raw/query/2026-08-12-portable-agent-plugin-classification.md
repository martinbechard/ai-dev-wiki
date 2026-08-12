# Query Fragment: Portable Agent Plugin Classification

## Query Asked

Is portable Agent Plugin packaging really an MCP concept?

## Answer Summary

No. Agent Plugins is a packaging and cross-client interoperability concept. Agent Plugins 1.0 defines two portable component types: Agent Skills and MCP servers. MCP is therefore one component inside the package rather than the parent concept. Client-specific extensions, installation, distribution, permissions, authentication, and user experience sit outside the portable core.

## Wiki Pages Consulted

- `docs/wiki/retrieval-and-tools/remote-mcp-skill-discovery-and-governance.md`
- `docs/wiki/retrieval-and-tools/progressive-mcp-tool-discovery.md`
- `docs/wiki/retrieval-and-tools/tool-call-and-mcp-governance.md`
- `docs/wiki/governance-and-risk/sensitive-data-and-supply-chain-controls.md`

## Authoritative Sources Consulted

- [Agent Plugins overview](https://agent-plugins.org/)
- [Agent Plugins Specification 1.0.0](https://agent-plugins.org/specification)
- [OpenAI plugin documentation](https://learn.chatgpt.com/docs/plugins)
- [OpenAI plugin packaging documentation](https://developers.openai.com/plugins/build/plugins)

## Durable Concepts Detected

- Portable agent capability packaging
- Cross-client discovery and interoperability
- Skills as workflow instructions
- MCP servers as tool and data interfaces
- Client extension namespaces for non-portable behavior
- Plugin supply-chain, permission, credential, and execution governance

## Candidate Wiki Destinations

- Create `docs/wiki/retrieval-and-tools/portable-agent-plugin-packaging-and-governance.md` as the downstream practice leaf.
- Keep broad Agent Plugins specification and ecosystem ownership in the upstream AI wiki.
- Retain MCP-specific loading and authorization details in the existing MCP leaves.

## Existing Pages To Link

- `docs/wiki/retrieval-and-tools/remote-mcp-skill-discovery-and-governance.md`
- `docs/wiki/retrieval-and-tools/progressive-mcp-tool-discovery.md`
- `docs/wiki/retrieval-and-tools/tool-call-and-mcp-governance.md`
- `docs/wiki/governance-and-risk/sensitive-data-and-supply-chain-controls.md`
- `docs/wiki/adoption-and-operating-model/portable-agent-skills-and-runbooks.md`

## Open Questions

- Should the upstream AI wiki create the broad Agent Plugins specification entity page before the downstream governance leaf links to it?
- Which Codex-specific plugin components are portable under Agent Plugins 1.0 and which remain OpenAI client extensions?

## Privacy And Sensitivity Notes

This fragment uses only public specification, documentation, and repository wiki sources. It contains no private or sensitive information.

## Ingest Rationale

The current wiki folds portable plugin packaging into an MCP-specific leaf. The specification establishes Agent Plugins as a broader package boundary spanning skills, MCP servers, and client extensions, so a separate downstream leaf would make the classification and governance guidance reusable without treating the entire concept as MCP.
