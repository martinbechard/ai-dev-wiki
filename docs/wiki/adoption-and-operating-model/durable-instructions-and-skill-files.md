# Durable Instructions And Skill Files

## Current Understanding

Durable instructions and skill files keep reusable procedure outside the live prompt until an agent needs it. They give the assistant stable role, scope, project rules, references, tool expectations, safety boundaries, and examples without forcing every request to carry every rule.

The folder-organization source describes a thin router that points agents toward task-relevant rules, knowledge, decisions, references, active plans, and archives. The AI-assisted coding deck describes agent definition files as the place for role, scope, project rules, important references, tool expectations, safety configuration, and examples. HVE Core shows the same pattern as a packaged workflow system with agents, prompts, instructions, and skills.

The [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md) adds the portability boundary: reusable procedure should not be trapped in one agent product or copied into drifting tool-specific rule files. This page owns the adoption practice for durable instruction surfaces, while [portable agent skills and runbooks](portable-agent-skills-and-runbooks.md) owns the skill primitive, runbook composition, and procedural-debt lens. [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md) owns the context architecture, and [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md) owns how live requests label source material.

## Practice Boundaries

- Move stable procedures into durable instruction surfaces once they are reused across tasks.
- Keep the root router thin so it sends agents to the right guidance instead of becoming an overloaded prompt.
- Store active work, decisions, references, and archive material by lifespan so agents do not confuse historical plans with current instructions.
- Keep safety and permission configuration distinct from prose instructions when enforcement belongs in the harness.
- Keep portable skills narrow enough that they can move across tools without carrying unrelated project context or personal preferences.

## Authoritative Sources

- [Folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md)

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

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed guidance on routers, rules layers, agent definitions, instructions, prompts, and skills.
- Maintained on 2026-06-23 to separate durable instruction placement from portable skill and runbook composition.
