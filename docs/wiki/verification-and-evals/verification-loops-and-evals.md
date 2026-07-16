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

The [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json) adds runtime-lifecycle and quality-model signals. AI-assisted delivery should distinguish static review, CI, sandboxed execution, preview-environment checks, staging, production observation, and operations telemetry as separate evidence layers. Established product-quality dimensions such as maintainability, reliability, security, and quality gates can anchor AI-generated code acceptance so teams do not rely only on task-completion benchmarks or passing unit tests.

The July 7 raw sources add diagnostic evidence for tool-use and runtime verification. The [topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) records tool-use failure categories such as skipped calls, ignored results, fabricated outputs, and unnecessary calls, along with security-benchmark localization and contamination-control concerns. The [leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) adds step-level action scoring, runtime telemetry, sandbox resource metrics, and production agent-service traces as verification evidence.

The [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json) adds performance-optimization, long-horizon, requirement-compilation, and trajectory-diagnosis signals. Agent evals should cover correctness-preserving optimization, original multi-file tasks, requirement-to-architecture-to-test traceability, and failure localization from traces. Broad benchmark and paper pages stay upstream; locally, these sources sharpen acceptance gates for profiling, hidden correctness checks, reproducible speedup, long-horizon planning, and trace-backed debugging.

The July 12 raw sources add system-evaluation and pre-CI triage signals. The [topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json) routes Dockerless-style environment-free patch checking into local practice as a cheap evidence layer before CI, sandbox, or reviewer time is spent. The [leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json) reinforces coding-agent evals as whole-system traces with side-effect safety, provider-specific harness adapters, trace assertions, token and cost signals, and sandboxed verification.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) adds frontend verification and risk-based review evidence. AI-generated user interfaces can compile and render while still failing keyboard paths, focus movement, accessibility, state changes, loading, error handling, or end-to-end task completion. Verification plans should also document when automated evidence is enough for lower-risk code and when a reviewer must inspect the generated implementation directly.

The [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json) and [July 15 leaf update watch source](../../../raw/processed/2026-07-15/ai-dev-wiki-leaf-update-watch-2026-07-15T210218-0400.json) add loop-engineering and active-security-review signals. Reliable multi-step AI work needs explicit act, observe, decide, retry, and stop conditions tied to tests, runtime feedback, tool results, and human approval gates. Security review findings should include severity, confidence, remediation, and re-verification evidence before they count as accepted risk reduction.

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
- Separate static review, CI, preview, staging, production, and operations evidence when an AI-generated change affects a deployed workflow.
- Include maintainability, reliability, security, and other software-quality dimensions in acceptance gates when the risk exceeds simple functional correctness.
- Classify tool-use failures separately from final-output failure so skipped calls, ignored evidence, fabricated outputs, and unnecessary calls become actionable diagnostics.
- Preserve per-step state, runtime telemetry, sandbox session metrics, and trace identifiers when they explain verification cost, failure localization, or anomalous agent behavior.
- Separate vulnerability classification from line-level localization, proof quality, compilation context, and contamination controls in security-oriented evals.
- Verify performance-optimization tasks with correctness preservation, profiling evidence, reproducible speedup measurement, and trajectory audit.
- Include original long-horizon tasks in acceptance suites when the workflow claims planning, multi-file change management, or sustained verification capability.
- Preserve requirement, architecture, test, implementation, and trace links when an agent compiles requirements into runnable software.
- Use test failures and trace saliency reduction to localize earliest agent errors instead of treating a final failure as an opaque outcome.
- Treat environment-free or static verifier scores as triage evidence that can prioritize CI, sandbox, or reviewer attention, not as final acceptance.
- Evaluate coding agents as systems with trace assertions, side-effect checks, provider adapters, sandbox evidence, and cost signals rather than as one-shot model calls.
- Verify AI-generated frontend work with task completion, accessibility, keyboard, focus, state-change, loading, and error-path checks, not only build output or screenshots.
- Record the review risk tier beside verification evidence so automated checks do not silently replace human inspection for high-impact generated code.
- Define act, observe, decide, retry, and stop conditions for recurring agent loops before treating multi-step behavior as reliable.
- Require severity, confidence, remediation, and re-verification evidence before AI-assisted security review counts as resolved risk.

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
- [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json)
- [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json)
- [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)
- [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json)
- [July 15 leaf update watch source](../../../raw/processed/2026-07-15/ai-dev-wiki-leaf-update-watch-2026-07-15T210218-0400.json)

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
- Maintained on 2026-07-06 with runtime-lifecycle verification layers and software-quality model gates for AI-generated code.
- Maintained on 2026-07-07 with tool-use failure categories, step-level action scoring, sandbox telemetry, and security-eval localization controls.
- Maintained on 2026-07-10 with performance-optimization eval, long-horizon task, requirement-traceability, and trajectory-diagnosis gates.
- Maintained on 2026-07-12 with pre-CI verifier triage, whole-system coding-agent evals, trace assertions, side-effect checks, and cost signals.
- Maintained on 2026-07-13 with frontend task-completion checks and risk-tiered review evidence for AI-generated code.
- Maintained on 2026-07-15 with act-observe-decide-retry-stop loop conditions and AI security review re-verification evidence.
