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

## Authoritative Sources

- [Folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [federation.md](../federation.md)

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
