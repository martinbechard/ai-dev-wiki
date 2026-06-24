# Rules And Knowledge Layers

## Current Understanding

Rules and knowledge are separate context layers. The rules layer holds durable conventions that govern work across tasks, while the knowledge layer holds stable project facts that agents repeatedly need but should not rederive in every session.

Rules include build conventions, design-system standards, reusable component catalogs, coding standards, testing expectations, review standards, and tool expectations. Knowledge includes stable technical facts, integration notes, architecture facts, and other project truths that should guide work without becoming live instructions for every task.

## Practice Boundaries

- Put durable conventions in the rules layer when they apply across tasks.
- Put stable project facts in the knowledge layer when repeated rediscovery would waste context or cause drift.
- Keep rules actionable and scoped so agents can follow them during editing or review.
- Keep knowledge factual and source-backed so it supports orientation without becoming a hidden command layer.
- Link from the router to the relevant layer instead of duplicating the same guidance in multiple files.

## Authoritative Sources

- [Folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Context router and knowledge layers](context-router-and-knowledge-layers.md)

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
