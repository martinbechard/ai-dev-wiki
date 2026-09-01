---
type: "Verification And Eval"
title: "Agent-Assisted Performance Optimization Gates"
description: "Agent-assisted performance optimization gates keep speedup work tied to correctness, baselines, representative workloads, and approval."
tags: ["verification-and-evals"]
---

# Agent-Assisted Performance Optimization Gates

## Current Understanding

Agent-assisted performance optimization gates keep speedup work tied to correctness, baselines, representative workloads, and approval. Optimization agents can propose patches, compiler flags, cache changes, dependency changes, or build-system edits quickly, but the accepted result is the verified improvement under the workflow a developer or system actually uses.

The [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json) routed performance optimization into local eval practice as a correctness-preserving, trace-backed workflow rather than a benchmark headline. The [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) adds build-agent evidence: performance work should record clean versus incremental baseline choice, profiling context, representative workload, suggested experiments, rollback path, and human approval before applying generated optimizations.

The [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) adds outcome-eval framing that applies to optimization work. Capability evals should prove an optimization agent can find and measure improvements, while regression evals should prove the accepted workflow still preserves correctness, deployment readiness, and environment-specific behavior after the change.

The [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json) adds first-party trace and reasoning-depth evidence. Performance and optimization gates should preserve local workload traces, product-specific success criteria, model or reasoning settings, token and credit use, and task complexity so teams can decide whether a higher-effort run improved the accepted outcome enough to justify the cost.

The [model-cost benchmark clipping](../../../raw/processed/cheapest-model-per-run-most-expensive-per-real-fix.md) adds a benchmark-gaming boundary for performance work. A generated optimization that replaces the measured workload with a precomputed lookup can be correct for the exact benchmark while moving work, freshness risk, or maintenance cost outside the measured path. Performance gates should classify in-place fixes separately from cache, materialized-view, snapshot, or test-case-specific rewrites, and should count only the accepted class when ranking model or workflow quality.

The [August 25 afternoon leaf update watch source](../../../raw/processed/2026-08-25/ai-dev-wiki-leaf-update-watch-2026-08-25T144100-0400.json) adds agent-evaluation metrics that also apply to performance optimization. Speed, latency, or cost improvements should be accepted only with task success, tool-use correctness, trajectory quality, safety, repeated-run reliability, and human-intervention evidence. Deterministic graders should own provable checks, while calibrated LLM judges may cover bounded qualitative criteria without replacing measured performance and correctness evidence.

The [August 31 leaf update watch source](../../../raw/processed/2026-08-31/ai-dev-wiki-leaf-update-watch-2026-08-31T210122-0400.json) adds end-to-end RAG benchmark evidence. Retrieval optimization should measure ingestion and question-answering workloads together, including chunk provenance, ranking, reranking, document grading, sufficiency checks, answer quality, latency, and model-routing cost. An optimization that improves one retrieval stage is not accepted until the pipeline-level task still meets accuracy, compliance, and provenance requirements.

This page owns performance-specific acceptance. [Trajectory-level agent evaluation](trajectory-level-agent-evaluation.md) owns trace, harness, and environment evidence; [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md) owns delivery-level acceptance; and [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md) owns human decisions about experiments and applying changes.

## Practice Boundaries

- Record the baseline metric, workload, environment, cache state, and whether the target is clean build, incremental build, runtime latency, throughput, memory, or another performance dimension.
- Preserve correctness checks before and after optimization so speed does not hide broken behavior.
- Require profiling or measurement evidence before accepting an agent-proposed optimization target.
- Treat generated compiler, build-system, dependency, cache, concurrency, or architecture changes as ordinary code changes with review, tests, and rollback.
- Separate experiments the agent may run from optimizations it may apply, merge, release, or recommend for production.
- Compare repeated measurements enough to distinguish real improvement from noise, warm-cache effects, or environment drift.
- Keep rollback rules and human approval tied to the measured change, not to a broad grant for performance-agent autonomy.
- Separate capability evals for finding optimization opportunities from regression evals that prove the deployed workflow remains correct in its target environment.
- Preserve first-party workload traces and product-specific success criteria when optimizing agent-assisted workflows.
- Record model route, reasoning depth, task complexity, token use, and credit cost when comparing optimization quality or performance outcomes.
- Classify whether a speedup improves the target workload in place, moves work to precomputation, narrows the schema to one benchmark case, or changes freshness and maintenance obligations.
- Count benchmark calls and read the produced patch or query before treating a fast result as an accepted optimization.
- Gate speed, latency, and cost claims with task success, tool correctness, trajectory quality, safety, repeated-run reliability, and human-intervention evidence.
- Prefer deterministic graders for provable optimization checks and reserve calibrated judges for bounded qualitative review.
- For RAG optimization, measure ingestion, retrieval, reranking, grading, sufficiency, answer quality, latency, model-routing cost, and provenance as one accepted pipeline.

## Authoritative Sources

- [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json)
- [Model-cost benchmark clipping](../../../raw/processed/cheapest-model-per-run-most-expensive-per-real-fix.md)
- [August 25 afternoon leaf update watch source](../../../raw/processed/2026-08-25/ai-dev-wiki-leaf-update-watch-2026-08-25T144100-0400.json)
- [August 31 leaf update watch source](../../../raw/processed/2026-08-31/ai-dev-wiki-leaf-update-watch-2026-08-31T210122-0400.json)
- [verification loops and evals](verification-loops-and-evals.md)
- [trajectory-level agent evaluation](trajectory-level-agent-evaluation.md)
- [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification-and-evals](index.md)
- [representative workflow calibration](representative-workflow-calibration.md)
- [terminal agent workflows](../agent-workflows/terminal-agent-workflows.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-17 from public raw artifacts about build-performance agents, profiling workflows, baseline selection, incremental-build measurement, rollback rules, and approval gates.
- Maintained on 2026-07-28 with capability-versus-regression eval boundaries for optimization agents and deployment-specific outcome checks.
- Maintained on 2026-08-04 with first-party trace, task-complexity, reasoning-depth, token-cost, and product-specific success criteria.
- Maintained on 2026-08-05 with benchmark-gaming classification, in-place fix counting, and tool-call cost evidence.
- Maintained on 2026-08-25 with task-success, tool-correctness, trajectory-quality, safety, reliability, human-intervention, deterministic-grader, and calibrated-judge gates.
- Maintained on 2026-08-31 with end-to-end RAG ingestion, retrieval, reranking, grading, sufficiency, answer-quality, latency, routing-cost, and provenance gates.
