# Source Reconciliation And Routing

## Current Understanding

Source reconciliation keeps the wiki aligned with authoritative evidence. The wiki is a synthesis layer, so it follows the repository authority order: code and tests describe actual behavior, specifications describe intended behavior, procedures describe workflow obligations, backlog records describe tracked work, architecture and plans describe design intent, and wiki pages summarize those sources.

During source ingest, recurring concepts and aliases should be normalized into the best durable page when evidence supports that mapping. Source-specific framing stays attributed to the source, while unresolved contradictions become open questions instead of false consensus.

Federation is part of routing. The upstream AI wiki owns broad ecosystem entities such as companies, models, products, agentic frameworks, MCP servers, general developer tools, and broad techniques. This downstream wiki owns local AI-assisted development practice, workflow, governance, evaluation, implementation, and adoption lenses.

## Practice Boundaries

- Read authoritative source files before updating wiki understanding.
- Use higher-priority sources when wiki prose conflicts with code, tests, specifications, procedures, backlog records, architecture, or plans.
- Preserve unresolved conflicts in Open Questions.
- Normalize aliases into existing durable leaves when they refer to the same local practice concept.
- Link or route upstream-owned ecosystem entities through [federation.md](../federation.md) instead of creating duplicate local encyclopedia leaves.
- Keep local leaves focused on downstream practice, workflow, governance, evaluation, implementation, and adoption implications.

## Authoritative Sources

- [schema.md](../schema.md)
- [federation.md](../federation.md)
- [topic-index.md](../topic-index.md)
- [AI Dev Wiki Raw Project-Wiki Monitor automation](/Users/martinbechard/.codex/automations/ai-dev-wiki-raw-project-wiki-monitor/automation.toml)
- [project-wiki source priority reference](/Users/martinbechard/.codex/skills/project-wiki/references/source-priority.md)
- [upstream AI wiki topic index](../../../upstream-ai-wiki/topic-index.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [source-workflows](index.md)
- [clipping and raw intake](clipping-and-raw-intake.md)
- [raw project-wiki monitor](raw-project-wiki-monitor.md)
- [automated update feeds](automated-update-feeds.md)
- [federation.md](../federation.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to separate authority order, source conflict handling, synonym normalization, and federation routing from the broader source-workflows hub.
