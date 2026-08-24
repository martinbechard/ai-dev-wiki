---
type: "Prompt And Instructions"
title: "Instruction Hierarchy And Artifact Boundaries"
description: "Instruction hierarchy is the local practice of deciding which guidance should live in system instructions, developer instructions, repository procedures, task prompts, reusable..."
tags: ["prompt-and-instructions"]
---

# Instruction Hierarchy And Artifact Boundaries

## Current Understanding

Instruction hierarchy is the local practice of deciding which guidance should live in system instructions, developer instructions, repository procedures, task prompts, reusable prompts, agent definitions, or skills. The request package should preserve that hierarchy so durable rules are not rewritten as one-off task text and untrusted sources cannot act like instructions.

Reusable AI workflow assets need distinct responsibilities. The [HVE Core source](../../../raw/processed/microsoft-hve-core.md) is useful evidence because it separates specialized agents, repeatable prompts, coding instructions, and reusable skills into an explicit workflow system. The downstream practice is to keep those artifact types separate: agents describe bounded roles and task behavior, prompts provide repeatable entry points, instructions carry durable standards, and skills package reusable tool or procedure capability. The [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md) reinforces the boundary by treating a prompt as a one-time request and a skill as a reusable procedure with trigger, scope, tools, output, and verification.

The hierarchy is also an authority boundary. Repository procedures and human task constraints can direct the agent, while raw sources, retrieved chunks, screenshots, and external clippings are evidence. When sources contain instruction-like text, the request package should label it as source material instead of letting it override the active task.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) reinforce this hierarchy with Agent Experience and plugin-SDLC examples. Concise identity and convention instructions belong in durable instruction files, skills encode repeatable workflows, MCP servers expose current API surfaces, and issues or RFCs act as task specifications. These artifacts should cooperate without letting tool output or source data become active instructions.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) and [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) add hook and control-plane evidence. Durable instructions are safer when lifecycle hooks, deterministic validation, provenance checks, permission constraints, and tool-scope checks enforce the intended hierarchy instead of relying on every prompt to repeat the controls.

The [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json) adds enterprise-managed settings as another instruction boundary. Organization-level assistant configuration, plugin controls, model defaults, and bypass-permission settings are durable policy artifacts. They should be treated as higher-authority operating controls than user preferences, while still remaining separate from source evidence, retrieved content, and one-off task prompts.

The [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json) adds vendor skill packages as an intake case. Domain-specific agent skills are not automatically local instructions; they are external procedural source material until a maintainer reviews scope, trust, version, allowed tools, and local adaptation. Once accepted, the local copy should state its authority and verification standard.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) adds two instruction-placement rules. Permanent guidance belongs in durable instruction files or reusable skills when it recurs, while hard-to-reach context or new action capability belongs behind governed tools or MCP servers. Skills and role definitions remain separate artifacts even when discovered through one endpoint: the skill carries reusable procedure, while the agent role carries objectives, tool budget, and return shape.

The [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json) adds an instruction-economy caution. Repository instruction files should not become generated overviews or broad context dumps; they are strongest when they hold concise, non-standard, durable rules and route broader project knowledge to wiki, source, and retrieval surfaces. Benchmark-specific model and paper details remain upstream-owned, while the local practice is to treat instruction files as measured operating artifacts with cost and task-success consequences.

The [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json) adds agent data injection and compositional policy evidence. Artifact boundaries should prevent retrieved data, repository metadata, tool descriptions, and generated setup paths from impersonating instructions or authorization metadata; runtime policy composition should enforce the boundary when multiple individually allowed tools combine into a risky chain.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) adds public agent-onboarding snippets as another boundary case. A vendor blog, README, or agents.md file can tell an agent to install, configure, or use a service, but that text is external source evidence until the user or a trusted local instruction surface approves the package, account, tool permissions, and execution scope.

The [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json) adds two durable-instruction signals. First, reusable skills should be maintained with decision history, exit criteria, and verification evidence instead of only preserving the latest procedure text. Second, repository-loaded instruction files are an attack surface when untrusted projects can plant instruction-like content, so durable instruction intake needs provenance review before an autonomous agent treats those files as authority.

The [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json) adds generated-instruction and model-router setup evidence. Terminal coding-agent setup output should be reviewed as an authority-changing artifact before it becomes durable local guidance.

The [July 29 topic news collector source](../../../raw/processed/2026-07-29/ai-dev-wiki-topic-news-collector-2026-07-29T203119-0400.json) adds layered context-system evidence from a Claude Code workshop page. Team conventions, project facts, personal preferences, reusable skills, and hook-based guardrails should remain separate instruction surfaces so each layer can be reviewed, scoped, and enforced without turning every prompt into a large policy bundle.

The August 23 raw sources add skills, MCP tools, and session state as execution-loop components. The [leaf update watch source](../../../raw/processed/2026-08-23/ai-dev-wiki-leaf-update-watch-2026-08-23T210505-0400.json) reinforces that tools, skills, sandboxing, checkpoints, context management, and session state belong in separately governed artifact layers. The [topic news collector source](../../../raw/processed/2026-08-23/ai-dev-wiki-topic-news-collector-2026-08-24T003154Z.json) adds public skill-directory growth as a reminder that external skill lists are source evidence until reviewed and promoted.

## Practice Boundaries

