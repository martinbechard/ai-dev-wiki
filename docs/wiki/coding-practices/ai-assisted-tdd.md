---
type: "Coding Practice"
title: "AI-Assisted TDD"
description: "TDD gives the agent a concrete design target."
tags: ["coding-practices"]
---

# AI-Assisted TDD

## Current Understanding

TDD gives the agent a concrete design target. A failing test turns an intended behavior, contract, edge case, or regression into executable acceptance criteria before implementation begins.

The local loop is to add or repair one meaningful failing test, implement the smallest code change that satisfies the test while keeping existing behavior intact, refactor the design, and rerun the relevant suite. The test output then becomes evidence for the next agent step.

The [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json) adds an agentic requirement-compilation lens. When requirements are large, multi-modal, or DSL-backed, tests should preserve traceability from source requirement to generated architecture, acceptance check, implementation, and verification result. Broad framework background belongs upstream; locally, TDD keeps requirement interpretation executable and reviewable.

The [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json) reinforces TDD as an AI coding stabilizer. Tests force design intent into executable constraints before the agent drafts implementation, and regression checks protect behavior when generated code is refactored or trimmed.

The [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json) adds acceptance-test ownership evidence from secondary commentary. Human review should stay focused on behavioral specifications, Gherkin-style acceptance tests, QA procedures, and criticality-scaled coverage when agents are allowed to draft unit tests and implementation code.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds compiler-diagnostic evidence for durable guardrails. When architecture rules, generated-code constraints, or framework conventions can be encoded as compiler or static-analysis diagnostics, those checks should supplement prompts so both humans and agents receive deterministic feedback during the TDD loop.

## Practice Boundaries

- Start with a failing test when behavior, contracts, regressions, or edge cases are being changed.
- Keep each test focused enough to narrow the agent task.
- Preserve existing passing behavior while implementing the smallest change that satisfies the failing test.
- Refactor names, types, modules, and duplication only after behavior is protected by tests.
- Rerun the relevant suite after implementation and after refactoring.
- Carry failure output into the next request package instead of asking the model to guess.
- Link generated tests to the source requirement or decision they protect when an agent turns requirements into code.
- Use failing tests to expose requirement interpretation errors before accepting generated architecture or implementation.
- Use tests and behavior inventories to constrain AI-generated refactors before large cleanup or bloat-removal passes.
- Keep humans accountable for acceptance criteria, QA procedures, and criticality-scaled coverage even when agents draft lower-level tests and implementation.
- Prefer compiler, type, lint, or static-analysis diagnostics for recurring architectural constraints when prompts alone would leave the rule advisory.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [Generated code refactoring](generated-code-refactoring.md)
- [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json)
- [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json)
- [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [fix branch and PR packaging](fix-branch-and-pr-packaging.md)
- [generated code refactoring](generated-code-refactoring.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on test-first agent work, regression repair, implementation, refactoring, and rerunning suites.
- Maintained on 2026-07-10 with requirement-to-test traceability for agentic requirement-compilation workflows.
- Maintained on 2026-07-11 with TDD as an executable constraint for AI-generated code cleanup and refactoring.
- Maintained on 2026-07-29 with human-owned acceptance-test, QA-procedure, and criticality-scaled coverage guidance.
- Maintained on 2026-07-30 with compiler and static-analysis diagnostics as deterministic AI-assisted TDD guardrails.
