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

The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) and [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) keep broad ecosystem entities upstream-owned while retaining local practice leaves.

The [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json) and [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) keep broad ecosystem entities upstream-owned. [GitHub Copilot](../../../upstream-ai-wiki/developer-tools/github-copilot.md), [xAI](../../../upstream-ai-wiki/companies/xai.md), the [Grok model family](../../../upstream-ai-wiki/models/grok-model-family.md), [Microsoft Agent Framework](../../../upstream-ai-wiki/agentic-frameworks/microsoft-agent-framework.md), [MCP observability](../../../upstream-ai-wiki/techniques/mcp-observability.md), and the [upstream MCP server index](../../../upstream-ai-wiki/mcp-servers/index.md) own broad product, company, model, framework, protocol, and observability background.

The July 29 raw sources keep broad ecosystem entities upstream-owned. [Claude Code](../../../upstream-ai-wiki/developer-tools/claude-code.md), [Anthropic](../../../upstream-ai-wiki/companies/anthropic.md), [OpenAI](../../../upstream-ai-wiki/companies/openai.md), [Microsoft Agent Framework](../../../upstream-ai-wiki/agentic-frameworks/microsoft-agent-framework.md), [Model Context Protocol](../../../upstream-ai-wiki/techniques/mcp-protocol-versioning.md), [MCP server coverage](../../../upstream-ai-wiki/mcp-servers/index.md), [AWS Bedrock](../../../upstream-ai-wiki/developer-tools/amazon-bedrock.md), and named coding-agent tools own broad product, company, framework, protocol, and developer-tool context. Local pages keep only downstream practice for failure attribution, instruction layers, outcome prompting, measurement, MCP migration, thin harnesses, compaction, RAG provenance, acceptance gates, and primary-folder authority.

Upstream routing:

- [Amazon AI](../../../upstream-ai-wiki/companies/amazon-ai.md), [Google AI](../../../upstream-ai-wiki/companies/google-ai.md), [Microsoft AI](../../../upstream-ai-wiki/companies/microsoft-ai.md), [Oracle](../../../upstream-ai-wiki/companies/oracle.md), [OpenAI](../../../upstream-ai-wiki/companies/openai.md), [Mastra](../../../upstream-ai-wiki/agentic-frameworks/mastra.md), [Claude Code](../../../upstream-ai-wiki/developer-tools/claude-code.md), [GitHub Copilot](../../../upstream-ai-wiki/developer-tools/github-copilot.md), the upstream [AI coding agents hub](../../../upstream-ai-wiki/developer-tools/ai-coding-agents-and-autonomous-engineering-platforms.md), and the upstream [MCP server index](../../../upstream-ai-wiki/mcp-servers/index.md) own broad product, company, framework, and MCP-server coverage.
- Endor Labs, Apideck, Box, Visual Studio Code, and some July 27 product-specific pages do not yet have dedicated upstream leaves identified in this local ingest, so local synthesis links upstream hubs when available and keeps only downstream practice.

Local routing:

