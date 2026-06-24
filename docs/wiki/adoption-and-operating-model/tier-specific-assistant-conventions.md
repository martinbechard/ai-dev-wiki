# Tier Specific Assistant Conventions

## Current Understanding

Tier-specific assistant conventions specialize agent behavior for different work areas when those areas need distinct context, tools, verification, or approval. The stable rule is to specialize by work boundary and risk, not by preference for one assistant personality.

The current sources support specialized agents, model-specific instructions, tool descriptions, output constraints, and eval thresholds. They do not yet define a local taxonomy for frontend, backend, data, security, documentation, or other repository tiers. The exact repository tier taxonomy is Not yet identified.

Tier conventions should remain connected to [durable instructions and skill files](durable-instructions-and-skill-files.md) so agents can load the right procedure without copying every tier rule into each prompt.

## Practice Boundaries

- Create a tier convention only when the work area has different sources, tools, approvals, or verification checks.
- Keep tier guidance in durable instructions or skill files when it applies across tasks.
- Test model-specific or harness-specific behavior through the workflow checks instead of assuming one instruction works everywhere.
- Avoid creating parallel tier rules until the local taxonomy is identified.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [durable instructions and skill files](durable-instructions-and-skill-files.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption operating agreements](adoption-operating-agreements.md)
- [durable instructions and skill files](durable-instructions-and-skill-files.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md)

## Open Questions

- Which local work tiers need distinct assistant conventions is Not yet identified.

## Maintenance Notes

- Created on 2026-06-23 to separate tier-specific assistant behavior from the broader operating-agreement map while preserving the missing local taxonomy.
