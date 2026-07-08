---
type: "Source Workflow"
title: "Leaf Update Watch"
description: "The leaf update watch is a raw-only automation for public updates about existing durable local wiki leaves."
tags: ["source-workflows"]
---

# Leaf Update Watch

## Current Understanding

The leaf update watch is a raw-only automation for public updates about existing durable local wiki leaves. It builds a leaf universe from the accepted local topic roots, excludes hubs and maintenance pages, uses the relative wiki page path as the stable leaf id, and checks new or oldest-unchecked leaves first.

The watch searches with public topic names, aliases, and source URLs rather than whole local wiki pages. It uses only public web sources, applies a seven-day visible publication or update window, routes broad upstream-owned entity updates through [federation.md](../federation.md), and saves qualifying findings as structured raw JSON artifacts under [raw](../../../raw). It does not edit wiki pages and does not save scanner output under [raw/processed](../../../raw/processed).

The automation maintains a deterministic local batch ledger when it runs. The ledger tracks checked leaves, source URLs, result status, qualified updates, and follow-up notes so future runs can sweep durable leaves without turning the wiki itself into the scan payload.

## Practice Boundaries

- Select durable local leaves, not folder hubs or maintenance pages, as the update-check unit.
- Check new or previously unchecked leaves before older checked leaves.
- Break ties with stable relative path sorting.
- Use public names, aliases, and source URLs rather than private local page text when searching.
- Save qualifying results as raw source artifacts for normal ingest.
- Leave wiki edits to [raw-project-wiki-monitor.md](raw-project-wiki-monitor.md) and human-directed ingest work.

## Authoritative Sources

- Target environment automation record for AI Dev Wiki Leaf Update Watch.
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
- [public topic news collector](public-topic-news-collector.md)
- [raw project-wiki monitor](raw-project-wiki-monitor.md)
- [source reconciliation and routing](source-reconciliation-and-routing.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to separate durable-leaf public update checks from the broader automated-update-feeds page.