- Local pages keep [layered AI code review roles](../coding-practices/layered-ai-code-review-roles.md), [progressive MCP tool discovery](../retrieval-and-tools/progressive-mcp-tool-discovery.md), [agent cost telemetry](../adoption-and-operating-model/agent-cost-telemetry.md), [executable PRD templates](../prompt-and-instructions/executable-prd-templates.md), [coding agent runtime updater integrity](coding-agent-runtime-updater-integrity.md), [verification tax and acceptance gates](../verification-and-evals/verification-tax-and-acceptance-gates.md), [file-oriented enterprise builder workflows](../application-patterns/file-oriented-enterprise-builder-workflows.md), [deep research and writing workflows](../agent-workflows/deep-research-and-writing-workflows.md), [use compose build workflow selection](../agent-workflows/use-compose-build-workflow-selection.md), [persistent agent workspaces](../agent-workflows/persistent-agent-workspaces.md), and [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md).
- July 28 telemetry routing stays local in [agent cost telemetry](../adoption-and-operating-model/agent-cost-telemetry.md) and [user-visible progress and runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md).
- July 28 approval and governance routing stays local in [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md), [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md), and [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md).
- July 28 tool routing stays local in [progressive MCP tool discovery](../retrieval-and-tools/progressive-mcp-tool-discovery.md), [remote MCP skill discovery and governance](../retrieval-and-tools/remote-mcp-skill-discovery-and-governance.md), and [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md).
- July 28 harness and context routing stays local in [application harness patterns](../application-patterns/application-harness-patterns.md), [harness sizing by workflow complexity](../application-patterns/harness-sizing-by-workflow-complexity.md), [AI process layer and workflow state](../application-patterns/ai-process-layer-and-workflow-state.md), [declarative agent workflow artifacts](../application-patterns/declarative-agent-workflow-artifacts.md), and [context engineering for request packages](../prompt-and-instructions/context-engineering-for-request-packages.md).
- July 28 risk and eval routing stays local in [prompt injection and untrusted content](../governance-and-risk/prompt-injection-and-untrusted-content.md), [sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md), [destructive command controls](../governance-and-risk/destructive-command-controls.md), and [agent-assisted performance optimization gates](../verification-and-evals/agent-assisted-performance-optimization-gates.md).

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
- Route July 27 vendor, MCP server, IDE, coding-agent, and enterprise-product updates upstream while retaining linked local leaves for review-role, tool-discovery, telemetry, instruction, updater, CI, workflow, and governance practice.
- Route July 28 product, company, model, framework, IDE, MCP, and observability-tool updates upstream while retaining local managed-policy, telemetry, approval, supply-chain, context, harness, and eval practice.
- Route July 29 company, product, framework, protocol, benchmark, conference, and tool entities upstream while retaining local practice for eval attribution, context, prompting, measurement, MCP migration, harnesses, RAG, TDD, and primary-root authority.

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
- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 29 topic news collector source](../../../raw/processed/2026-07-29/ai-dev-wiki-topic-news-collector-2026-07-29T203119-0400.json)
- [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json)

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
- The upstream AI wiki does not yet have dedicated local links for Endor Labs, Apideck, Box, or Visual Studio Code in the July 27 source-routing note; route through upstream company, developer-tool, coding-agent, or MCP hubs until those leaves exist.
- The upstream AI wiki owns July 28 GitHub, Copilot, GitHub Actions, Dependabot, OpenSSF, Grok, xAI, Microsoft Agent Framework, MCP, OpenTelemetry, IDE, and framework background; use upstream hubs if exact entity leaves are missing.
- The upstream AI wiki owns July 29 Claude Code, Anthropic, OpenAI, Microsoft Agent Framework, Model Context Protocol, MCP servers, AWS Bedrock, benchmark, conference, and coding-agent tool background; use upstream hubs if exact entity leaves are missing.

## Maintenance Notes

- Created on 2026-06-23 to separate authority order, source conflict handling, synonym normalization, and federation routing from the broader source-workflows hub.
- Maintained on 2026-06-26 with knowledge-package routing that separates external agent evidence from local implementation acceptance.
- Maintained on 2026-07-01 with knowledge-source migration semantics and FastMCP upstream routing.
- Maintained on 2026-07-06 with broad-entity routing for July 6 products, tools, standards, and snippet-date evidence.
- Maintained on 2026-07-07 with broad-entity routing for July 7 desktop-agent, telemetry, runtime, benchmark, memory, and contribution-policy sources.
- Maintained on 2026-07-16 with broad-entity routing for product, vendor, runner-provider, certification, and coding-agent ecosystem updates.
- Maintained on 2026-07-17 with broad-entity routing for product, vendor, framework, benchmark, and weak-date evidence, including non-promotion of the Cursor mobile item.
- Maintained on 2026-07-26 with upstream routing for products, benchmarks, models, companies, regulations, and coding-agent tools while retaining local evaluation, governance, instruction, memory, cost, supervision, and review controls.
- Maintained on 2026-07-27 with upstream routing for vendor, MCP server, IDE, and coding-agent entities while retaining local practice implications.
- Maintained on 2026-07-28 with upstream routing for product, company, model, framework, IDE, MCP, and observability entities while retaining local governance, telemetry, approval, supply-chain, context, harness, and eval practice.
- Maintained on 2026-07-29 with upstream routing for company, product, framework, protocol, benchmark, conference, and coding-agent tool entities while retaining local practice implications.
