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

The [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json), [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json), [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md), [Deepsec clipping](../../../raw/processed/vercel-labsdeepsec Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents.md), and [Just Bash clipping](../../../raw/processed/vercel-labsjust-bash Bash for Agents.md) reinforce the federation split. Vercel, LangChain, MintMCP, Agent Orchestrator, ai-memory, Deepsec, Just Bash, Chat SDK, standards, and model names are broad ecosystem entities unless the local page is about downstream workflow, governance, evaluation, harness, or adoption practice. Date evidence that comes only from search-result snippets should remain source-attributed and should not be promoted into a durable current fact without stronger source-page evidence.

The [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) and [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) continue that split. GitHub, Vercel, Oracle, ZenML, Honeycomb, Cycode, Godot, model families, benchmarks, standards bodies, and workflow runtimes are upstream-owned broad entities when the wiki needs company, product, model, or framework background. Local pages keep the downstream practices: desktop-agent onboarding controls, spend governance, sandbox and runtime telemetry, repo-derived role design, merge-conflict coordination, step-level evals, generated-code accountability, and governed memory boundaries.

The [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json) reinforces product-versus-practice routing. OpenAI, GitHub, StepSecurity, Atlassian, Pervaziv, Presidio, Gradient, individual coding agents, runner providers, certification programs, and product releases remain upstream-owned as ecosystem entities. Local ingest keeps the practice implications: prompt-injection harnesses, secret alert routing, PR review-state filters, runner egress evidence, fleet verification capacity, issue-to-agent handoff contracts, private-agent data boundaries, and vendor-selection governance evidence.

The [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) reinforces date-evidence routing. GitLab, GitHub, [OpenAI](../../../upstream-ai-wiki/companies/openai.md), Cursor, JetBrains, [Microsoft AI](../../../upstream-ai-wiki/companies/microsoft-ai.md), [Google Cloud](../../../upstream-ai-wiki/developer-tools/google-cloud-workbench-notebooks.md), [LangChain](../../../upstream-ai-wiki/agentic-frameworks/langchain-stack.md), and benchmark or framework names remain upstream-owned broad entities. Local pages keep only practice implications for governed flows, security-review gates, remediation packets, destructive-command controls, portable skills, performance verification, sandboxing, and eval design. The Cursor mobile-agent item was not promoted into a July 17 durable update because the [official Cursor changelog](https://cursor.com/changelog) identifies the mobile release as June 29, 2026; the source artifact's weak date evidence remains a routing note rather than a current local fact.

The [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json) and [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json) reinforce the same federation boundary. Broad coding-agent tool and company coverage routes to the [upstream AI coding agents hub](../../../upstream-ai-wiki/developer-tools/ai-coding-agents-and-autonomous-engineering-platforms.md), [OpenAI](../../../upstream-ai-wiki/companies/openai.md), [Microsoft AI](../../../upstream-ai-wiki/companies/microsoft-ai.md), and [Nvidia](../../../upstream-ai-wiki/companies/nvidia-ai.md), while model-family coverage routes through the [upstream model hub](../../../upstream-ai-wiki/models/index.md). Local pages keep benchmark design, agent selection, subagent auditability, workflow security, supervision, memory scope, model routing, cost telemetry, and human-review practice.

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
- Keep product, company, framework, standard, and model details upstream-owned when local sources only need their practice implications.
- Attribute weak or snippet-only date evidence and avoid converting it into source-page certainty.
- Route July 7 broad ecosystem updates upstream while keeping local practice updates anchored in workflow, governance, evaluation, telemetry, memory, and adoption leaves.
- Route July 16 product, vendor, certification, and runner-provider updates upstream while retaining only local workflow, governance, verification, and adoption controls.
- Route July 17 product, vendor, framework, and benchmark entities upstream while retaining local practice evidence for governance, approval, remediation, skills, sandboxing, and evals.
- Recheck weak date evidence before durable synthesis; keep misdated or snippet-only items as routing notes unless official source-page evidence supports the ingest window.
- Route July 26 product, benchmark, model, company, regulation, and coding-agent tool entities upstream while retaining local practice for evaluation, governance, instruction, memory, cost, supervision, and review controls.

## Authoritative Sources

- [schema.md](../schema.md)
- [federation.md](../federation.md)
- [topic-index.md](../topic-index.md)
- Target environment automation record for AI Dev Wiki Raw Project-Wiki Monitor: Not yet identified.
- project-wiki source priority reference from the installed skill package: Not yet identified.
- [upstream AI wiki topic index](../../../upstream-ai-wiki/topic-index.md)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json)
- [FastMCP research source](../../../raw/processed/project-wiki-research-2026-07-01-fastmcp.md)
- [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json)
- [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json)
- [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md)
- [Deepsec clipping](../../../raw/processed/vercel-labsdeepsec Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents.md)
- [Just Bash clipping](../../../raw/processed/vercel-labsjust-bash Bash for Agents.md)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [Official Cursor changelog](https://cursor.com/changelog)
- [upstream AI coding agents hub](../../../upstream-ai-wiki/developer-tools/ai-coding-agents-and-autonomous-engineering-platforms.md)
- [upstream OpenAI](../../../upstream-ai-wiki/companies/openai.md)
- [upstream Microsoft AI](../../../upstream-ai-wiki/companies/microsoft-ai.md)
- [upstream LangChain stack](../../../upstream-ai-wiki/agentic-frameworks/langchain-stack.md)
- [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json)
- [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json)

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

- The upstream AI wiki does not yet have GitLab, JetBrains, WebStorm, GoLand, or Cursor product entity leaves to link for the July 17 routing note.
- The upstream AI wiki does not yet have dedicated entity leaves for July 26 benchmark sources such as Tokoscope, DeepSWE, GLSRM, Coding Agents Index, or the open-source coding-agent comparison set; route them through the upstream coding-agents, model, or technique hubs until entity leaves exist.

## Maintenance Notes

- Created on 2026-06-23 to separate authority order, source conflict handling, synonym normalization, and federation routing from the broader source-workflows hub.
- Maintained on 2026-06-26 with knowledge-package routing that separates external agent evidence from local implementation acceptance.
- Maintained on 2026-07-01 with knowledge-source migration semantics and FastMCP upstream routing.
- Maintained on 2026-07-06 with broad-entity routing for July 6 products, tools, standards, and snippet-date evidence.
- Maintained on 2026-07-07 with broad-entity routing for July 7 desktop-agent, telemetry, runtime, benchmark, memory, and contribution-policy sources.
- Maintained on 2026-07-16 with broad-entity routing for product, vendor, runner-provider, certification, and coding-agent ecosystem updates.
- Maintained on 2026-07-17 with broad-entity routing for product, vendor, framework, benchmark, and weak-date evidence, including non-promotion of the Cursor mobile item.
- Maintained on 2026-07-26 with upstream routing for products, benchmarks, models, companies, regulations, and coding-agent tools while retaining local evaluation, governance, instruction, memory, cost, supervision, and review controls.
