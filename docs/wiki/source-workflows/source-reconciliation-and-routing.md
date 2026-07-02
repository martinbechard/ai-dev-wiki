---
type: "Source Workflow"
title: "Source Reconciliation And Routing"
description: "Source reconciliation keeps the wiki aligned with authoritative evidence."
tags: ["source-workflows"]
---

# Source Reconciliation And Routing

## Current Understanding

Source reconciliation keeps the wiki aligned with authoritative evidence. The wiki is a synthesis layer, so it follows the repository authority order: code and tests describe actual behavior, specifications describe intended behavior, procedures describe workflow obligations, backlog records describe tracked work, architecture and plans describe design intent, and wiki pages summarize those sources.

During source ingest, recurring concepts and aliases should be normalized into the best durable page when evidence supports that mapping. Source-specific framing stays attributed to the source, while unresolved contradictions become open questions instead of false consensus.

Federation is part of routing. The upstream AI wiki owns broad ecosystem entities such as companies, models, products, agentic frameworks, MCP servers, general developer tools, and broad techniques. This downstream wiki owns local AI-assisted development practice, workflow, governance, evaluation, implementation, and adoption lenses.

The [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) adds a knowledge-package routing pattern. Knowledge-based pull requests treat external collaborator code, tests, and cleaned agent traces as evidence packages that the receiving project reviews, regenerates, and verifies under local policy. The local implication is to separate knowledge intake from implementation acceptance instead of merging foreign agent output directly.

The [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json) adds knowledge-source migration evidence. Search-rule, connector, locale, hidden-content, and CSV-import changes can alter what an agent can retrieve even when the visible workflow name stays the same. Source reconciliation should therefore preserve migration state, connector semantics, access scope, and excluded-source limitations when routing agent knowledge sources.

The [FastMCP research source](../../../raw/processed/project-wiki-research-2026-07-01-fastmcp.md) is routed as broad framework coverage for the upstream AI wiki and as a local governed-MCP practice signal. If the upstream wiki later creates a FastMCP entity leaf, local pages should link to that owner and keep only the downstream tool-surface curation guidance.

## Practice Boundaries

- Read authoritative source files before updating wiki understanding.
- Use higher-priority sources when wiki prose conflicts with code, tests, specifications, procedures, backlog records, architecture, or plans.
- Preserve unresolved conflicts in Open Questions.
- Normalize aliases into existing durable leaves when they refer to the same local practice concept.
- Link or route upstream-owned ecosystem entities through [federation.md](../federation.md) instead of creating duplicate local encyclopedia leaves.
- Keep local leaves focused on downstream practice, workflow, governance, evaluation, implementation, and adoption implications.
- Treat external agent artifacts as source evidence that must be routed, regenerated, and verified before becoming local implementation.
- Preserve connector semantics, locale scope, hidden-content handling, migration state, and source exclusions when ingesting knowledge-source changes.
- Route broad framework entities upstream while keeping only local practice implications in this wiki.

## Authoritative Sources

- [schema.md](../schema.md)
- [federation.md](../federation.md)
- [topic-index.md](../topic-index.md)
- [AI Dev Wiki Raw Project-Wiki Monitor automation](/Users/martinbechard/.codex/automations/ai-dev-wiki-raw-project-wiki-monitor/automation.toml)
- [project-wiki source priority reference](/Users/martinbechard/.codex/skills/project-wiki/references/source-priority.md)
- [upstream AI wiki topic index](../../../upstream-ai-wiki/topic-index.md)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json)
- [FastMCP research source](../../../raw/processed/project-wiki-research-2026-07-01-fastmcp.md)

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
- Maintained on 2026-06-26 with knowledge-package routing that separates external agent evidence from local implementation acceptance.
- Maintained on 2026-07-01 with knowledge-source migration semantics and FastMCP upstream routing.
