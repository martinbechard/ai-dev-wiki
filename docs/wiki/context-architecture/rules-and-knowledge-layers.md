---
type: "Context Architecture"
title: "Rules And Knowledge Layers"
description: "Rules and knowledge are separate context layers."
tags: ["context-architecture"]
---

# Rules And Knowledge Layers

## Current Understanding

Rules and knowledge are separate context layers. The rules layer holds durable conventions that govern work across tasks, while the knowledge layer holds stable project facts that agents repeatedly need but should not rederive in every session.

Rules include build conventions, design-system standards, reusable component catalogs, coding standards, testing expectations, review standards, and tool expectations. Knowledge includes stable technical facts, integration notes, architecture facts, and other project truths that should guide work without becoming live instructions for every task.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) reinforce that unknown local frameworks need layered teaching. Identity, conventions, and workflow rules belong in durable instruction surfaces; current API shape, reference implementations, and diagnostic facts belong in knowledge or retrieval layers. Skills and MCP servers can expose procedures or current API evidence, but they should not collapse rule, knowledge, and tool authority into one prompt.

The [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json) adds company-context evidence: agents need a current and permission-aware knowledge layer for org facts, not only a static rules layer. Rules define how the agent should act; retrievable knowledge supplies the facts and examples that may change independently.

The [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json) adds context-layer evidence for agent systems. Retrieval, semantic definitions, entity identity, lineage, policy enforcement, and decision memory should remain separate from rules so agents can use governed meaning without converting every retrieved fact into an instruction.

## Practice Boundaries

- Put durable conventions in the rules layer when they apply across tasks.
- Put stable project facts in the knowledge layer when repeated rediscovery would waste context or cause drift.
- Keep rules actionable and scoped so agents can follow them during editing or review.
- Keep knowledge factual and source-backed so it supports orientation without becoming a hidden command layer.
- Link from the router to the relevant layer instead of duplicating the same guidance in multiple files.
- Keep procedural skills, current API references, and diagnostic examples in their own layers so a task can load the missing evidence without turning source material into global instructions.
- Keep company context permission-aware and refreshable when it feeds agent retrieval or reusable memory.
- Separate governed meaning, lineage, and decision memory from executable rules; the knowledge layer informs decisions while the rules layer governs allowed behavior.
- Preserve policy and provenance metadata with retrieved business or project context so agents can explain why the context was valid for the task.

## Authoritative Sources

- [Folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Context router and knowledge layers](context-router-and-knowledge-layers.md)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json)
- [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [thin context router](thin-context-router.md)
- [lifespan organized documentation](lifespan-organized-documentation.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on durable rules, project facts, reusable procedures, and context-aware guidance.
- Maintained on 2026-06-25 with layered teaching guidance for proprietary or unfamiliar project APIs.
- Maintained on 2026-06-29 with permission-aware company context as a refreshable knowledge layer.
- Maintained on 2026-07-03 with governed meaning, lineage, decision memory, policy metadata, and provenance as knowledge-layer concerns.
