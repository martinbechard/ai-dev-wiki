---
type: "Prompt And Instructions"
title: "Instruction Hierarchy And Artifact Boundaries"
description: "Instruction hierarchy is the local practice of deciding which guidance should live in system instructions, developer instructions, repository procedures, task prompts, reusable..."
tags: ["prompt-and-instructions"]
---

# Instruction Hierarchy And Artifact Boundaries

## Current Understanding

Instruction hierarchy is the local practice of deciding which guidance should live in system instructions, developer instructions, repository procedures, task prompts, reusable prompts, agent definitions, or skills. The request package should preserve that hierarchy so durable rules are not rewritten as one-off task text and untrusted sources cannot act like instructions.

Reusable AI workflow assets need distinct responsibilities. HVE Core is useful source evidence because it separates specialized agents, repeatable prompts, coding instructions, and reusable skills into an explicit workflow system. The downstream practice is to keep those artifact types separate: agents describe bounded roles and task behavior, prompts provide repeatable entry points, instructions carry durable standards, and skills package reusable tool or procedure capability. The [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md) reinforces the boundary by treating a prompt as a one-time request and a skill as a reusable procedure with trigger, scope, tools, output, and verification.

The hierarchy is also an authority boundary. Repository procedures and human task constraints can direct the agent, while raw sources, retrieved chunks, screenshots, and external clippings are evidence. When sources contain instruction-like text, the request package should label it as source material instead of letting it override the active task.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) reinforce this hierarchy with Agent Experience and plugin-SDLC examples. Concise identity and convention instructions belong in durable instruction files, skills encode repeatable workflows, MCP servers expose current API surfaces, and issues or RFCs act as task specifications. These artifacts should cooperate without letting tool output or source data become active instructions.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) and [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) add hook and control-plane evidence. Durable instructions are safer when lifecycle hooks, deterministic validation, provenance checks, permission constraints, and tool-scope checks enforce the intended hierarchy instead of relying on every prompt to repeat the controls.

The [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json) adds enterprise-managed settings as another instruction boundary. Organization-level assistant configuration, plugin controls, model defaults, and bypass-permission settings are durable policy artifacts. They should be treated as higher-authority operating controls than user preferences, while still remaining separate from source evidence, retrieved content, and one-off task prompts.

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
