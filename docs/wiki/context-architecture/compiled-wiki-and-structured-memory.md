# Compiled Wiki And Structured Memory

## Current Understanding

Context systems need a clear source of truth and a clear compiled view. The [Karpathy wiki versus OpenBrain source](../../../raw/processed/Karpathy's Wiki vs. Open Brain. One Fails When You Need It Most..md) contrasts prose-first wikis with structured memory stores: wikis are useful for browsable synthesis and deep topic work, while structured stores are better for high-volume, multi-agent, operational facts that need precise queries and auditability.

The local rule is that a wiki should compile understanding from authoritative sources rather than become the authoritative store for every fast-changing fact. For raw-source ingest, source artifacts remain provenance, durable leaves hold synthesized practice, and digests point readers to the leaves. For high-volume operational memory, a structured store can be the source of truth while generated wiki pages act as a hot reference layer.

## Practice Boundaries

- Use durable wiki leaves for stable synthesized practice, decisions, and cross-source understanding.
- Use structured storage for high-volume operational facts, records, task state, and multi-agent query surfaces.
- Treat generated or compiled wiki pages as views unless the project explicitly designates them as source authority.
- Preserve provenance so stale prose can be traced back to raw facts or corrected by regenerating from the authoritative store.
- Record contradictions and unresolved ownership in Open Questions instead of smoothing them into confident prose.

## Authoritative Sources

- [Karpathy wiki versus OpenBrain source](../../../raw/processed/Karpathy's Wiki vs. Open Brain. One Fails When You Need It Most..md)
- [context router and knowledge layers](context-router-and-knowledge-layers.md)
- [source workflows](../source-workflows/index.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [context router and knowledge layers](context-router-and-knowledge-layers.md)
- [lifespan organized documentation](lifespan-organized-documentation.md)
- [source workflows](../source-workflows/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold source-of-truth and compiled-view boundaries.
