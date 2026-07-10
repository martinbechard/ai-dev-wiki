---
type: "Prompt And Instructions"
title: "Request Packages And File Boundaries"
description: "A prompt in an AI-assisted development workflow is the full request package: user intent, system and developer instructions, repository guidance, selected files, retrieved..."
tags: ["prompt-and-instructions"]
---

# Request Packages And File Boundaries

## Current Understanding

A prompt in an AI-assisted development workflow is the full request package: user intent, system and developer instructions, repository guidance, selected files, retrieved passages, tool outputs, constraints, and done signals. The user-visible sentence is only one part of what the model sees.

File boundaries are part of the prompt contract. Agents need clear separation between source files, logs, instructions, generated artifacts, and untrusted external content so they do not blend evidence with commands. Strong developer prompts name the outcome, constraints, evidence to inspect, allowed actions, and verification signal.

Provider-specific prompt features and model behavior belong upstream when they are broad ecosystem facts. This page owns the local packaging practice for coding agents and AI application work.

Reusable instruction artifacts are tracked in [instruction hierarchy and artifact boundaries](instruction-hierarchy-and-artifact-boundaries.md). Context selection and token-budget practice are tracked in [context engineering for request packages](context-engineering-for-request-packages.md). This page stays focused on the package boundary: what enters the request, how it is labeled, and what done signal the agent can verify.

The [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) adds two packaging rules. First, KPR-style knowledge packages should carry source code, tests, cleaned traces, and provenance as evidence while the receiving project regenerates implementation under local context. Second, prompt and provenance artifacts can affect human review behavior, so review packages should include the relevant prompt, source labels, and generation context when AI-generated code is being assessed.

The [context loss source](../../../raw/processed/Your AI Agent Already Forgot Half of What You Told It.md) and [lost-in-the-middle source](../../../raw/processed/So Long and Thanks for All the Context.md) add two request-package rules. First, use an acceptance criterion as the done signal when a procedure has several steps, because the agent can check the current artifact even if it loses track of the sequence. Second, restate source-read requirements near the action that needs them, especially when exact fields must be copied from a source file rather than paraphrased from memory.

The [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json) adds a repo-local instruction boundary. Request packages should label AGENTS.md, generated skill files, workspace customizations, and other repository-provided instructions by trust status and source authority before the agent treats them as live procedure.

## Practice Boundaries

- Package the task with the smallest source set that can support the decision.
- Label files, logs, and generated text clearly so the agent can reason about authority.
- Include acceptance criteria and verification commands when the task changes code or durable documentation.
- Keep untrusted source content as evidence, not as live instruction.
- Use durable repository instructions for recurring constraints instead of repeating them ad hoc.
- Link reusable instruction assets and context-engineering details to their own durable leaves when they need independent maintenance.
- Include prompt and provenance artifacts when they are part of the evidence reviewers need to understand AI-generated work.
- Keep incoming knowledge packages separate from local implementation instructions until the project accepts them through verification.
- Prefer acceptance criteria that can be checked against artifacts over fragile step counts in long sessions.
- Put exact source-read instructions next to the write, review, or merge action that depends on the source.
- Use handoff files as request-package inputs for fresh sessions instead of continuation prompts that assume prior chat memory.
- Label repo-local instructions, generated skill files, workspace customizations, and third-party repository guidance as trusted instruction, local evidence, or untrusted source content before use.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [Context loss source](../../../raw/processed/Your AI Agent Already Forgot Half of What You Told It.md)
- [Lost-in-the-middle source](../../../raw/processed/So Long and Thanks for All the Context.md)
- [context state externalization and rehydration](../context-architecture/context-state-externalization-and-rehydration.md)
- [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json)

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
- [context state externalization and rehydration](../context-architecture/context-state-externalization-and-rehydration.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on prompt packaging, context assembly, and file boundaries.
- Maintained on 2026-06-23 as the request-package boundary after splitting reusable instruction assets and context-engineering practice into sibling leaves.
- Maintained on 2026-06-26 with KPR-style knowledge-package boundaries and prompt provenance as review evidence.
- Maintained on 2026-06-27 with acceptance criteria, point-of-use source-read instructions, and handoff-file packaging for context pressure.
- Maintained on 2026-07-09 with trust labels for repo-local instructions, generated skill files, workspace customizations, and third-party repository guidance.
