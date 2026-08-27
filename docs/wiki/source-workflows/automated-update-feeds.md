---
type: "Source Workflow"
title: "Automated Update Feeds"
description: "Automated update feeds use source-first boundaries."
tags: ["source-workflows"]
---

# Automated Update Feeds

## Current Understanding

Automated update feeds use source-first boundaries. Public collectors and leaf watches save raw artifacts only; ingest workflows own wiki page updates, digest updates, lint, verification, and processed-source moves.

This wiki uses three automation layers:

- [public-topic-news-collector.md](public-topic-news-collector.md) watches approved AI-assisted development practice topics and saves dated raw artifacts.
- [leaf-update-watch.md](leaf-update-watch.md) checks existing durable local leaves and saves qualifying public updates as raw artifacts.
- [raw-project-wiki-monitor.md](raw-project-wiki-monitor.md) moves human clippings into raw source storage, processes unprocessed raw artifacts into durable leaves and monthly digests, runs project-wiki lint, and moves fully processed artifacts into processed storage.

Collectors only use public sources and must avoid private, proprietary, sensitive, PII, or company-internal local content. They include source URLs, visible dates, factual summaries, relevance notes, named entities, exclusions with reasons, and follow-up notes. When a source is about an upstream-owned entity such as a model, provider, product, framework, MCP server, or broad developer tool, the source workflow routes that entity through [federation.md](../federation.md) and keeps only the local practice implication here.

The [July 10 leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json) reinforces the feed boundary: leaf watches may find useful public evidence about managed settings, cost telemetry, harnesses, and source workflows, but the raw artifact remains the handoff to ingest. Feed output should identify qualifying URLs, excluded candidates, and follow-up notes without turning watcher output into wiki edits before the monitor processes it.

The [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json) adds MCP roadmap evidence for server-initiated events, task composition, agentic messaging, and agent identity. Locally, update-feed design should keep polling as the default source-first collector pattern until event or task primitives can provide source URL, visible date, authorization scope, trigger reason, exclusion rationale, and replayable raw artifact evidence.

## Feed Topics

The feed-topic list is configuration for local practice monitoring, not a separate entity inventory.

- Context architecture: context engineering, durable agent instructions, memory, compaction, and source selection.
- Source workflows: raw source ingest, AI knowledge management for software teams, clipping and citation workflows, and source reconciliation.
- Prompt and instructions: coding-agent prompts, instruction files, prompt packaging, and file boundary practices.
- Agent workflows: planning loops, subagents, handoffs, delegated coding, and visible work tracking.
- Coding practices: [AI-assisted TDD](../coding-practices/ai-assisted-tdd.md), code review, regression repair, refactoring generated code, and tier-specific conventions.
- Retrieval and tools: code retrieval, RAG for codebases, tool-call patterns, and MCP as a governed practice.
- Verification and evals: software engineering evals, AI code review checks, benchmarks, deterministic graders, and runtime verification.
- Application patterns: harness architecture, structured outputs, workflow state, streaming progress, and AI process layers.
- Governance and risk: permissions, approvals, audit logs, secrets, prompt injection, package-install risk, licensing, privacy, and compliance.
- Adoption and operating model: team rollout, operating agreements, acceptance gates, training material, and human accountability.
- Event and task primitives: server-initiated events, agentic messaging, and task composition can reduce polling only when they preserve source-first provenance, authorization scope, replayability, and exclusion evidence.

## Configured Automations

- [AI Dev Wiki Topic News Collector](public-topic-news-collector.md) runs daily as a raw-only public topic collector.
- [AI Dev Wiki Leaf Update Watch](leaf-update-watch.md) runs daily as a raw-only checker for durable local leaves.
- [AI Dev Wiki Raw Project-Wiki Monitor](raw-project-wiki-monitor.md) runs twice daily as the ingest job that may refresh wiki leaves and digests after processing raw artifacts.

## Authoritative Sources

- [source-workflows](index.md)
- [topic-index.md](../topic-index.md)
- [schema.md](../schema.md)
- [federation.md](../federation.md)
- [July 10 leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json)
- [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json)
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

- [public topic news collector](public-topic-news-collector.md)
- [leaf update watch](leaf-update-watch.md)
- [raw project-wiki monitor](raw-project-wiki-monitor.md)
- [clipping and raw intake](clipping-and-raw-intake.md)
- [source reconciliation and routing](source-reconciliation-and-routing.md)
- [digests](../digests/index.md)
- [context-architecture](../context-architecture/index.md)
- [verification-and-evals](../verification-and-evals/index.md)
- [governance-and-risk](../governance-and-risk/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to document the accepted update-feed setup.
- Recorded the configured update-feed automations on 2026-06-23 after setup.
- Split on 2026-06-23 so each automation layer has a durable local practice leaf.
- Maintained on 2026-07-10 with leaf-watch handoff boundaries for qualifying URLs, exclusions, and follow-up notes.
- Maintained on 2026-08-26 with MCP roadmap event, task, messaging, and identity implications for source-first feed design.
