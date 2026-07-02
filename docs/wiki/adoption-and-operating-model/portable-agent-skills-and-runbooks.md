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

## Practice Boundaries

- Use a one-off prompt for one-time work and a skill when a procedure recurs across sessions, tools, or agents.
- Avoid turning every preference into a skill; preserve only recurring procedures that have a non-obvious trigger, boundary, or verification rule.
- Keep skill files inspectable and scoped so they can be carried between tools without copying unrelated project context.
- Use runbooks when multiple skills must be composed into an outcome that needs handoff, publishing, release, research, or review.
- Treat verification as part of the skill contract, not as optional completion prose.
- Keep Open Skills as source evidence for the local practice lens; broad ecosystem tracking for agent tools and product catalogs remains upstream.
- Store recurring procedures where the team can review ownership, trigger rules, tool requirements, and verification expectations.
- Avoid vendor-local procedure drift by keeping portable runbooks aligned with project or team source-of-truth rules.

## Authoritative Sources

- [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md)
- [durable instructions and skill files](durable-instructions-and-skill-files.md)
- [instruction hierarchy and artifact boundaries](../prompt-and-instructions/instruction-hierarchy-and-artifact-boundaries.md)
- [verification tax and acceptance gates](../verification-and-evals/verification-tax-and-acceptance-gates.md)
- [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json)

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

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed guidance on portable procedures, runbook composition, scope boundaries, procedural debt, and proof standards for agent work.
- Maintained on 2026-07-01 with portable procedure ownership, trigger rules, required tools, and verification standards.
