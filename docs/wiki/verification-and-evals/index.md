# Verification And Evals

## Current Understanding

Verification and evals covers how AI-assisted outputs earn trust. The local scope includes build, test, lint, runtime checks, source-backed claims, deterministic graders, LLM judges, regression suites, benchmarks, and done signals.

This topic owns evaluation practice rather than model benchmark catalogs. When a public benchmark or eval product is primarily an upstream ecosystem entity, this wiki keeps only the local interpretation or operating rule.

## Pattern Leaf Pages

- [verification-loops-and-evals.md](verification-loops-and-evals.md) records the build, test, lint, runtime, grounding, and eval overview.
- [verification-tax-and-acceptance-gates.md](verification-tax-and-acceptance-gates.md) records the validation bottleneck and acceptance-gate practice for agentic delivery.
- [code-review-evals-and-rubrics.md](code-review-evals-and-rubrics.md) records AI-assisted code review evals, reviewer rubrics, and source-backed review evidence.
- [judge-grader-boundaries.md](judge-grader-boundaries.md) records deterministic grader, human review, and LLM-as-judge boundaries.
- [representative-workflow-calibration.md](representative-workflow-calibration.md) records representative prompts, tool-call calibration, and local model drift checks.
- [trajectory-level-agent-evaluation.md](trajectory-level-agent-evaluation.md) records trace, transcript, tool-call, state-transition, and intermediate-decision evidence for agent workflow evaluation.
- [agent-assisted-performance-optimization-gates.md](agent-assisted-performance-optimization-gates.md) records correctness, baseline, representative workload, measurement, rollback, and approval gates for optimization agents.
- [product-judgment-quality-gates.md](product-judgment-quality-gates.md) records product judgment gates, periodic health review, and pre-merge acceptance checks.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [Studious source](../../../raw/processed/jacquardlabsstudious Studious — a product-judgment workflow for Claude Code quality gates, periodic health reviews, and pre-merge audits that examine each piece of work..md)
- [Evals source](../../../raw/processed/You’ll Finally Understand AI Evals After Watching This.md)
- [Topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [coding-practices](../coding-practices/index.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [coding-practices](../coding-practices/index.md)
- [agent-workflows](../agent-workflows/index.md)
- [application-patterns](../application-patterns/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 as the local owner for verification and evaluation practice.
- Maintained on 2026-06-23 to split acceptance gates, code review evals, grader boundaries, and representative calibration into durable leaves.
- Maintained on 2026-06-24 to add trajectory-level agent evaluation for trace and intermediate-decision evidence.
- Maintained on 2026-07-17 to add performance-optimization acceptance gates for agent-assisted speedup work.
