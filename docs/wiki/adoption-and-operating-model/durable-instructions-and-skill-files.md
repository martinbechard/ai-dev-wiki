---
type: "Adoption And Operating Model"
title: "Durable Instructions And Skill Files"
description: "Durable instructions and skill files keep reusable procedure outside the live prompt until an agent needs it."
tags: ["adoption-and-operating-model"]
---

# Durable Instructions And Skill Files

## Current Understanding

Durable instructions and skill files keep reusable procedure outside the live prompt until an agent needs it. They give the assistant stable role, scope, project rules, references, tool expectations, safety boundaries, and examples without forcing every request to carry every rule.

The [folder-organization source](../../../raw/processed/Folder organization by @AICodethatWorks.md) describes a thin router that points agents toward task-relevant rules, knowledge, decisions, references, active plans, and archives. The [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md) describes agent definition files as the place for role, scope, project rules, important references, tool expectations, safety configuration, and examples. The [HVE Core source](../../../raw/processed/microsoft-hve-core.md) shows the same pattern as a packaged workflow system with agents, prompts, instructions, and skills.

The [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md) adds the portability boundary: reusable procedure should not be trapped in one agent product or copied into drifting tool-specific rule files. This page owns the adoption practice for durable instruction surfaces, while [portable agent skills and runbooks](portable-agent-skills-and-runbooks.md) owns the skill primitive, runbook composition, and procedural-debt lens. [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md) owns the context architecture, and [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md) owns how live requests label source material.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) adds a freshness and provenance lens for durable instruction files. Rules should carry enough creation reason, affected files or incidents, related code changes, and human confirmation dates for maintainers to detect stale operational memory before an agent keeps following outdated guidance.

The [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json) adds a codebase-wiki memory signal. Durable instruction files should point agents toward compact, versionable wiki context instead of embedding full documentation in the live prompt, and scheduled refreshes should preserve provenance so stale project memory can be corrected.

The [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) adds IDE customization, hook, generated-file, and provider-selection signals. Durable instruction surfaces should separate product-managed settings from repository-owned rules, and generated customizations should be reviewed for provenance, scope, approval mode, and tool access before they become standing guidance.

The [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json) adds a trust-boundary signal for repo-local instructions and generated customization files. Durable instructions should distinguish maintainer-owned guidance from untrusted repository content, and teams should teach developers when generated skills, prompts, hooks, rules, or AGENTS.md files are reusable procedure versus unreviewed instruction input.

The July 17 raw sources add skill-provenance and registry-control evidence. The [topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) records IDE-managed skills, public registry connections, and cross-agent imports as durability pressure. Durable instruction surfaces should include owner, version, compatibility target, and change history, while public registry provenance, poisoned registry risk, and allowed tool scope route to [sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md).

The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) adds two instruction-surface signals. Repository rule-file discovery can show setup spread but not actual usage or quality, so it stays here as an adoption-metric caveat. [Executable PRD templates](../prompt-and-instructions/executable-prd-templates.md) owns PRD templates that define permissions, approval gates, logging, escalation, and eval-style done criteria.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds internal-skill adoption evidence. Skills become durable process artifacts when they are tied to named workflows, team standards, validation steps, and owner review; standalone prompts or uncataloged snippets should not be promoted until the workflow and evidence contract are clear.

The [August 7 topic news collector source](../../../raw/processed/2026-08-07/ai-dev-wiki-topic-news-collector-2026-08-07T203203-0400.json) adds skill-eval workshop evidence. Durable skills should be treated as testable instruction artifacts: each shared skill needs representative tasks, edge-case prompts, expected tool-use boundaries, regression checks, and owner review before teams rely on it in recurring coding-agent work.

The [August 12 topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json) adds instruction-maintenance debt evidence. Durable instruction files should be periodically audited for obsolete front-loaded rules, repeated prompts, and model-era assumptions, then shortened or moved into progressive-disclosure skills when the standing prompt no longer needs them. Broad model and product details stay upstream; locally, the operating rule is to treat instruction cleanup as maintenance work with owner review and verification, not as casual prompt trimming.

The [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json) adds startup operating-practice evidence for root instruction files, hooks, evals, and plan mode. Broad Claude Code product coverage stays upstream; locally, durable instructions should support "trust but verify" operating agreements by routing agents to project rules, worktree practice, hook evidence, and eval gates without turning a root instruction file into an overloaded manual.

The [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json) adds durable-instruction signals:

- Review standards can be team-owned, repo-versioned skill files that AI reviewers run against codebase context.
- Platform-specific coding-agent skills can package service constraints, guardrails, and verification steps for prototypes.
- Locally, both should remain inspectable, source-controlled, owner-reviewed instruction artifacts rather than hidden vendor configuration.

The August 23 raw sources add skill-intake pressure. The [topic news collector source](../../../raw/processed/2026-08-23/ai-dev-wiki-topic-news-collector-2026-08-24T003154Z.json) records public skill-directory growth, and the [leaf update watch source](../../../raw/processed/2026-08-23/ai-dev-wiki-leaf-update-watch-2026-08-23T210505-0400.json) treats skills as part of the execution graph beside MCP tools, checkpoints, context, and session state. Locally, durable skills should enter team use through a reviewed intake path with owner, source snapshot, compatibility target, tool scope, verification steps, and retirement criteria.

