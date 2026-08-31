---
type: "Adoption And Operating Model"
title: "Portable Agent Skills And Runbooks"
description: "Portable agent skills are reusable procedures that can travel across agent tools without becoming one overloaded prompt."
tags: ["adoption-and-operating-model"]
---

# Portable Agent Skills And Runbooks

## Current Understanding

Portable agent skills are reusable procedures that can travel across agent tools without becoming one overloaded prompt. The [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md) frames the core problem as procedural debt: teams accumulate prompt bloat, repeated setup explanations, fragmented tool-specific rules, and weak verification when each agent harness owns a different copy of the same working method.

A local skill should be narrower than a broad operating manual. It should name the triggering situation, the job it owns, the tools or references it expects, the boundaries that stop misuse, the output shape, and the proof standard required before completion. This keeps the live prompt small while giving the agent an inspectable procedure when the work calls for it.

Runbooks compose skills into reliable workflows. A skill answers what one reusable capability does, while a runbook defines the sequence that produces a larger outcome. The downstream practice is to keep skill primitives small, keep runbooks explicit, and route both through the correct scope: personal procedures stay personal, project procedures stay with the repository, and shared team procedures belong in a controlled team source of truth.

The [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json) reinforces procedural debt as an operating risk. Portable skills and runbooks should record trigger rules, boundaries, required tools, ownership, and verification standards in a reusable artifact rather than leaving procedure inside a single vendor workspace, chat history, or personal prompt collection.

The [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json) adds a third-party skill intake boundary. Vendor-published agent skills can package domain integration instructions for coding agents, but local adoption should review trust, versioning, scope, and project fit before importing those instructions into a repository or team workflow.

The [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json) adds portability pressure from codebase wiki memory and shared context tags. Team procedures should keep reusable knowledge in source-backed, versionable wiki or skill artifacts so a single vendor workspace does not become the only place where project memory or agent context can be reused.

The July 17 raw sources add IDE and platform packaging evidence. The [topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) records IDE-managed agent skills and imports from other coding agents as a portability signal; broad WebStorm, GoLand, [GitHub Copilot CLI](../../../upstream-ai-wiki/developer-tools/github-copilot-cli.md), [Claude Code](../../../upstream-ai-wiki/developer-tools/claude-code.md), and [OpenAI Codex](../../../upstream-ai-wiki/developer-tools/openai-codex.md) product coverage remains upstream-owned. The [leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json) adds build-evaluate-deploy-monitor skills as operational packages. Locally, a portable skill should carry source registry, import path, compatibility, evaluation, deployment, monitoring, and approval-workflow metadata when those facts affect reuse.

The [managed agent vertical integration query source](../../../raw/processed/query/2026-08-05-managed-agent-vertical-integration.md) adds a layer-by-layer portability rule. The focused selection practice lives in [managed agent portability boundaries](managed-agent-portability-boundaries.md); this page keeps the skill rule that reusable procedures should stay in reviewable project or team artifacts when vendor-managed sessions, memory, and control-plane semantics cannot be moved cleanly.

The [August 10 topic news collector source](../../../raw/processed/2026-08-10/ai-dev-wiki-topic-news-collector-2026-08-10T203108-0400.json) adds a current vendor example of software-testing skills packaged for agents. Locally, test-suite architecture, TDD, load profiling, and vulnerability-audit skills should be imported as reviewable runbook material with owner, version, command behavior, customization notes, and generated-output review gates rather than as opaque product-specific capability.

The August 12 raw sources add Agent Plugins packaging evidence. The [portable agent plugin classification query source](../../../raw/processed/query/2026-08-12-portable-agent-plugin-classification.md) clarifies that portable Agent Plugins packages are not the same thing as MCP, and the [topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json) plus [leaf update watch source](../../../raw/processed/2026-08-12/ai-dev-wiki-leaf-update-watch-2026-08-12T210257-0400.json) show skills travelling with manifests, MCP server configuration, client namespaces, managed settings, and marketplace installation. This page keeps the skill/runbook contract; [portable agent plugin packaging and governance](../retrieval-and-tools/portable-agent-plugin-packaging-and-governance.md) owns the package boundary that carries those skills between clients.

The August 17 [leaf update watch](../source-workflows/leaf-update-watch.md) adds general-availability and workflow-management evidence for portable plugin packages. Locally, reusable skills and runbooks should keep version, owner, client compatibility, subagent task expectations, side-channel question handling, and MCP allowlist assumptions visible so a plugin update or client switch does not silently change the procedure.

The [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json) adds platform-specific skill evidence:

- A reusable service skill should package platform workflows, constraints, guardrails, verification steps, and expected artifacts.
- Coding agents should not prototype against external services from general model knowledge alone.
- Product-specific details remain upstream-owned; locally, the runbook must show what the skill authorizes, what it forbids, and how generated artifacts are checked.

The [August 30 leaf update watch source](../../../raw/processed/2026-08-30/ai-dev-wiki-leaf-update-watch-2026-08-30T210135-0400.json) adds portable-skill evidence from Microsoft Agent Skills and Goldman Sachs skill packaging. Locally, reusable skills should keep detailed procedure and institutional knowledge in reviewable packages that can be approved, evaluated, and refreshed without bloating every prompt.

## Practice Boundaries

