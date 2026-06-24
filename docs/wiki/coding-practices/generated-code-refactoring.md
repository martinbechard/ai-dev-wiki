# Generated Code Refactoring

## Current Understanding

Generated code is a draft unless it already fits the architecture, conventions, and verification bar. AI-assisted development should refactor generated output into maintainable code instead of preserving awkward structure because it came from a model.

The local practice is to keep compatibility strategies simple during greenfield work, remove obsolete types and functions, and let tests, builds, and review evidence decide whether the result is acceptable. [AI-assisted TDD](ai-assisted-tdd.md), [intelligent code review](intelligent-code-review.md), and [fix branch and PR packaging](fix-branch-and-pr-packaging.md) own the sibling practices that often surround this refactoring work.

Broad catalogs of coding assistants stay in the upstream AI wiki; this page owns the downstream engineering practice for turning a useful generated result into maintainable code.

The [coding agents change source](../../../raw/processed/How are coding agents changing software engineering?.md) adds a scale warning: coding agents can produce larger pull requests, persistent generated code, and rising tool-call volume. The local implication is not to reject agent output, but to keep generated changes small enough to review, remove unnecessary code, and measure success by merged, reviewed, maintainable work rather than raw lines produced.

## Practice Boundaries

- Refactor generated code toward the repository's existing patterns before treating it as finished.
- Prefer deleting obsolete paths over keeping parallel code when the project has no compatibility requirement.
- Preserve the useful behavior with examples, screenshots, tests, or user flows before restructuring.
- Use build, tests, lint, browser checks, and human review so cleanup keeps the useful outcome intact.
- Treat attractive generated output as a prototype or reference implementation until the architecture and verification bar are satisfied.
- Keep AI-assisted pull requests small enough for meaningful review when possible.
- Watch for unnecessary compatibility layers, generated artifacts, lockfile churn, and defensive code that the task does not need.
- Treat accepted generated code as sticky code that will carry maintenance cost unless reviewed and simplified.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Coding agents change source](../../../raw/processed/How are coding agents changing software engineering?.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent-workflows](../agent-workflows/index.md)
- [governance-and-risk](../governance-and-risk/index.md)
- [ai-assisted TDD](ai-assisted-tdd.md)
- [intelligent code review](intelligent-code-review.md)
- [fix branch and PR packaging](fix-branch-and-pr-packaging.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on TDD, review assistants, generated code, and branch packaging.
- Maintained on 2026-06-23 as the generated-output refactoring leaf after splitting adjacent TDD, review, and fix-packaging practices.
