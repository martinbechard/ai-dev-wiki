---
type: "Context Architecture"
title: "Context Router And Knowledge Layers"
description: "Context router and knowledge layers are the local pattern for keeping agent guidance small enough to load and stable enough to prevent repeated rediscovery."
tags: ["context-architecture"]
---

# Context Router And Knowledge Layers

## Current Understanding

Context router and knowledge layers are the local pattern for keeping agent guidance small enough to load and stable enough to prevent repeated rediscovery. The source note describes a thin router file that points the agent to task-specific guidance, a rules layer for conventions, a knowledge layer for project facts, and documentation folders organized by lifespan.

The specific patterns live in sibling leaves. [Thin context router](thin-context-router.md) owns routing, [rules and knowledge layers](rules-and-knowledge-layers.md) owns durable conventions and stable facts, [lifespan organized documentation](lifespan-organized-documentation.md) owns documentation authority signals, and [context selection and compaction](context-selection-and-compaction.md) owns token discipline.

This page owns the downstream practice. Broad coverage of Claude Code and other coding-agent products belongs to the upstream [AI wiki developer tools index](../../../upstream-ai-wiki/developer-tools/index.md).

The [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json) reinforces the router boundary for enterprise context layers. The router should direct agents toward the smallest relevant layer for governed meaning, policy, lineage, retrieval, memory, and task rules instead of sending every task through a broad context bundle.

The [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) adds runtime-memory and workflow-runtime evidence. Context routers should route separately to model context, durable execution history, memory stores, event logs, and human-wait state. Tool and runtime names stay upstream-owned; locally, the router must prevent those layers from collapsing into one opaque prompt bundle.

The [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json) adds active-versus-durable context evidence. Context routers should distinguish active turn context, working-set assembly, durable decisions, memory stores, artifacts, and auditable storage so agents know which layer is instruction, evidence, history, or recoverable state.

The [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) adds searchable project artifact evidence. Search over chats, projects, images, and documents should enter the context router as a retrieval layer with source labels, artifact filters, and direct-open verification, not as a replacement for durable instructions, current files, or authoritative wiki pages.

The [July 21 leaf update watch source](../../../raw/processed/2026-07-21/ai-dev-wiki-leaf-update-watch-2026-07-21T210116-0400.json) adds repository-context routing evidence. Memory-aware, MCP-native context layers that store observations in git can reduce repeated repository exploration, but they should be routed as source-backed observation layers with freshness, authority, and minimum-useful-slice checks. Local practice should keep these observations separate from durable instructions, current files, and verified wiki facts until the agent opens the relevant evidence.

The [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json) adds multi-folder workspace routing evidence. Context routers should name one primary repository and instruction root for Git operations, reviews, pull requests, AGENTS.md, and skill discovery, while secondary folders remain attributed evidence roots until a task explicitly grants them authority.

The [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json) adds enterprise source-ranking evidence. Context routers should keep source trust, freshness, access scope, conflict policy, and reranking criteria visible when drawing from Slack, Teams, drive, wiki, repository, or ticket sources. The router should not treat the existence of a connector as permission to merge every retrieved artifact into one undifferentiated context bundle.

## Pattern Leaves

- [thin-context-router.md](thin-context-router.md) keeps the root guidance file short and task-oriented.
- [rules-and-knowledge-layers.md](rules-and-knowledge-layers.md) separates durable conventions from stable project facts.
- [lifespan-organized-documentation.md](lifespan-organized-documentation.md) separates active plans, decisions, references, and archive history.
- [context-selection-and-compaction.md](context-selection-and-compaction.md) keeps useful evidence in view while limiting irrelevant context.

## Practice Boundaries

- Keep routing, rules, knowledge, active plans, decisions, references, archives, and compaction as separate context concerns.
- Route detailed maintenance questions to the smallest leaf that owns the concept.
- Keep upstream product and agent-tool background in the federated AI wiki unless the local page is describing a downstream practice lens.
- Preserve authority signals so agents know which documents should guide current work.
- Route governed meaning, policy metadata, and decision memory to knowledge-layer leaves rather than repeating them in the thin router.
- Route model context, durable execution history, memory stores, event logs, and human-wait state as separate layers.
- Route active turn context, working-set assembly, durable decisions, artifacts, and auditable storage as separate context layers.
- Route searchable chats, project files, images, and documents as attributed retrieval candidates that must be opened and verified before they become durable context.
- Route memory-aware repository observations as attributed, freshness-labeled retrieval candidates; require direct evidence checks before they replace live file reads or durable wiki synthesis.
- Route primary Git and instruction roots separately from secondary related-code, documentation, and reference folders.
- Route enterprise knowledge sources with explicit source trust, freshness, access scope, conflict handling, and reranking labels before they become active model context.
- Route persistent memories, managed settings, and behavior-baseline deviations through different layers so convenience context cannot override governance evidence.

## Authoritative Sources

- [Folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [federation.md](../federation.md)
- [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)
- [July 21 leaf update watch source](../../../raw/processed/2026-07-21/ai-dev-wiki-leaf-update-watch-2026-07-21T210116-0400.json)
- [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json)
- [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json)
- [August 17 leaf update watch source](../../../raw/processed/2026-08-17/ai-dev-wiki-leaf-update-watch-2026-08-17T210257-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [prompt request packages](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [source-workflows](../source-workflows/index.md)
- [federation.md](../federation.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from the folder organization source note and the two local AI development decks.
- Maintained on 2026-06-23 as the overview page for split context architecture leaves.
- Maintained on 2026-07-03 with governed meaning, policy metadata, lineage, retrieval, memory, and task-rule routing boundaries.
- Maintained on 2026-07-07 with separate routing for model context, execution history, memory stores, event logs, and human-wait state.
- Maintained on 2026-07-12 with active context, working-set assembly, durable decisions, artifacts, and auditable storage as separate routing layers.
- Maintained on 2026-07-14 with searchable project artifact routing, source labels, and direct-open verification boundaries.
- Maintained on 2026-07-22 with memory-aware repository observation routing, freshness labels, and minimum-useful-slice checks.
- Maintained on 2026-07-29 with primary Git/instruction root and secondary evidence-folder routing guidance.
- Maintained on 2026-08-14 with enterprise source trust, freshness, access-scope, conflict-policy, and reranking labels for context routing.
- Maintained on 2026-08-17 with separate routing for persistent memory, managed agent settings, and behavior-baseline deviations.