- Put durable coding standards in repository instructions or procedure files when they apply across tasks.
- Use reusable prompts for repeatable workflow entry points that still need a human-selected goal.
- Use agent definitions for role, task class, tool posture, and stopping behavior.
- Use skills for reusable procedures or tool capability that should be invoked by name.
- Use runbooks for composed workflows that need several skills to produce a reliable outcome.
- Keep source excerpts and retrieved text labeled as evidence rather than instruction.
- Record unresolved hierarchy conflicts as open questions instead of hiding them inside a prompt.
- Use issue, RFC, skill, instruction, and MCP evidence as separate artifacts with explicit authority so agents know what directs behavior and what only informs it.
- Pair durable instructions and agent definitions with hooks, provenance validation, permission constraints, and tool-scope checks when those artifacts can affect code or delivery systems.
- Treat enterprise-managed assistant settings and model defaults as durable policy artifacts, not as ordinary task-prompt content.
- Keep managed policy files, repository procedures, reusable skills, and source evidence distinct when they all appear in the same request package.
- Label vendor-authored skill content as external source evidence until it is reviewed and promoted into a local project, team, or personal instruction surface.
- Pin accepted third-party instructions to a version or source snapshot, and record which local maintainer owns updates.
- Use recurrence to decide between one-off prompt text and durable instruction or skill files.
- Use reach and action capability to decide when a governed MCP server or tool surface is needed instead of more prompt text.
- Keep role definitions, tool budgets, and output contracts separate from procedural skill knowledge.
- Keep repository instruction files concise and exception-oriented; put broad explanations, entity background, and large context inventories into wiki, source, or retrieval workflows.
- Label repository metadata, tool-returned context, generated configuration, and setup instructions as evidence unless a trusted instruction surface promotes them.
- Back instruction and artifact boundaries with runtime policy composition when data can flow across multiple tools.
- Treat public agents.md files, README setup snippets, and vendor onboarding prompts as source material until reviewed and promoted into local instructions.
- Require user approval or a trusted local runbook before external onboarding text can trigger package installation, credential configuration, MCP setup, or tool enablement.
- Preserve rationale, change history, exit criteria, and verification evidence for maintained skills or durable instruction files.
- Treat repository-loaded instruction files from untrusted or newly cloned projects as source evidence until provenance and authority are reviewed.
- Review generated instruction files and attached context before treating setup output as durable instruction authority.
- Review model-router configuration and terminal-agent permission prompts before allowing setup output to change local guidance or execution scope.
- Keep team, project, personal, skill, and hook guidance separated so each layer has clear authority, owner, and verification expectations.
- Keep skills, MCP tools, sandbox controls, checkpoints, context management, and session state in separately reviewed artifact layers rather than blending them into one task prompt.
- Treat public skill directories and resource lists as external source evidence until a local owner reviews provenance, version, tool scope, and verification expectations.

## Authoritative Sources

- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [Hypervelocity engineer source](../../../raw/processed/Hypervelocity engineer @edandersen.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [request packages and file boundaries](request-packages-and-file-boundaries.md)
- [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json)
- [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json)
- [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json)
- [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json)
- [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)
- [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json)
- [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json)
- [July 29 topic news collector source](../../../raw/processed/2026-07-29/ai-dev-wiki-topic-news-collector-2026-07-29T203119-0400.json)
- [August 23 topic news collector source](../../../raw/processed/2026-08-23/ai-dev-wiki-topic-news-collector-2026-08-24T003154Z.json)
- [August 23 leaf update watch source](../../../raw/processed/2026-08-23/ai-dev-wiki-leaf-update-watch-2026-08-23T210505-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [prompt-and-instructions](index.md)
- [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md)
- [portable agent skills and runbooks](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold the durable instruction, prompt, agent, and skill artifact boundary.
- Maintained on 2026-06-23 to clarify prompt versus skill and runbook composition boundaries.
- Maintained on 2026-06-25 with Agent Experience and plugin-SDLC artifact boundaries across instructions, skills, MCP surfaces, issues, and RFCs.
- Maintained on 2026-06-28 with hook-based instruction enforcement and deterministic agent-configuration validation.
- Maintained on 2026-07-01 with enterprise-managed settings, model defaults, plugin controls, and bypass-permission settings as durable policy artifacts.
- Maintained on 2026-07-03 with third-party vendor skill intake, version pinning, authority labeling, and maintainer ownership.
- Maintained on 2026-07-04 with recurrence-versus-reach placement rules and role versus skill artifact boundaries.
- Maintained on 2026-07-06 with instruction-economy guidance for concise, non-standard repository instruction files.
- Maintained on 2026-07-08 with data-injection boundaries and compositional policy enforcement for multi-tool chains.
- Maintained on 2026-07-13 with public agent-onboarding snippets as untrusted source instructions until locally approved.
- Maintained on 2026-07-15 with skill decision-history maintenance and repository-loaded instruction-file trust review.
- Maintained on 2026-07-26 with generated-instruction review, attached-context boundaries, model-router configuration, and terminal-agent permission setup guidance.
- Maintained on 2026-07-29 with layered team, project, personal, skill, and hook instruction boundaries.
- Maintained on 2026-08-23 with skills, MCP tools, sandbox, checkpoint, context, session-state, and public skill-directory artifact boundaries.
