---
type: "Verification And Eval"
title: "Verification Loops And Evals"
description: "Verification is the evidence layer that lets AI-assisted outputs earn trust."
tags: ["verification-and-evals"]
---

# Verification Loops And Evals

## Current Understanding

Verification is the evidence layer that lets AI-assisted outputs earn trust. For coding work, verification includes build, test, lint, runtime checks, source-backed claims, and review evidence. For AI application behavior, evals provide structured inputs, outputs, grading logic, and pass or score signals.

Evals can test releases or guide generation, and graders can be deterministic tools, human review, or model judges. Judgment-based grading needs clear boundaries because model explanations are not proof of internal reasoning. Broad benchmark and model-score catalogs belong upstream; this page owns the local practice of using verification and evals.

Detailed verification practice is split by maintenance path. [Verification tax and acceptance gates](verification-tax-and-acceptance-gates.md) owns the validation bottleneck, [code review evals and rubrics](code-review-evals-and-rubrics.md) owns review-specific scoring, [judge grader boundaries](judge-grader-boundaries.md) owns grader selection and LLM-as-judge governance, and [representative workflow calibration](representative-workflow-calibration.md) owns model and harness calibration.

The [context loss source](../../../raw/processed/Your AI Agent Already Forgot Half of What You Told It.md) and [context collapse source](../../../raw/processed/When Context Collapses Teaching Agents to Detect and Recover from Lost Memory.md) reinforce acceptance criteria and deterministic continuity checks as verification primitives. A loop is trustworthy when the current artifact satisfies the done signal and the progress file agrees with the output, not when the agent says it remembers completing the steps.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) and [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) reinforce harness-level failure analysis and cost-sensitive verification. Agent failures should be attributed to task setup, context construction, tool constraints, scoring, observability, and review separation before they are blamed on model choice. Verification depth should scale with uncertainty, change risk, and verifier cost rather than becoming either a fixed checklist or an agent's own unsupported self-review.

The [harness engineering masterclass source](../../../raw/processed/Harness Engineering Masterclass Technical Deep Dive on how to build Agentic Systems.md) reinforces verification and observability as separate reliability primitives. A harness should ask for receipts such as tests, builds, screenshots, source tables, traces, tool timelines, cost, latency, prompt versions, and approval events. The local loop should turn repeated misses into stricter schemas, permission gates, memories, skills, or eval cases.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) adds a testing taxonomy for agentic workflows. Verification should distinguish AI-authored test artifacts, self-healing scripted tests, and fully agentic test loops where an agent plans, acts, observes runtime signals, and adapts without a hand-authored path underneath. Those modes need different evidence, ownership, and acceptance criteria.

## Practice Boundaries

- Run the checks that match the change surface before claiming completion.
- Treat tests as executable acceptance criteria when behavior matters.
- Use deterministic checks for syntax, imports, schemas, formatting, and known invariants.
- Use judgment-based graders only with explicit rubrics and source references.
- Separate creative generation from factual claims by grounding claims in source evidence.
- Report verification commands and material results in completion notes.
- Link specialized acceptance, review, judge, and calibration practices to their own leaves when they need independent maintenance.
- Use artifact-level acceptance criteria for multi-step agent tasks so completion can be checked after context pressure.
- Verify progress cursors against written outputs before resuming or declaring long-running work complete.
- Attribute failed agent runs to harness inputs, permissions, tools, scoring, and observability before changing models.
- Escalate from cheap diagnostics to expensive verification when uncertainty, risk, or reviewer cost justifies the extra evidence.
- Convert repeated verification failures into harness changes such as stronger schemas, permission gates, stored memories, reusable skills, or regression eval cases.
- Distinguish generated tests, self-healing scripted tests, and agentic runtime test loops before accepting test evidence.
- Require trace, observation, and path-choice evidence when a test agent owns the execution path rather than only authoring a script.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [Context loss source](../../../raw/processed/Your AI Agent Already Forgot Half of What You Told It.md)
- [Context collapse source](../../../raw/processed/When Context Collapses Teaching Agents to Detect and Recover from Lost Memory.md)
- [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json)
- [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json)
- [Harness engineering masterclass source](../../../raw/processed/Harness Engineering Masterclass Technical Deep Dive on how to build Agentic Systems.md)
- [context state externalization and rehydration](../context-architecture/context-state-externalization-and-rehydration.md)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)

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
- [context state externalization and rehydration](../context-architecture/context-state-externalization-and-rehydration.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on verification, evals, graders, grounding, and done signals.
- Maintained on 2026-06-23 as the verification and eval overview after splitting acceptance, review, judge, and calibration leaves.
- Maintained on 2026-06-27 with artifact-level acceptance criteria and progress-output continuity checks.
- Maintained on 2026-06-28 with harness-level failure attribution and cost-sensitive verification depth.
- Maintained on 2026-06-30 with receipts, traceability, and post-failure harness hardening guidance.
- Maintained on 2026-07-04 with generated-test, self-healing-script, and agentic-test-loop boundaries.
