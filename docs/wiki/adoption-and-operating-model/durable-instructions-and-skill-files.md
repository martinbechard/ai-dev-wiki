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
