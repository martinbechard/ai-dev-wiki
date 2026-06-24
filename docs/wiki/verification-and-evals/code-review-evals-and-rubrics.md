# Code Review Evals And Rubrics

## Current Understanding

AI-assisted code review evals measure whether a model or harness can inspect changes against the repository's standards, source evidence, and risk profile. They should test the review task itself, not only whether the model can produce plausible comments.

Useful review rubrics include correctness, source grounding, missing tests, security risk, architectural fit, maintainability, and whether the reviewer reports uncertainty instead of inventing evidence. The AI-assisted coding deck treats review as part of the controlled coding loop, and the Dwarf Star source is evidence that code review prompts can be part of representative model calibration.

This page owns review-specific eval practice. General grader selection lives in [judge grader boundaries](judge-grader-boundaries.md), and delivery acceptance gates live in [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md).

## Practice Boundaries

- Build review eval cases from real or representative changes, not only abstract review questions.
- Include source files, diffs, tests, logs, and repository rules that a reviewer should inspect.
- Grade whether findings are actionable, source-backed, and prioritized by risk.
- Penalize invented code paths, test results, security claims, or backlog status.
- Include cases where the correct review outcome is no finding plus residual risk.
- Keep broad benchmark catalogs upstream unless a benchmark changes local review practice.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [generated code refactoring](../coding-practices/generated-code-refactoring.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification-and-evals](index.md)
- [judge grader boundaries](judge-grader-boundaries.md)
- [representative workflow calibration](representative-workflow-calibration.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold AI-assisted code review eval and rubric practice.
