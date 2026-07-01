---
type: "Verification And Eval"
title: "Trajectory-Level Agent Evaluation"
description: "Agent evaluation should inspect the path an agent took, not only the final answer or merged diff."
tags: ["verification-and-evals"]
---

# Trajectory-Level Agent Evaluation

## Current Understanding

Agent evaluation should inspect the path an agent took, not only the final answer or merged diff. The local evaluation object includes task framing, retrieved context, reasoning-visible summaries, tool calls, execution order, state transitions, approval waits, errors, retries, generated artifacts, and final verification.

The [topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) records multiple public signals that agent monitoring, observability, and evals are converging around trajectory evidence. Vendor, benchmark, and product pages stay upstream-owned; this page owns the local practice of using trajectory evidence to decide whether an agent workflow is reliable.

Trajectory evaluation complements [representative workflow calibration](representative-workflow-calibration.md). Calibration checks whether a model or harness is suitable for representative tasks. Trajectory evaluation checks whether a particular run, workflow family, or agent configuration behaved safely and effectively across its intermediate decisions.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) adds an agreement and environment-design signal. Agent evals should inspect whether independent runs converge on the same evidence-backed result, whether disagreement exposes missing context or weak rubrics, and whether the harness environment made the relevant tools, context, and feedback visible.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) also routes model benchmark announcements upstream. Locally, benchmark improvements only change practice when they trigger new representative terminal, coding, review, or repair tasks in the acceptance suite before autonomy expands.

The [agent evals source](../../../raw/processed/Making Agent Evals Isn’t As Hard As You Think!.md) adds a test-shape taxonomy for agent behavior. Behavioral unit evals should lock a single expected step or tool call, integration evals should score full-run outcomes, online evals should monitor live traces and trends, and benchmark evals should measure a representative capability across task distributions. The local practice is to choose the eval shape from the failure mode being controlled.

## Evaluation Signals

- Whether the request package preserved source authority and task boundaries.
- Whether retrieval and context additions were relevant, attributed, and sufficient.
- Whether tool calls used the intended schemas, order, permissions, and inputs.
- Whether retries corrected real failures instead of hiding them.
- Whether approval waits, blocked states, and handoffs were visible.
- Whether safety, governance, cost, and latency constraints held across the run.
- Whether final verification matched the risk surface of the work.
- Whether independent agents or repeated runs agree on the evidence-backed result and expose the same residual risks.
- Whether model or harness changes were tested against representative local terminal, coding, review, and repair tasks before autonomy changed.
- Whether a behavior needs a single-step regression check, a full-run outcome check, live trace monitoring, or a capability benchmark.

## Practice Boundaries

- Evaluate tool-using agent workflows with trace and transcript evidence, not only final outputs.
- Record the model or routing policy when available, but do not block evaluation when a tool provider hides exact routing.
- Treat public long-horizon benchmarks as context for benchmark design, not as proof that a local workflow is reliable.
- Keep benchmark entities and vendor products upstream unless a local acceptance rule depends on them.
- Use human review when trajectory evidence contains judgment-heavy product, security, architecture, or operational tradeoffs.
- Track cross-run agreement and disagreement as evidence about task clarity, retrieval sufficiency, and rubric quality.
- Treat public benchmark gains as candidate eval inputs, not as local authorization to increase tool or write access.
- Use behavioral unit evals for expected next actions, integration evals for final artifacts, online evals for deployed trend monitoring, and benchmarks for capability-level comparison.

## Authoritative Sources

- [Topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [representative workflow calibration](representative-workflow-calibration.md)
- [verification loops and evals](verification-loops-and-evals.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)
- [user-visible progress and runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [Agent evals source](../../../raw/processed/Making Agent Evals Isn’t As Hard As You Think!.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification-and-evals](index.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [agent harness components](../application-patterns/agent-harness-components.md)
- [code review evals and rubrics](code-review-evals-and-rubrics.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-24 to hold trajectory, trace, and intermediate-decision evaluation practice for agent workflows.
- Maintained on 2026-06-27 with cross-run agreement, environment-design, and benchmark-to-local-suite routing rules.
- Maintained on 2026-06-30 with behavioral unit, integration, online, and benchmark eval shape guidance.
