# Coding Practices

## Current Understanding

Coding practices covers the engineering habits that make AI-assisted development reliable: TDD, regression repair, self-review, refactoring generated code, branch and PR packaging, and tier-specific conventions.

This topic owns local coding workflows and acceptance practices. It does not own catalogs of coding assistants or autonomous engineering platforms; those are upstream ecosystem entities unless a local workflow lens is needed here.

## Pattern Leaf Pages

- [ai-assisted-tdd.md](ai-assisted-tdd.md) records the test-first loop for agent work and regression repair.
- [intelligent-code-review.md](intelligent-code-review.md) records source-backed AI review, tier checks, coherence checks, and security review boundaries.
- [layered-ai-code-review-roles.md](layered-ai-code-review-roles.md) records developer, architecture, and security role separation for AI-assisted review.
- [structural-diff-review-for-ai-generated-code.md](structural-diff-review-for-ai-generated-code.md) records parser-aware diff triage for AI-generated commits and formatting churn.
- [generated-code-refactoring.md](generated-code-refactoring.md) records the practice of treating generated output as a draft until it fits local architecture and verification expectations.
- [fix-branch-and-pr-packaging.md](fix-branch-and-pr-packaging.md) records reproduction, scoped change packaging, regression coverage, and review-ready evidence for fixes.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [source-workflows](../source-workflows/index.md)
- [schema.md](../schema.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent-workflows](../agent-workflows/index.md)
- [verification-and-evals](../verification-and-evals/index.md)
- [governance-and-risk](../governance-and-risk/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 as the local owner for AI-assisted software engineering practice.
- Maintained on 2026-06-23 by splitting reusable coding practice concepts into durable leaf pages.
- Maintained on 2026-07-27 with layered AI code review roles as a durable leaf.
- Maintained on 2026-08-05 with structural diff review for AI-generated code as a durable leaf.
