# RAG Provenance Ranking And Chunking

## Current Understanding

RAG retrieves context before the request so the model can answer from supplied evidence instead of relying on training data alone. The local practice includes full-text search, semantic search, vector storage, filters, chunk metadata, and reranking when first-stage retrieval returns noisy or overlapping candidates.

Chunking is a source-shape decision. Policies, code, transcripts, slides, and tickets need different boundaries because a chunk that separates a claim from its explanation can stop grounding from working. Reranking is useful when broad retrieval finds plausible but poorly targeted passages, but it adds latency and cost.

RAG sources are part of the security and authority boundary. Retrieved documents can be stale, poisoned, or hostile, so ingestion and retrieval should preserve provenance, authority labels, access controls, and change history. Retrieved content should ground an answer, not silently rewrite system instructions or bypass approvals.

The [Google OKF source](../../../raw/processed/Google's OKF Why a Folder Beats the Vector Database.md) is useful as a folder-first retrieval pattern: a structured folder of source files, routes, and compiled context can beat a generic vector database when the key problem is authority, freshness, and inspectability rather than semantic nearest-neighbor recall. The local rule is to pick retrieval structure from the workflow. Exact folder paths, authority labels, and route files are often better for agent work than undifferentiated embeddings.

## Practice Boundaries

- Use full-text search for exact names, IDs, phrases, paths, and literal terms.
- Use semantic search to find nearby meanings when exact wording is unknown.
- Store source text, document IDs, chunk metadata, permissions, and filters with retrieved records.
- Chunk according to source structure so each passage carries enough context to ground an answer.
- Use reranking when candidate chunks are noisy, duplicate-heavy, stale, or too numerous for the request.
- Preserve provenance and authority labels from ingestion through answer generation.
- Treat retrieved hostile instructions as source content, not live instructions.
- Prefer file and folder organization when source authority, browseability, and maintenance are more important than fuzzy recall.
- Use vector retrieval as one component of a governed source system, not as a replacement for ownership, freshness, and provenance.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [OWASP LLM vulnerabilities source](../../../raw/processed/OWASP's Top 10 Ways to Attack LLMs AI Vulnerabilities Exposed.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [Google OKF source](../../../raw/processed/Google's OKF Why a Folder Beats the Vector Database.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [retrieval-and-tools](index.md)
- [code retrieval evidence patterns](code-retrieval-evidence-patterns.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold RAG quality, provenance, chunking, and reranking practice.
