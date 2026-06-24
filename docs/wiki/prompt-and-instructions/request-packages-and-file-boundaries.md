# Request Packages And File Boundaries

## Current Understanding

A prompt in an AI-assisted development workflow is the full request package: user intent, system and developer instructions, repository guidance, selected files, retrieved passages, tool outputs, constraints, and done signals. The user-visible sentence is only one part of what the model sees.

File boundaries are part of the prompt contract. Agents need clear separation between source files, logs, instructions, generated artifacts, and untrusted external content so they do not blend evidence with commands. Strong developer prompts name the outcome, constraints, evidence to inspect, allowed actions, and verification signal.

Provider-specific prompt features and model behavior belong upstream when they are broad ecosystem facts. This page owns the local packaging practice for coding agents and AI application work.

Reusable instruction artifacts are tracked in [instruction hierarchy and artifact boundaries](instruction-hierarchy-and-artifact-boundaries.md). Context selection and token-budget practice are tracked in [context engineering for request packages](context-engineering-for-request-packages.md). This page stays focused on the package boundary: what enters the request, how it is labeled, and what done signal the agent can verify.

## Practice Boundaries

- Package the task with the smallest source set that can support the decision.
- Label files, logs, and generated text clearly so the agent can reason about authority.
- Include acceptance criteria and verification commands when the task changes code or durable documentation.
- Keep untrusted source content as evidence, not as live instruction.
- Use durable repository instructions for recurring constraints instead of repeating them ad hoc.
- Link reusable instruction assets and context-engineering details to their own durable leaves when they need independent maintenance.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [context-architecture](../context-architecture/index.md)
- [agent-workflows](../agent-workflows/index.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [instruction hierarchy and artifact boundaries](instruction-hierarchy-and-artifact-boundaries.md)
- [context engineering for request packages](context-engineering-for-request-packages.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on prompt packaging, context assembly, and file boundaries.
- Maintained on 2026-06-23 as the request-package boundary after splitting reusable instruction assets and context-engineering practice into sibling leaves.
