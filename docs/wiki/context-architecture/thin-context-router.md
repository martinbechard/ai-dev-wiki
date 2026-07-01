---
type: "Context Architecture"
title: "Thin Context Router"
description: "The thin context router is the short root guidance file that sends an agent to the right task-specific documentation."
tags: ["context-architecture"]
---

# Thin Context Router

## Current Understanding

The thin context router is the short root guidance file that sends an agent to the right task-specific documentation. It should route rather than summarize the whole repository, because loading every rule and reference into the live prompt increases distraction and cost.

The source note frames the router as a single root file with a strict size limit. The local practice is to keep the router task-oriented: it names where to find rules, project facts, plans, decisions, references, and archives, then lets the agent load the smallest relevant document.

## Practice Boundaries

- Keep the router short enough that it can be loaded at the start of work.
- Point to task-specific rules, knowledge, plans, decisions, references, and archive locations instead of copying their content into the router.
- Use the router for navigation, authority hints, and task routing.
- Move durable conventions and stable project facts into their own layers.
- Keep archived or historical material clearly marked so it does not drive current work.

## Authoritative Sources

- [Folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md)
- [Context router and knowledge layers](context-router-and-knowledge-layers.md)
- [Request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [rules and knowledge layers](rules-and-knowledge-layers.md)
- [lifespan organized documentation](lifespan-organized-documentation.md)
- [context selection and compaction](context-selection-and-compaction.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from the folder organization source note covering the root router file and task-specific guidance routing.
