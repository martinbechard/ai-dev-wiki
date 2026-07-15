---
type: "Retrieval And Tools"
title: "RAG Tools And MCP Practice"
description: "Retrieval and tool use turn an AI system from a text generator into a governed application component."
tags: ["retrieval-and-tools"]
---

# RAG Tools And MCP Practice

## Current Understanding

Retrieval and tool use turn an AI system from a text generator into a governed application component. The local pattern separates fact supply from action execution: retrieval, attachments, and dynamic context tools supply evidence; client action tools and MCP servers perform typed operations outside the model.

RAG for code and documents needs exact paths, symbols, chunks, reranking, and runtime truth in addition to semantic similarity. MCP is treated here as a governed access practice, while individual MCP servers and the protocol's broad ecosystem coverage belong to the upstream [AI wiki MCP server index](../../../upstream-ai-wiki/mcp-servers/index.md) and [techniques index](../../../upstream-ai-wiki/techniques/index.md).

The detailed practice leaves split the domain by maintenance path. [Code retrieval evidence patterns](code-retrieval-evidence-patterns.md) owns repository evidence selection, [RAG provenance ranking and chunking](rag-provenance-ranking-and-chunking.md) owns document retrieval quality and source boundaries, and [tool call and MCP governance](tool-call-and-mcp-governance.md) owns typed action execution.

The [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json) reinforces the split. Search, facets, and targeted reads reduce context noise before answer generation, while MCP tool metadata and action tools need separate governance because they can influence what the agent does.

The [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) adds a service-delivery MCP example and a searchable-workspace retrieval example. Local practice should keep public-sector MCP, project search, and work-artifact search routed through the detailed leaves: retrieval supplies attributed evidence, while MCP tools need identity, transport, read/write scope, local testing, and audit controls before action.

## Practice Boundaries

- Use retrieval to assemble evidence before asking the model for a factual or code-aware answer.
- Route repository evidence, RAG quality, and action execution to separate leaves when a page needs operational detail.
- Keep retrieved evidence from becoming hidden instruction.
- Keep action tools typed, logged, validated, and executed outside the model.
- Use retrieval controls to narrow evidence and tool controls to govern action; do not let either surface become hidden authority.
- Route searchable work artifacts through evidence verification and route service-delivery MCP tools through identity, transport, read/write scope, testing, and audit controls.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [OWASP LLM vulnerabilities source](../../../raw/processed/OWASP's Top 10 Ways to Attack LLMs AI Vulnerabilities Exposed.md)
- [federation.md](../federation.md)
- [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [context-architecture](../context-architecture/index.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [code retrieval evidence patterns](code-retrieval-evidence-patterns.md)
- [RAG provenance ranking and chunking](rag-provenance-ranking-and-chunking.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on RAG, embeddings, vector databases, chunking, reranking, tool calls, and MCP.
- Maintained on 2026-06-23 as the retrieval and tool overview after splitting detailed practice leaves.
- Maintained on 2026-07-01 with search-first retrieval, faceted scoping, and MCP metadata governance boundaries.
- Maintained on 2026-07-14 with searchable work artifacts and service-delivery MCP routing to detailed evidence and action-control leaves.
