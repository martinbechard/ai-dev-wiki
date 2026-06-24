# Public Topic News Collector

## Current Understanding

The public topic news collector is a raw-only automation for AI-assisted development practice updates. It searches approved local topic roots, uses only public web sources, applies a two-day visible publication or update window, and saves qualifying findings as structured raw JSON artifacts under [raw](../../../raw).

The collector does not edit wiki pages and does not save output under [raw/processed](../../../raw/processed). It respects the one-way federation boundary: broad ecosystem updates for companies, models, products, agentic frameworks, MCP servers, general developer tools, and broad techniques are upstream-owned, while this wiki keeps only the local practice implication or routing note.

The collector should include source URLs, visible dates, short factual summaries, relevance to AI-assisted development practice, named entities, upstream-owned entities, excluded candidates with reasons, and follow-up notes. It must not send private, proprietary, sensitive, PII, or company-internal local content to external services.

## Practice Boundaries

- Search public sources for practice-level updates across the accepted local topic roots.
- Use the two-day visible date window in the configured automation.
- Record exclusions for missing, ambiguous, future-dated, or boundary-only dates.
- Save qualifying results as raw source artifacts for normal ingest.
- Validate JSON artifacts when the automation creates them.
- Leave wiki edits to [raw-project-wiki-monitor.md](raw-project-wiki-monitor.md) and human-directed ingest work.

## Authoritative Sources

- [AI Dev Wiki Topic News Collector automation](/Users/martinbechard/.codex/automations/ai-dev-wiki-topic-news-collector/automation.toml)
- [automated update feeds](automated-update-feeds.md)
- [schema.md](../schema.md)
- [federation.md](../federation.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [source-workflows](index.md)
- [automated update feeds](automated-update-feeds.md)
- [leaf update watch](leaf-update-watch.md)
- [raw project-wiki monitor](raw-project-wiki-monitor.md)
- [source reconciliation and routing](source-reconciliation-and-routing.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to separate the raw-only public topic collector from the broader automated-update-feeds page.