## Practice Boundaries

- Move stable procedures into durable instruction surfaces once they are reused across tasks.
- Keep the root router thin so it sends agents to the right guidance instead of becoming an overloaded prompt.
- Store active work, decisions, references, and archive material by lifespan so agents do not confuse historical plans with current instructions.
- Keep safety and permission configuration distinct from prose instructions when enforcement belongs in the harness.
- Keep portable skills narrow enough that they can move across tools without carrying unrelated project context or personal preferences.
- Record why durable instruction rules exist, which files or incidents they relate to, and when a human last confirmed them.
- Review stale instructions when libraries, incident decisions, architecture, or recurring patterns change.
- Point agents from durable instructions to maintained wiki context when the reusable knowledge is larger than a rule file should carry.
- Keep scheduled documentation refreshes provenance-backed so durable instructions can route to current compiled context without becoming source dumps.
- Separate repository-owned instructions, personal IDE preferences, centrally managed settings, hooks, and generated customization files.
- Review generated agent customization files before treating them as durable project policy.
- Label repo-local instruction files by owner and trust status before agents execute commands or access credentials because of them.
- Train developers to review generated skills, prompts, hooks, and rules before moving them into reusable durable guidance.
- Track owner, version, compatibility target, source location, and change history for skills or instruction files that become durable procedure.
- Route public skill registries, imported instruction bundles, allowed tool scope, and poisoned registry controls through supply-chain review before treating them as trusted instructions.
- Treat repository rule-file discovery as a coarse adoption signal, not proof of productive or correct agent use.
- Route PRD templates that define permissions, approval gates, logging, escalation, or eval-style done criteria through [executable PRD templates](../prompt-and-instructions/executable-prd-templates.md).
- Catalog internal skills by workflow, owner, validation evidence, standards coverage, and compatibility target before treating them as reusable procedure.
- Evaluate shared skills with representative tasks, edge cases, tool-use expectations, and regression checks before promoting them into durable team guidance.
- Audit durable instruction files for stale prompt debt and move recurring procedure into reviewed skills or wiki-backed guidance when progressive disclosure can carry it more safely.
- Keep root instruction files short enough to route agents to project rules, hooks, worktree boundaries, eval gates, and verification expectations without duplicating the durable wiki or every reusable skill.
- Treat plan-mode prompts, hooks, and eval commands as maintained instruction surfaces when they shape recurring agent behavior or acceptance gates.
- Store AI review standards and platform-specific guardrail skills as versioned, owner-reviewed instruction artifacts with verification steps and service constraints visible to reviewers.
- Promote third-party skills only after intake records name the owner, source snapshot, compatibility target, allowed tools, verification steps, and retirement criteria.
- Treat skill loading, skill updates, and skill retirement as execution-graph changes when they affect what an agent can do or how completion is verified.

## Authoritative Sources

- [Folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)
- [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json)
- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [August 7 topic news collector source](../../../raw/processed/2026-08-07/ai-dev-wiki-topic-news-collector-2026-08-07T203203-0400.json)
- [August 12 topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json)
- [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json)
- [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json)
- [August 23 topic news collector source](../../../raw/processed/2026-08-23/ai-dev-wiki-topic-news-collector-2026-08-24T003154Z.json)
- [August 23 leaf update watch source](../../../raw/processed/2026-08-23/ai-dev-wiki-leaf-update-watch-2026-08-23T210505-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption operating agreements](adoption-operating-agreements.md)
- [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [portable agent skills and runbooks](portable-agent-skills-and-runbooks.md)
- [research plan implement review lifecycle](../agent-workflows/research-plan-implement-review-lifecycle.md)
- [sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md)
- [executable PRD templates](../prompt-and-instructions/executable-prd-templates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed guidance on routers, rules layers, agent definitions, instructions, prompts, and skills.
- Maintained on 2026-06-23 to separate durable instruction placement from portable skill and runbook composition.
- Maintained on 2026-07-04 with instruction provenance, confirmation dates, and stale-rule review triggers.
- Maintained on 2026-07-05 with versionable codebase-wiki context and provenance-backed documentation refresh signals.
- Maintained on 2026-07-08 with generated customization review, hook boundaries, managed-setting separation, and provider-selection scope.
- Maintained on 2026-07-09 with repo-local instruction trust boundaries and generated customization review as developer skill practice.
- Maintained on 2026-07-17 with IDE-managed skills, source ownership, compatibility metadata, change history, and routing to supply-chain controls for registry and tool-scope risk.
- Maintained on 2026-07-27 with rule-file adoption caveats and executable PRD template review boundaries.
- Maintained on 2026-07-30 with internal-skill workflow ownership, standards, validation, and compatibility evidence.
- Maintained on 2026-08-07 with skill-eval workshop evidence for representative tasks, edge cases, tool-use expectations, and regression checks.
- Maintained on 2026-08-12 with prompt-debt auditing and progressive-disclosure cleanup as durable instruction maintenance.
- Maintained on 2026-08-20 with root instruction, plan-mode, hook, worktree, and eval routing evidence from startup operating-practice signals.
- Maintained on 2026-08-21 with repo-versioned review standards and platform-specific guardrail skill packaging.
- Maintained on 2026-08-23 with third-party skill intake, execution-graph, owner, compatibility, tool-scope, verification, and retirement criteria.
