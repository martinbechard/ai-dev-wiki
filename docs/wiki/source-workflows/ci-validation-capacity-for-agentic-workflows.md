---
type: "Source Workflow"
title: "CI Validation Capacity For Agentic Workflows"
description: "CI validation capacity treats fast checks, deferred checks, ownership, and evidence routing as an operating constraint for AI-assisted delivery."
tags: ["source-workflows", "verification-and-evals"]
---

# CI Validation Capacity For Agentic Workflows

## Current Understanding

CI validation capacity treats fast checks, deferred checks, ownership, and evidence routing as an operating constraint for AI-assisted delivery. Agentic teams can generate code faster than CI, reviewers, or scheduled validation can absorb it, so validation design belongs in the workflow rather than only in repository infrastructure.

The [October 7 topic news collector source](../../../raw/processed/2026-10-06/ai-dev-wiki-topic-news-collector-2026-10-07T003059Z.json) contributes two source-specific signals:

- CodeHerder reports a five-minute merge-request CI budget, expiring written exceptions, import-graph check selection with full-run fallback, scheduled slow checks, agent-owned repair tasks, and expiring flaky-test quarantine.
- Tech To Heart frames CI as the delivery gate and cost center that needs baseline wait-time, queue-time, setup-overhead, failure-rate, runner-cost, caching, batching, selective validation, ownership for red builds, and audit trails.

Locally, both sources support the same durable practice: speed up foreground checks only when deferred validation still has owners, evidence, and repair paths.

## Practice Boundaries

- Keep merge-request validation fast enough for review flow, but record the policy, exception owner, expiry, and fallback path when a check exceeds the budget.
- Select affected checks from dependency or import evidence when available, and run full fallback suites when selection evidence is incomplete.
- Move slow validation to scheduled or deferred lanes only when failures create owned repair tasks with logs, bisect or reproduction evidence, duplicate suppression, and escalation rules.
- Quarantine flaky tests with expiry, owner, and reinstatement criteria; do not let quarantine become permanent evidence loss.
- Measure queue time, setup overhead, failure rate, runner cost, cache effectiveness, and red-build ownership before expanding agentic coding throughput.
- Route local acceptance-gate detail to [verification tax and acceptance gates](../verification-and-evals/verification-tax-and-acceptance-gates.md) and workflow queue evidence to [source reconciliation and routing](source-reconciliation-and-routing.md).

## Authoritative Sources

- [October 7 topic news collector source](../../../raw/processed/2026-10-06/ai-dev-wiki-topic-news-collector-2026-10-07T003059Z.json)
- [verification tax and acceptance gates](../verification-and-evals/verification-tax-and-acceptance-gates.md)
- [source reconciliation and routing](source-reconciliation-and-routing.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [source-workflows](index.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [verification tax and acceptance gates](../verification-and-evals/verification-tax-and-acceptance-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-10-07 from October 7 raw-source evidence about merge-request CI budgets, selective validation, scheduled repair tasks, flaky-test quarantine, validation-cost measurement, and red-build ownership.
