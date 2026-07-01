---
type: "Project Wiki"
title: "Project Wiki"
description: "This folder contains the maintained synthesis layer for this repository."
---

# Project Wiki

This folder contains the maintained synthesis layer for this repository.

The wiki organizes current project understanding across source documents, code, tests, plans, and backlog records. It is a navigation and synthesis layer. It is not the source of truth.

## Use

Agents use the project-wiki skill before changing or explaining specs, architecture, plans, backlog files, documentation surfaces, or user-visible behavior.

Run:

```bash
python3 ~/.codex/skills/project-wiki/scripts/wiki_ops.py status
python3 ~/.codex/skills/project-wiki/scripts/wiki_ops.py suggest --changed
python3 ~/.codex/skills/project-wiki/scripts/wiki_ops.py lint
python3 ~/.codex/skills/project-wiki/scripts/wiki_ops.py questions
```

## Pages

- [schema.md](schema.md)
- [topic-index.md](topic-index.md)
- [glossary.md](glossary.md)
- [open-decisions.md](open-decisions.md)
- [known-defects.md](known-defects.md)
- [maintenance-log.md](maintenance-log.md)
- [federation.md](federation.md)
- [digests](digests/index.md)

## Topic Folders

- [context-architecture](context-architecture/index.md) covers routers, rules layers, knowledge layers, context selection, and compaction.
- [source-workflows](source-workflows/index.md) covers raw source handling, clippings, ingest, reconciliation, digests, and update feeds.
- [prompt-and-instructions](prompt-and-instructions/index.md) covers request packaging, prompts, durable instructions, and file boundaries.
- [agent-workflows](agent-workflows/index.md) covers planning loops, subagents, handoffs, and controlled change workflows.
- [coding-practices](coding-practices/index.md) covers TDD, review, regression repair, and refactoring generated code.
- [retrieval-and-tools](retrieval-and-tools/index.md) covers code retrieval, RAG, tool calls, and MCP as a governed practice.
- [verification-and-evals](verification-and-evals/index.md) covers build, test, lint, runtime checks, evals, graders, and done signals.
- [application-patterns](application-patterns/index.md) covers harness architecture, structured outputs, streaming, workflow state, and product controls.
- [governance-and-risk](governance-and-risk/index.md) covers permissions, approvals, secrets, audit logs, privacy, licensing, and prompt injection.
- [adoption-and-operating-model](adoption-and-operating-model/index.md) covers team rollout, operating agreements, workflow selection, and human acceptance.

Use each topic folder as a hub plus granular leaf pages. Create local leaves for downstream practice, workflow, governance, adoption, or implementation lenses. Link to the federated AI wiki for broad ecosystem entity background.

## Operational Folders

- [raw](../../raw) stores unprocessed source artifacts for local wiki ingest.
- [raw/processed](../../raw/processed) stores source artifacts after they have been fully synthesized into wiki pages.
- [Clippings](../../Clippings) stores human-saved source notes before review or ingest.
- [scripts](../../scripts) stores repository-local helper scripts for wiki source collection, validation, and inspection.

## Automations

- [automated-update-feeds.md](source-workflows/automated-update-feeds.md) records the public topic collector, [leaf update watch](source-workflows/leaf-update-watch.md), and [raw project-wiki monitor](source-workflows/raw-project-wiki-monitor.md) model.
- AI Dev Wiki Topic News Collector saves raw public topic updates.
- AI Dev Wiki Leaf Update Watch saves raw public updates for existing durable local leaves.
- AI Dev Wiki Raw Project-Wiki Monitor ingests raw artifacts into wiki leaves and digests after lint.
