---
type: "Context Architecture"
title: "Compiled Wiki And Structured Memory"
description: "Context systems need a clear source of truth and a clear compiled view."
tags: ["context-architecture"]
---

# Compiled Wiki And Structured Memory

## Current Understanding

Context systems need a clear source of truth and a clear compiled view. The [Karpathy wiki versus OpenBrain source](../../../raw/processed/Karpathy's Wiki vs. Open Brain. One Fails When You Need It Most..md) contrasts prose-first wikis with structured memory stores: wikis are useful for browsable synthesis and deep topic work, while structured stores are better for high-volume, multi-agent, operational facts that need precise queries and auditability.

The local rule is that a wiki should compile understanding from authoritative sources rather than become the authoritative store for every fast-changing fact. For raw-source ingest, source artifacts remain provenance, durable leaves hold synthesized practice, and digests point readers to the leaves. For high-volume operational memory, a structured store can be the source of truth while generated wiki pages act as a hot reference layer.

The [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json) adds two compatible public signals. Company context should be durable, current, retrievable, and access-controlled instead of stuffed into every prompt, and structured Markdown wikis can act as reusable memory across coding agents. Locally, that supports a compiled wiki as a governed context layer that agents can reload, while keeping source authority and freshness checks outside the prose itself.

The [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json) adds a wiki-memory signal. File-based wiki memory works best when raw sources are synthesized into compact, persistent, inspectable knowledge that agents can reload over time. The local boundary is that wiki memory is maintained compiled context: it improves reuse and reviewability, but it still depends on source provenance, freshness checks, and periodic correction.

## Practice Boundaries

- Use durable wiki leaves for stable synthesized practice, decisions, and cross-source understanding.
- Use structured storage for high-volume operational facts, records, task state, and multi-agent query surfaces.
- Treat generated or compiled wiki pages as views unless the project explicitly designates them as source authority.
- Preserve provenance so stale prose can be traced back to raw facts or corrected by regenerating from the authoritative store.
- Record contradictions and unresolved ownership in Open Questions instead of smoothing them into confident prose.
- Keep access control and freshness visible when compiled wiki pages or structured memory are used as company context for agents.
- Treat reusable agent memory as a maintained source-backed layer, not as unreviewed prompt accumulation.
- Prefer compact, source-backed, inspectable wiki memory for reusable agent knowledge rather than repeated raw chunk stuffing.
- Refresh or correct wiki memory from provenance when source facts drift or a later run exposes a contradiction.

## Authoritative Sources

- [Karpathy wiki versus OpenBrain source](../../../raw/processed/Karpathy's Wiki vs. Open Brain. One Fails When You Need It Most..md)
- [context router and knowledge layers](context-router-and-knowledge-layers.md)
- [source workflows](../source-workflows/index.md)
- [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json)
- [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json)

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
- Maintained on 2026-06-29 with durable company-context and structured Markdown wiki memory signals.
- Maintained on 2026-07-02 with file-based wiki memory, source synthesis, and freshness-boundary guidance.
