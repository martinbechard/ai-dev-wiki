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

## Practice Boundaries

- Start with a failing test when behavior, contracts, regressions, or edge cases are being changed.
- Keep each test focused enough to narrow the agent task.
- Preserve existing passing behavior while implementing the smallest change that satisfies the failing test.
- Refactor names, types, modules, and duplication only after behavior is protected by tests.
- Rerun the relevant suite after implementation and after refactoring.
- Carry failure output into the next request package instead of asking the model to guess.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [Generated code refactoring](generated-code-refactoring.md)

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
