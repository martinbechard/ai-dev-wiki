---
type: "Coding Practice"
title: "Generated Code Refactoring"
description: "Generated code is a draft unless it already fits the architecture, conventions, and verification bar."
tags: ["coding-practices"]
---

# Generated Code Refactoring

## Current Understanding

Generated code is a draft unless it already fits the architecture, conventions, and verification bar. AI-assisted development should refactor generated output into maintainable code instead of preserving awkward structure because it came from a model.

The local practice is to keep compatibility strategies simple during greenfield work, remove obsolete types and functions, and let tests, builds, and review evidence decide whether the result is acceptable. [AI-assisted TDD](ai-assisted-tdd.md), [intelligent code review](intelligent-code-review.md), and [fix branch and PR packaging](fix-branch-and-pr-packaging.md) own the sibling practices that often surround this refactoring work.

Broad catalogs of coding assistants stay in the upstream AI wiki; this page owns the downstream engineering practice for turning a useful generated result into maintainable code.

The [coding agents change source](../../../raw/processed/How are coding agents changing software engineering?.md) adds a scale warning: coding agents can produce larger pull requests, persistent generated code, and rising tool-call volume. The local implication is not to reject agent output, but to keep generated changes small enough to review, remove unnecessary code, and measure success by merged, reviewed, maintainable work rather than raw lines produced.

The [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json) adds a compliance and traceability lens. Ordinary coding assistance may not be the same as regulated high-risk AI use, but generated-code practice should preserve documentation, traceability, review, and human oversight records when code is connected to regulated, employment, worker-management, or other sensitive workflows.

The [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json) reinforces the same scale risk from a governance angle. As organizations generate and ship more AI-written code, the limiting factor becomes control, security, provenance, review capacity, and maintainability rather than raw generation speed.

The [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) adds maintainer-policy pressure around AI-authored code. Locally, generated-code refactoring should produce code the submitter can explain, test, repair, and own. Passing review feedback back to an agent without understanding the change is not enough when maintainers require accountability for authorship and fix quality.

The [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json) adds behavior-inventory and TDD reinforcement. Refactoring generated code should start by preserving what the application currently does, turning that behavior inventory into regression checks where possible, then pruning bloat under lint, CI, instruction-file, and human-review guardrails. The goal is maintainable behavior-preserving code, not a raw line-count reduction.

## Practice Boundaries

- Refactor generated code toward the repository's existing patterns before treating it as finished.
- Prefer deleting obsolete paths over keeping parallel code when the project has no compatibility requirement.
- Preserve the useful behavior with examples, screenshots, tests, or user flows before restructuring.
- Use build, tests, lint, browser checks, and human review so cleanup keeps the useful outcome intact.
- Treat attractive generated output as a prototype or reference implementation until the architecture and verification bar are satisfied.
- Keep AI-assisted pull requests small enough for meaningful review when possible.
- Watch for unnecessary compatibility layers, generated artifacts, lockfile churn, and defensive code that the task does not need.
- Treat accepted generated code as sticky code that will carry maintenance cost unless reviewed and simplified.
- Preserve traceability from generated code to requirements, review evidence, tests, and human acceptance when the workflow has regulatory or workforce implications.
- Keep legal and provider background upstream; locally, record the engineering evidence needed to support oversight.
- Treat governance, review capacity, provenance, and maintainability as acceptance criteria for generated code, not as cleanup work after merge.
- Require a human owner who can explain, repair, and maintain generated code before it is packaged for review.
- Treat undisclosed or unowned generated code as not review-ready when project policy requires contributor accountability.
- Build or confirm a behavior inventory before deleting generated code at scale.
- Use regression checks, lint, CI, instruction files, and human review as guardrails when trimming generated-code bloat.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Coding agents change source](../../../raw/processed/How are coding agents changing software engineering?.md)
- [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json)
- [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json)
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
- [lifecycle AI review gates](../governance-and-risk/lifecycle-ai-review-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on TDD, review assistants, generated code, and branch packaging.
- Maintained on 2026-06-23 as the generated-output refactoring leaf after splitting adjacent TDD, review, and fix-packaging practices.
- Maintained on 2026-06-24 with documentation, traceability, and human oversight implications for sensitive generated-code workflows.
- Maintained on 2026-06-29 with governance, review-capacity, provenance, and maintainability risks for generated code at scale.
- Maintained on 2026-07-07 with contributor-accountability, authorship, and repair-ownership requirements for generated code.
- Maintained on 2026-07-11 with behavior inventory, regression-check, CI, lint, and human-review guardrails for generated-code cleanup.
