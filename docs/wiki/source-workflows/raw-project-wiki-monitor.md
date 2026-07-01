---
type: "Source Workflow"
title: "Raw Project-Wiki Monitor"
description: "The raw project-wiki monitor is the ingest automation for this wiki."
tags: ["source-workflows"]
---

# Raw Project-Wiki Monitor

## Current Understanding

The raw project-wiki monitor is the ingest automation for this wiki. It first checks [Clippings](../../../Clippings) for human-saved source files, moves eligible clipping files into [raw](../../../raw) without overwriting existing files, and then checks [raw](../../../raw) for unprocessed source artifacts outside [raw/processed](../../../raw/processed).

When unprocessed raw files exist, the monitor follows the project-wiki raw source ingest workflow: read the source, extract recurring local ideas and entities, search the federated upstream topic index before creating local entity leaves, update durable local leaves under accepted topic roots, update monthly digests, run project-wiki lint, move only fully processed sources into processed storage, and report changed leaves, moved files, lint status, and blockers.

The monitor is the automation layer allowed to refresh docs/wiki pages after raw source processing. Public collectors and leaf watches remain raw-only.

The [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) reinforces that raw ingest should preserve knowledge packages as evidence before synthesis. External code, tests, traces, vendor claims, and public research should be read as source material, mapped into durable local leaves, and verified against the wiki contract before the source is moved to processed storage.

## Practice Boundaries

- Ignore hidden filesystem metadata and keep clipping moves collision-safe.
- Do not overwrite an existing raw file during clipping intake.
- Leave incomplete or blocked raw files outside processed storage.
- Normalize synonyms and aliases into the best durable page when source evidence supports that mapping.
- Preserve unresolved source conflicts as open questions.
- Update digests only after durable leaves hold the detailed source-backed understanding.
- Run project-wiki lint before considering ingest complete.
- Report moved clippings, raw files found, changed leaves, digest updates, processed-source moves, lint result, and blockers.
- Keep knowledge-package provenance visible when source material contains external agent work, traces, or claims about local practice.

## Authoritative Sources

- [AI Dev Wiki Raw Project-Wiki Monitor automation](/Users/martinbechard/.codex/automations/ai-dev-wiki-raw-project-wiki-monitor/automation.toml)
- [AI Dev Wiki Raw Project-Wiki Monitor memory](/Users/martinbechard/.codex/automations/ai-dev-wiki-raw-project-wiki-monitor/memory.md)
- [automated update feeds](automated-update-feeds.md)
- [clipping and raw intake](clipping-and-raw-intake.md)
- [source reconciliation and routing](source-reconciliation-and-routing.md)
- [digests](../digests/index.md)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)

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
- [leaf update watch](leaf-update-watch.md)
- [digests](../digests/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to separate clipping moves, raw ingest, durable leaf updates, digest updates, lint, and processed-source moves from the broader automated-update-feeds page.
- Maintained on 2026-06-26 with knowledge-package provenance as an ingest concern.
