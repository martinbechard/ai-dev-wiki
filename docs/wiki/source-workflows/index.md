# Source Workflows

## Current Understanding

Source workflows cover how this wiki captures, stores, ingests, reconciles, and archives source material. The steady-state flow is source first: public collectors and human clippings create raw artifacts, ingest reads each artifact, durable leaves and digests are updated, and fully processed artifacts move to processed storage.

This topic owns raw source handling, clipping intake, source reconciliation, synonym factoring, conflict notes, digest maintenance, and feed automation. It also owns routing rules for one-way federation, so upstream-owned ecosystem updates are not duplicated locally.

## Source Workflow Leaf Pages

- [automated-update-feeds.md](automated-update-feeds.md) records the overall source-first automation model and approved feed topics.
- [public-topic-news-collector.md](public-topic-news-collector.md) records the raw-only public topic collector for AI-assisted development practice updates.
- [leaf-update-watch.md](leaf-update-watch.md) records the raw-only public update check for existing durable local leaves.
- [raw-project-wiki-monitor.md](raw-project-wiki-monitor.md) records the clipping move, raw ingest, durable leaf update, digest update, lint, and processed-source move workflow.
- [clipping-and-raw-intake.md](clipping-and-raw-intake.md) records where human-saved source notes, unprocessed raw artifacts, and fully processed raw artifacts belong.
- [source-reconciliation-and-routing.md](source-reconciliation-and-routing.md) records authority order, conflict handling, synonym normalization, and federation routing during source ingest.

## Authoritative Sources

- [Folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md)
- [topic-index.md](../topic-index.md)
- [schema.md](../schema.md)
- [federation.md](../federation.md)
- Target environment automation record for AI Dev Wiki Topic News Collector.
- Target environment automation record for AI Dev Wiki Leaf Update Watch.
- Target environment automation record for AI Dev Wiki Raw Project-Wiki Monitor.

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [digests](../digests/index.md)
- [context-architecture](../context-architecture/index.md)
- [federation.md](../federation.md)
- [governance-and-risk](../governance-and-risk/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 as the owner for raw source, clipping, ingest, and automation workflows.
- Split on 2026-06-23 into durable leaves for update feeds, collector behavior, leaf watches, raw ingest, clipping intake, and source reconciliation.
