# Fix Branch And PR Packaging

## Current Understanding

Fix assistants are easier to trust when reproduction, scope, patch, tests, and verification evidence are explicit. The local practice is to prove the problem before editing, keep the change scoped to one concern, add or repair regression coverage, and package the result with enough evidence for review.

This page records the coding practice. Repository-specific branch naming, hosting workflows, and pull request automation are project-specific source-workflow concerns when they exist.

## Practice Boundaries

- Reproduce the bug with a failing test, compile error, browser issue, log line, screenshot mismatch, or user scenario before editing.
- Scope the work to one concern and keep unrelated cleanup out of the change.
- Patch the smallest owning module unless the design requires a broader refactor.
- Add or repair regression coverage when behavior changed or drifted.
- Report build, test, lint, runtime, and review evidence with the fix.
- Package review notes around reproduction, scope, patch, verification, and remaining risk.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Generated code refactoring](generated-code-refactoring.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [ai-assisted TDD](ai-assisted-tdd.md)
- [intelligent code review](intelligent-code-review.md)
- [source-workflows](../source-workflows/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on fix assistants, branch scope, regression coverage, and review-ready evidence.
