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

The [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json) reinforces wiki memory as an ingest output. Raw artifacts should become compact, source-backed durable leaves and item-level digest entries rather than repeated raw chunks, while source files stay available as provenance after processing.

The July 10 raw artifacts reinforce item-level ingest. The [topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json) carries independent practice implications for MCP identity, harness loops, task-scoped access, performance evals, review workflow, requirement traceability, trajectory diagnosis, and harness taxonomies. The [leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json) carries leaf-targeted follow-up notes and exclusions. The monitor should synthesize those as durable leaves and item-level digest entries, not as one batch summary.

The July 25 raw artifacts reinforce source routing and evidence quality. The [topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json) includes upstream-owned companies, products, standards, models, and MCP servers, while the [leaf update watch source](../../../raw/processed/2026-07-25/ai-dev-wiki-leaf-update-watch-2026-07-25T210250-0400.json) maps public evidence to existing local leaves. The monitor should keep broad entity background upstream, preserve sponsored-source caution, and synthesize only the local practice implications into durable leaves and item-level digest entries.

The September 3 raw artifacts reinforce high-volume item-level routing:

- The [leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json) and [topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json) contain many upstream-owned products, providers, standards, and protocols.
- The monitor should route their local practice implications into durable leaves and item-level digests instead of preserving batch-shaped wiki prose.

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
- Keep raw-source ingest focused on compact synthesized wiki memory instead of copying raw collector summaries into topic pages.
- Preserve processed artifacts as provenance after item-level leaves and digests hold the reusable understanding.
- Treat collector runs with many unrelated findings as multiple item-level practice updates rather than one digest or page-change batch.
- Preserve source-quality labels such as sponsored or vendor-positioned evidence when those labels affect how strongly a local operating rule should rely on the source.
- For high-volume collector pairs, group synthesis by durable practice implication and independently changing digest item, not by raw artifact, provider, protocol, or source sweep.

## Authoritative Sources

- Target environment automation record for AI Dev Wiki Raw Project-Wiki Monitor.
- Target environment automation memory for AI Dev Wiki Raw Project-Wiki Monitor.
- [automated update feeds](automated-update-feeds.md)
- [clipping and raw intake](clipping-and-raw-intake.md)
- [source reconciliation and routing](source-reconciliation-and-routing.md)
- [digests](../digests/index.md)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json)
- [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json)
- [July 10 leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json)
- [July 25 topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json)
- [July 25 leaf update watch source](../../../raw/processed/2026-07-25/ai-dev-wiki-leaf-update-watch-2026-07-25T210250-0400.json)
- [September 3 leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json)
- [September 3 topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json)

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
- Maintained on 2026-07-05 with compact wiki-memory synthesis and processed-artifact provenance signals.
- Maintained on 2026-07-10 with item-level ingest boundaries for high-volume collector and leaf-watch artifacts.
- Maintained on 2026-07-25 with upstream entity routing, sponsored-source caution, and item-level synthesis for topic-news and leaf-watch artifacts.
- Maintained on 2026-09-03 with high-volume item-level routing across ownership, identity, memory, tool audit, runtime control, worktree isolation, evaluation, and governed deployment practice implications.
