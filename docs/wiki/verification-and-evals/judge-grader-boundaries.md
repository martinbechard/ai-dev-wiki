# Judge Grader Boundaries

## Current Understanding

Eval graders can be deterministic tools, human review, or model judges. Deterministic checks include compilers, linters, type checkers, schema validators, unit tests, integration tests, static analysis, and security scans. Judgment checks include human review, product review, architecture review, rubric-based LLM-as-judge, and pair comparison.

LLM-as-judge is useful when there is no single ground truth, such as explanation quality, coherence, helpfulness, relevance, tone, safety, or competing design choices. It should be used with explicit rubrics, examples, and source references because a model's explanation is not proof that the judgment is correct.

Mature eval suites mix both signals. Hard checks measure correctness and policy, while judgment checks measure usefulness and semantic quality that is difficult to encode as rules.

The [evals source](../../../raw/processed/You’ll Finally Understand AI Evals After Watching This.md) adds the online versus offline scorer distinction. Offline scorers behave like regression tests over datasets or saved traces. Online scorers run against production traces or sampled live runs and behave more like monitoring. The local rule is to decide where a scorer runs based on cost, latency, risk, and whether the failure should block release or trigger operational review.

## Practice Boundaries

- Prefer deterministic graders for syntax, imports, schemas, formats, policies, and executable invariants.
- Use LLM judges only when the target quality cannot be captured by a deterministic check.
- Give judges explicit rubrics, examples, source evidence, and expected failure modes.
- Keep judge outputs as evaluation evidence, not as proof of hidden reasoning.
- Calibrate judgment graders with examples and spot checks before relying on scores.
- Mix hard gates and judgment checks when both correctness and usefulness matter.
- Treat offline scorer suites as regression evidence and online scorers as monitoring evidence.
- Sample expensive LLM judges when online coverage is useful but per-run scoring is too costly.
- Store failure reasons with scored traces so failures can become dataset items for future regression checks.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [verification loops and evals](verification-loops-and-evals.md)
- [code review evals and rubrics](code-review-evals-and-rubrics.md)
- [Evals source](../../../raw/processed/You’ll Finally Understand AI Evals After Watching This.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification-and-evals](index.md)
- [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md)
- [representative workflow calibration](representative-workflow-calibration.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold deterministic grader, human review, and LLM-as-judge boundaries.
