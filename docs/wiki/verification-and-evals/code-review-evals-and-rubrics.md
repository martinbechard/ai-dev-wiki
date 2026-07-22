---
type: "Verification And Eval"
title: "Code Review Evals And Rubrics"
description: "AI-assisted code review evals measure whether a model or harness can inspect changes against the repository's standards, source evidence, and risk profile."
tags: ["verification-and-evals"]
---

# Code Review Evals And Rubrics

## Current Understanding

AI-assisted code review evals measure whether a model or harness can inspect changes against the repository's standards, source evidence, and risk profile. They should test the review task itself, not only whether the model can produce plausible comments.

Useful review rubrics include correctness, source grounding, missing tests, security risk, architectural fit, maintainability, and whether the reviewer reports uncertainty instead of inventing evidence. The AI-assisted coding deck treats review as part of the controlled coding loop, and the Dwarf Star source is evidence that code review prompts can be part of representative model calibration.

This page owns review-specific eval practice. General grader selection lives in [judge grader boundaries](judge-grader-boundaries.md), and delivery acceptance gates live in [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md).

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) adds a cost-quality dimension for AI code review. Review evals should capture whether deeper file exploration, explicit review-depth settings, or repository search tools improve finding quality enough to justify added cost and latency. Broad product feature tracking stays upstream; locally, the rubric should make review depth and evidence path measurable.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) and [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) add prompt-provenance and knowledge-acceptance signals. Review rubrics should distinguish accepting an external knowledge package from accepting implementation, and should include prompt, provenance label, review-depth setting, and retrieval path when those artifacts shaped the review.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) adds scoped retrieval and cross-run agreement to review evaluation. Rubrics should measure whether targeted context gathering finds the same material issues as broader retrieval and whether independent reviewers converge on the same source-backed findings.

The [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) adds independent verification and repeatability signals. The generator should not be the sole formal reviewer of its own output, and agentic security review should be evaluated across repeated runs. Rubrics should separate reference-matched findings from exploratory findings so unstable extra issues do not look like dependable coverage.

The [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json) and [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json) reinforce review independence and trajectory evaluation. Code review evals should score whether the reviewer inspects the path to the change, not only the final diff, and whether repeated reviews converge on source-backed risks. Outcome scores, step-level traces, human review, and LLM-as-judge outputs should be kept distinct so a fluent positive review does not erase missing evidence.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) adds recall-first tuning evidence. Review evals should measure missed defects, filtered false positives, reviewer attention cost, and the repository or dependency evidence behind cross-file findings instead of scoring only whether the final comment sounds plausible.

The [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json) adds architecture-context and compliance-fit dimensions. Code-review evals should score whole-repository context, architectural fit, Git workflow integration, actionability, team-standard customization, latency, and whether the deployment model can satisfy source-location and audit requirements.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) and [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json) add representative benchmark and enterprise-review signals. Review rubrics should include real codebase tasks, language-specific tasks, benchmark-contamination checks, repository-context requirements, false-positive controls, and whether a finding leads to a validated fix. Model or vendor claims are useful only when mapped to the local review job and calibrated against source-backed outcomes.

The [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json) adds model-routing and benchmark-repository signals for review evals. Rubrics should record whether routing decisions were based on language, repository risk, review depth, finding type, and validated-fix outcome, and should keep benchmark repository provenance separate from local acceptance evidence. Broad review-tool and benchmark entity coverage remains upstream-owned.

The July 18-21 raw sources add task-shape, review-history, disagreement, and AI-code gate signals. The [July 19 topic news collector source](../../../raw/processed/2026-07-19/ai-dev-wiki-topic-news-collector-2026-07-19T203449-0400.json) argues that benchmark reports should expose task shape beyond aggregate Pass@1, and the [July 21 topic news collector source](../../../raw/processed/2026-07-21/ai-dev-wiki-topic-news-collector-2026-07-21T203101-0400.json) adds full review-history visibility, rate-limit impact metrics, reviewer disagreement as a stop condition, and AI-code verification gates. Review evals should score when reviewers fail to converge, when review wait time or rate limits change process quality, and when AI-generated code needs a gate that prioritizes security and architecture risks over style-only findings.