- Use a one-off prompt for one-time work and a skill when a procedure recurs across sessions, tools, or agents.
- Avoid turning every preference into a skill; preserve only recurring procedures that have a non-obvious trigger, boundary, or verification rule.
- Keep skill files inspectable and scoped so they can be carried between tools without copying unrelated project context.
- Use runbooks when multiple skills must be composed into an outcome that needs handoff, publishing, release, research, or review.
- Treat verification as part of the skill contract, not as optional completion prose.
- Keep Open Skills as source evidence for the local practice lens; broad ecosystem tracking for agent tools and product catalogs remains upstream.
- Store recurring procedures where the team can review ownership, trigger rules, tool requirements, and verification expectations.
- Avoid vendor-local procedure drift by keeping portable runbooks aligned with project or team source-of-truth rules.
- Treat third-party skill packs as source material until reviewed, pinned, adapted, and assigned an owner in the local instruction hierarchy.
- Record whether a skill is vendor-owned, project-owned, team-owned, or personal so future agents know where updates and accountability belong.
- Keep reusable project memory in source-backed, versionable artifacts when multiple agent tools or teams need the same context.
- Treat vendor-local context tags or workspace memory as convenience surfaces, not the sole source of team procedure or project knowledge.
- Record source registry, import path, owner, compatibility target, verification standard, and approval workflow before importing portable skills across agent tools.
- Treat platform skills that scaffold, evaluate, deploy, or monitor systems as operational runbooks, not just prompt snippets.
- Keep portable procedures outside vendor session state when model, runtime, memory, or control-plane substitution matters.
- Treat reusable testing and vulnerability-audit skills as runbook material that needs owner, version, command behavior, customization, and output-review metadata before team use.
- Keep the reusable skill contract distinct from the plugin package that installs it; review skill procedure, package manifest, MCP declarations, and client-specific behavior as separate artifacts.
- Record plugin version, owner, compatible clients, expected subagent task artifacts, side-channel question rules, and MCP allowlist assumptions in reusable runbooks.
- For service-specific skills, record platform constraints, guardrails, generated artifacts, verification steps, allowed tool scope, and owner review before relying on them for prototype generation.
- Use progressive disclosure for skills so agents load detailed instructions, scripts, resources, and assets only when the task needs them.
- Pair institutional skill libraries with security review, owner feedback, and eval loops so reusable practices stay current and auditable.

## Authoritative Sources

- [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md)
- [durable instructions and skill files](durable-instructions-and-skill-files.md)
- [instruction hierarchy and artifact boundaries](../prompt-and-instructions/instruction-hierarchy-and-artifact-boundaries.md)
- [verification tax and acceptance gates](../verification-and-evals/verification-tax-and-acceptance-gates.md)
- [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json)
- [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json)
- [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json)
- [managed agent vertical integration query source](../../../raw/processed/query/2026-08-05-managed-agent-vertical-integration.md)
- [August 10 topic news collector source](../../../raw/processed/2026-08-10/ai-dev-wiki-topic-news-collector-2026-08-10T203108-0400.json)
- [portable agent plugin classification query source](../../../raw/processed/query/2026-08-12-portable-agent-plugin-classification.md)
- [August 12 topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json)
- [August 12 leaf update watch source](../../../raw/processed/2026-08-12/ai-dev-wiki-leaf-update-watch-2026-08-12T210257-0400.json)
- [August 17 leaf update watch source](../../../raw/processed/2026-08-17/ai-dev-wiki-leaf-update-watch-2026-08-17T210257-0400.json)
- [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json)
- [August 30 leaf update watch source](../../../raw/processed/2026-08-30/ai-dev-wiki-leaf-update-watch-2026-08-30T210135-0400.json)
- [upstream AI coding agents hub](../../../upstream-ai-wiki/developer-tools/ai-coding-agents-and-autonomous-engineering-platforms.md)
- [upstream Claude Code](../../../upstream-ai-wiki/developer-tools/claude-code.md)
- [upstream OpenAI Codex](../../../upstream-ai-wiki/developer-tools/openai-codex.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption operating agreements](adoption-operating-agreements.md)
- [durable instructions and skill files](durable-instructions-and-skill-files.md)
- [workflow before model selection](workflow-before-model-selection.md)
- [human agent approval boundaries](human-agent-approval-boundaries.md)
- [managed agent portability boundaries](managed-agent-portability-boundaries.md)
- [portable agent plugin packaging and governance](../retrieval-and-tools/portable-agent-plugin-packaging-and-governance.md)

## Open Questions

- The upstream AI wiki does not yet have JetBrains, WebStorm, or GoLand entity leaves to link for IDE-managed skill product signals.

## Maintenance Notes

- Created on 2026-06-23 from source-backed guidance on portable procedures, runbook composition, scope boundaries, procedural debt, and proof standards for agent work.
- Maintained on 2026-07-01 with portable procedure ownership, trigger rules, required tools, and verification standards.
- Maintained on 2026-07-03 with third-party skill intake, ownership, trust review, version pinning, and local adaptation boundaries.
- Maintained on 2026-07-05 with versionable wiki memory, reusable context portability, and vendor-local memory boundaries.
- Maintained on 2026-07-17 with IDE-managed skill imports, source registry metadata, cross-agent compatibility, and build-evaluate-deploy-monitor runbook boundaries.
- Maintained on 2026-08-05 with layer-by-layer managed-agent portability guidance for reusable procedures.
- Maintained on 2026-08-10 with testing-skill import boundaries for ownership, versioning, command behavior, customization, and generated-output review.
- Maintained on 2026-08-12 with Agent Plugins package boundaries separated from reusable skill and runbook contracts.
- Maintained on 2026-08-17 with plugin version, client compatibility, subagent task, side-channel question, and MCP allowlist runbook guidance.
- Maintained on 2026-08-21 with service-specific skill constraints, guardrails, generated-artifact, verification-step, allowed-tool-scope, and owner-review guidance.
- Maintained on 2026-08-30 with progressive-disclosure, script/resource/asset, approval-control, security-review, feedback-loop, and eval-loop skill evidence.
