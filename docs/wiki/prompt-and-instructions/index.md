# Prompt And Instructions

## Current Understanding

Prompt and instructions covers the full request package sent to an AI assistant, not only the sentence typed by the developer. The local scope includes system prompts, developer prompts, repository instructions, task constraints, file boundaries, source labels, and done signals.

This topic owns durable instruction patterns and prompt packaging guidance for AI-assisted development. Provider-specific prompt features, model families, and broad SDK behavior stay upstream unless a local practice decision depends on them.

## Pattern Leaf Pages

- [request-packages-and-file-boundaries.md](request-packages-and-file-boundaries.md) records the request package, file boundary, source-label, and done-signal pattern.
- [instruction-hierarchy-and-artifact-boundaries.md](instruction-hierarchy-and-artifact-boundaries.md) records how durable instructions, agents, prompts, and skills stay separated.
- [context-engineering-for-request-packages.md](context-engineering-for-request-packages.md) records how project data, conventions, and evidence are selected for a request.
- [executable-prd-templates.md](executable-prd-templates.md) records PRD template fields that become controlled implementation inputs for coding agents.
- [portable-agent-skills-and-runbooks.md](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md) records the adoption lens for reusable procedure skills and composed runbooks.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Hypervelocity engineer source](../../../raw/processed/Hypervelocity engineer @edandersen.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md)
- [context-architecture](../context-architecture/index.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [context-architecture](../context-architecture/index.md)
- [agent-workflows](../agent-workflows/index.md)
- [governance-and-risk](../governance-and-risk/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 as the local owner for prompt and instruction patterns.
- Maintained on 2026-06-23 to separate request packaging, context engineering, and reusable instruction artifacts into durable leaves.
- Maintained on 2026-06-23 to link prompt boundaries to portable skill and runbook practice.
- Maintained on 2026-07-27 with executable PRD templates as a durable leaf.