## Practice Boundaries

- Build review eval cases from real or representative changes, not only abstract review questions.
- Include source files, diffs, tests, logs, and repository rules that a reviewer should inspect.
- Grade whether findings are actionable, source-backed, and prioritized by risk.
- Penalize invented code paths, test results, security claims, or backlog status.
- Include cases where the correct review outcome is no finding plus residual risk.
- Keep broad benchmark catalogs upstream unless a benchmark changes local review practice.
- Measure review-depth settings, repository exploration path, false positives, missed findings, cost, and latency when comparing AI review configurations.
- Grade whether the review had enough prompt, provenance, trace, and retrieval-path context to assess AI-generated or externally packaged work.
- Separate knowledge-package acceptance from implementation acceptance when external agent artifacts are involved.
- Include comparison cases for targeted versus broad retrieval so review-efficiency changes do not hide missed findings.
- Track independent-reviewer agreement and disagreement when calibrating review rubrics or model routing.
- Separate generation, review, test, and approval roles when the eval represents a formal review gate.
- Measure repeatability across repeated agentic security-review runs, distinguishing reference-matched findings from variable exploratory findings.
- Grade review traces for evidence collection, tool-use discipline, and risk escalation before accepting the final review summary.
- Keep human review, deterministic checks, and LLM-as-judge scores separate when calibrating code review quality.
- Measure recall, precision, filtering quality, and reviewer attention cost as separate code-review eval dimensions.
- Include cross-file and dependency-risk cases where the expected finding requires repository evidence beyond the changed hunk.
- Score whole-repository architecture context, workflow integration, actionability, team-standard customization, and latency as separate dimensions.
- Include compliance-fit checks for source location, audit evidence, and deployment model when the review tool is meant for regulated or proprietary code.
- Prefer real-codebase and language-specific eval tasks over generic score claims when calibrating AI code review.
- Track benchmark provenance, contamination risk, repository-context use, false positives, and validated-fix outcomes separately.
- Record model-routing criteria, review depth, finding category, benchmark provenance, and validated-fix outcome as separate review-eval fields.
- Include task shape, review-history state, review wait time, rate-limit effects, and reviewer convergence or disagreement when comparing review agents.
- Treat persistent reviewer disagreement on a central risk as a stop condition that needs human review or better evidence, not as a success after repeated rounds.
- Evaluate AI-code gates by security, architecture, dependency, and quality risk priority instead of rewarding style-only volume.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [generated code refactoring](../coding-practices/generated-code-refactoring.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json)
- [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json)
- [July 1 evening leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T210055-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json)
- [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json)
- [July 19 topic news collector source](../../../raw/processed/2026-07-19/ai-dev-wiki-topic-news-collector-2026-07-19T203449-0400.json)
- [July 21 topic news collector source](../../../raw/processed/2026-07-21/ai-dev-wiki-topic-news-collector-2026-07-21T203101-0400.json)

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
- Maintained on 2026-06-25 with cost-quality and retrieval-depth measurements for AI code review.
- Maintained on 2026-06-26 with prompt provenance, review-depth settings, retrieval path, and knowledge-package acceptance boundaries.
- Maintained on 2026-06-27 with targeted-retrieval comparison cases and independent-reviewer agreement signals.
- Maintained on 2026-07-01 with independent verification-layer boundaries and repeatability scoring for AI security review.
- Maintained on 2026-07-01 with trajectory-level review traces, repeated-review convergence, and separated human, deterministic, and judge signals.
- Maintained on 2026-07-04 with recall-first tuning, filtered false-positive costs, and dependency-aware review cases.
- Maintained on 2026-07-05 with architecture-context, workflow-integration, actionability, customization, latency, and compliance-fit dimensions.
- Maintained on 2026-07-11 with real-codebase, language-specific, contamination-aware, and validated-fix review eval dimensions.
- Maintained on 2026-07-16 with model-routing, review-depth, finding-category, benchmark-provenance, and validated-fix eval fields.
- Maintained on 2026-07-22 with task-shape reporting, review-history state, rate-limit impact, reviewer-disagreement stop conditions, and AI-code gate priorities.
