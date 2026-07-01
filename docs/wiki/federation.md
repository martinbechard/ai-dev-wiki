---
type: "Topic"
title: "Wiki Federation"
description: "This wiki is a downstream, one-way extension of the upstream AI ecosystem wiki."
---

# Wiki Federation

## Current Understanding

This wiki is a downstream, one-way extension of the upstream AI ecosystem wiki. The downstream wiki reads and links upstream pages, but it does not rewrite upstream content as part of normal local maintenance.

The accepted upstream is the [AI wiki](../../upstream-ai-wiki/README.md). It owns broad AI ecosystem context, including [companies](../../upstream-ai-wiki/companies/index.md), [models](../../upstream-ai-wiki/models/index.md), [products](../../upstream-ai-wiki/products/index.md), [developer tools](../../upstream-ai-wiki/developer-tools/index.md), [agentic frameworks](../../upstream-ai-wiki/agentic-frameworks/index.md), [MCP servers](../../upstream-ai-wiki/mcp-servers/index.md), and [techniques](../../upstream-ai-wiki/techniques/index.md).

This wiki owns the AI-assisted development lens: context architecture, guidance structure, agent operating practices, workflows, verification, governance, and local adoption patterns. It can cite upstream pages when a local practice depends on a product, framework, model, MCP server, or technique, but it should not create local encyclopedia leaves for those upstream-owned entities.

## Federation Rules

- Search the [upstream topic index](../../upstream-ai-wiki/topic-index.md) before creating local entity leaves.
- Link to upstream entity pages when the upstream wiki already owns the broad subject.
- Create local pages only when the topic is a downstream lens, such as usage guidance, operating model, evaluation criteria, governance, workflow, or local decision.
- Keep ecosystem monitoring in the upstream wiki unless the user approves a local feed for practice-oriented sources that the upstream wiki does not own.
- Record unclear ownership as an open question instead of silently duplicating analysis.

## Authoritative Sources

- [AI wiki README](../../upstream-ai-wiki/README.md)
- [AI wiki topic index](../../upstream-ai-wiki/topic-index.md)
- [AI wiki schema](../../upstream-ai-wiki/schema.md)
- [Folder organization source note](../../raw/processed/Folder organization by @AICodethatWorks.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [topic-index.md](topic-index.md)
- [schema.md](schema.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created to record the one-way federation from this AI-assisted development wiki to the broader AI ecosystem wiki before local topic folders are finalized.
- The upstream-ai-wiki folder at the vault root exposes the upstream wiki through a local symlink so Obsidian resolves cross-wiki links inside this vault.
