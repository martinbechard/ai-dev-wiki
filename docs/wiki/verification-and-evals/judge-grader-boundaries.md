---
type: "Verification And Eval"
title: "Judge Grader Boundaries"
description: "Eval graders can be deterministic tools, human review, or model judges."
tags: ["verification-and-evals"]
---

# Judge Grader Boundaries

## Current Understanding

Eval graders can be deterministic tools, human review, or model judges. Deterministic checks include compilers, linters, type checkers, schema validators, unit tests, integration tests, static analysis, and security scans. Judgment checks include human review, product review, architecture review, rubric-based LLM-as-judge, and pair comparison.

LLM-as-judge is useful when there is no single ground truth, such as explanation quality, coherence, helpfulness, relevance, tone, safety, or competing design choices. It should be used with explicit rubrics, examples, and source references because a model's explanation is not proof that the judgment is correct.

Mature eval suites mix both signals. Hard checks measure correctness and policy, while judgment checks measure usefulness and semantic quality that is difficult to encode as rules.

The [evals source](../../../raw/processed/You’ll Finally Understand AI Evals After Watching This.md) adds the online versus offline scorer distinction. Offline scorers behave like regression tests over datasets or saved traces. Online scorers run against production traces or sampled live runs and behave more like monitoring. The local rule is to decide where a scorer runs based on cost, latency, risk, and whether the failure should block release or trigger operational review.

The [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) adds trace-linked judge practice. Judge scores are more useful when they are tied to the trace, retrieval context, tool calls, latency, cost, and failure reasons that produced the output. Bring-your-own judge providers are a governance choice because the judge can see sensitive traces and can influence release or monitoring decisions.

The [agent evals source](../../../raw/processed/Making Agent Evals Isn’t As Hard As You Think!.md) reinforces the step-versus-content scoring split. Deterministic graders should check exact tool calls, arguments, structures, and measurable output properties. LLM judges should score subjective process or content criteria only when the rubric, examples, and trace slice make the judgment auditable.

The [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json) adds current grader-comparison signals. Deterministic graders should own exact rules, schemas, and measurable properties, while LLM judges should be reserved for semantic quality or tradeoff judgments with calibrated rubrics and sampled human review. Human review remains the fallback when grader disagreement changes release, product, or security risk.

The [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json) adds adversarial-test and role-grounded-rubric evidence. Deterministic graders should still own generated adversarial tests and exact pass/fail outcomes, while human or calibrated model judges can score role-specific professional quality only when the rubric is derived from representative deliverables and disagreement is preserved with the trace.

The [August 27 leaf update watch source](../../../raw/processed/2026-08-27/ai-dev-wiki-leaf-update-watch-2026-08-27T210207-0400.json) adds two boundary signals. Terminal-agent training evidence emphasizes verifier quality and process-level behavior, while production secret-scanning evaluation uses LLM judgment only after calibration against production labels and deterministic security signals.

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
- Tie judge results to trace, retrieval, tool-call, latency, cost, and failure-reason evidence when the score affects release or monitoring decisions.
- Review judge-provider access to traces before using an external or bring-your-own judge in sensitive workflows.
- Decide whether the grader is scoring an agent step, an output artifact, a trace, or a thread before choosing deterministic assertions, human review, or an LLM judge.
- Use deterministic graders for exactness, LLM judges for calibrated semantic judgment, and human review for consequential grader disagreement.
- Keep grader disagreement, calibration examples, and human override reasons with the scored trace when the result affects release or security posture.
- Keep generated adversarial tests, role-grounded rubric sources, heterogeneous judge outputs, and human override reasons separate when a benchmark or domain eval combines hard correctness with professional judgment.
- Evaluate terminal-agent process traces with verifiers that can inspect behavior, not only final task success.
- Calibrate production LLM judges against labeled outcomes and deterministic security checks before their scores affect release or repair gates.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [verification loops and evals](verification-loops-and-evals.md)
- [code review evals and rubrics](code-review-evals-and-rubrics.md)
- [Evals source](../../../raw/processed/You’ll Finally Understand AI Evals After Watching This.md)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [Agent evals source](../../../raw/processed/Making Agent Evals Isn’t As Hard As You Think!.md)
- [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json)
- [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json)
- [August 27 leaf update watch source](../../../raw/processed/2026-08-27/ai-dev-wiki-leaf-update-watch-2026-08-27T210207-0400.json)

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
- Maintained on 2026-06-26 with trace-linked judge results and judge-provider governance.
- Maintained on 2026-06-30 with step, content, trace, and thread scoring boundaries for agent evals.
- Maintained on 2026-07-16 with deterministic-grader, LLM-judge, and human-review disagreement boundaries.
- Maintained on 2026-08-08 with adversarial-test, role-grounded-rubric, heterogeneous-judge, and trace-linked override boundaries.
- Maintained on 2026-08-27 with terminal-agent verifier-quality boundaries and production LLM-judge calibration against labels and deterministic security signals.
