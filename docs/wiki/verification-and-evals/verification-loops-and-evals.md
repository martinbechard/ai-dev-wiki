# Verification Loops And Evals

## Current Understanding

Verification is the evidence layer that lets AI-assisted outputs earn trust. For coding work, verification includes build, test, lint, runtime checks, source-backed claims, and review evidence. For AI application behavior, evals provide structured inputs, outputs, grading logic, and pass or score signals.

Evals can test releases or guide generation, and graders can be deterministic tools, human review, or model judges. Judgment-based grading needs clear boundaries because model explanations are not proof of internal reasoning. Broad benchmark and model-score catalogs belong upstream; this page owns the local practice of using verification and evals.

Detailed verification practice is split by maintenance path. [Verification tax and acceptance gates](verification-tax-and-acceptance-gates.md) owns the validation bottleneck, [code review evals and rubrics](code-review-evals-and-rubrics.md) owns review-specific scoring, [judge grader boundaries](judge-grader-boundaries.md) owns grader selection and LLM-as-judge governance, and [representative workflow calibration](representative-workflow-calibration.md) owns model and harness calibration.

## Practice Boundaries

- Run the checks that match the change surface before claiming completion.
- Treat tests as executable acceptance criteria when behavior matters.
- Use deterministic checks for syntax, imports, schemas, formatting, and known invariants.
- Use judgment-based graders only with explicit rubrics and source references.
- Separate creative generation from factual claims by grounding claims in source evidence.
- Report verification commands and material results in completion notes.
- Link specialized acceptance, review, judge, and calibration practices to their own leaves when they need independent maintenance.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [coding-practices](../coding-practices/index.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [governance-and-risk](../governance-and-risk/index.md)
- [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md)
- [code review evals and rubrics](code-review-evals-and-rubrics.md)
- [judge grader boundaries](judge-grader-boundaries.md)
- [representative workflow calibration](representative-workflow-calibration.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on verification, evals, graders, grounding, and done signals.
- Maintained on 2026-06-23 as the verification and eval overview after splitting acceptance, review, judge, and calibration leaves.
