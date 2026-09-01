---
type: "Context Architecture"
title: "Self-Service Analytics Context Governance"
description: "Self-service analytics agents are primarily a context-governance problem."
tags: ["context-architecture"]
---

# Self-Service Analytics Context Governance

## Current Understanding

Self-service analytics agents are primarily a context-governance problem. The [Anthropic analytics source](../../../raw/processed/How Anthropic enables self-service data analytics with Claude.md) argues that analytics errors usually come from concept-to-entity ambiguity, data staleness, and retrieval failure rather than from SQL generation alone. The local practice is to make governed definitions, metadata, source routing, skills, and evals part of the context architecture before letting an agent answer business questions.

For analytics-style workflows, the agent should be routed first to canonical metrics, semantic layers, lineage, curated reference docs, and business context. Query history can be useful raw material, but it should be distilled into maintained reference documents and reusable patterns instead of exposed as an unstructured source of truth.

The [August 31 leaf update watch source](../../../raw/processed/2026-08-31/ai-dev-wiki-leaf-update-watch-2026-08-31T210122-0400.json) adds Domo and Hyperight evidence that self-service analytics remains an operating-model and data-governance problem when AI is involved. AI-generated answers should inherit certified metrics, owner records, data-readiness checks, semantic layers, catalogs, role-based access, lineage, and auditability before they drive business decisions. Enterprise AI production should reuse stewardship and access-control workflows instead of treating agent context as separate from governed data practice.

## Practice Boundaries

- Prefer fewer governed datasets and metric definitions over many plausible near-duplicates.
- Keep metadata, grain, lineage, ownership, valid values, and freshness signals as first-class context.
- Use thin knowledge skills or routers to narrow the search space before the agent writes a query.
- Treat query corpora as curation input unless a specific query is authoritative evidence.
- Maintain analytics skills and reference docs alongside the models they describe.
- Validate analytics agents with snapshot-safe evals, domain gates, and telemetry that records skill version, model, and result.
- Require certified metric ownership, data-readiness checks, role-based access, lineage, and audit trails before AI-generated analytics answers drive decisions.
- Reuse stewardship, semantic-layer, catalog, and access-control workflows as agent context infrastructure instead of building parallel AI-only data governance.

## Authoritative Sources

- [Anthropic analytics source](../../../raw/processed/How Anthropic enables self-service data analytics with Claude.md)
- [context selection and compaction](context-selection-and-compaction.md)
- [judge grader boundaries](../verification-and-evals/judge-grader-boundaries.md)
- [August 31 leaf update watch source](../../../raw/processed/2026-08-31/ai-dev-wiki-leaf-update-watch-2026-08-31T210122-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [context router and knowledge layers](context-router-and-knowledge-layers.md)
- [RAG provenance ranking and chunking](../retrieval-and-tools/rag-provenance-ranking-and-chunking.md)
- [representative workflow calibration](../verification-and-evals/representative-workflow-calibration.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold analytics-specific context governance.
- Maintained on 2026-08-31 with certified-metric, ownership, semantic-layer, catalog, role-based-access, lineage, auditability, and stewardship evidence for AI-assisted analytics.
