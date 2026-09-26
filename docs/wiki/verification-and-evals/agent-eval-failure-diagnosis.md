---
type: "Verification And Eval"
title: "Agent Eval Failure Diagnosis"
description: "Agent eval failure diagnosis separates reasoning, action, execution, and final-state failures before changing prompts, tools, or models."
tags: ["verification-and-evals"]
---

# Agent Eval Failure Diagnosis

## Current Understanding

The [September 24 leaf update watch source](../../../raw/processed/2026-09-24/ai-dev-wiki-leaf-update-watch-2026-09-24T210226-0400.json) adds RAG absence and production-observability evidence. Agent eval diagnosis should test whether retrieval systems abstain when evidence is absent, not only whether they answer when evidence is present, and should join completed-task evaluation with traceable tool authorization, reliability, cost, latency, and quality signals.

Agent eval failure diagnosis separates reasoning, action, execution, and final-state failures before changing prompts, tools, or models. The [September 17 topic news collector source](../../../raw/processed/2026-09-17/ai-dev-wiki-topic-news-collector-2026-09-17T003308Z.json) records practice guidance for agent evals that use isolated harnesses, code-based checks where possible, repeated trials, transcript review, and pull-request gates for prompt or agent changes. Broad article or vendor background stays upstream-owned; locally, the durable rule is that a single aggregate pass/fail score is too coarse for recurring software agents.

Failure diagnosis should identify the failure class before changing the agent. Common classes include:

- Wrong plan or reasoning path.
- Skipped necessary action.
- Wrong tool or arguments.
- Ignored returned evidence.
- Wrong final state.
- Nondeterministic service behavior.

The evidence package should include the task, initial state, allowed tools, transcript, tool calls, expected final state, actual final state, trial count, and failed check.

The [September 25 topic news collector source](../../../raw/processed/2026-09-25/ai-dev-wiki-topic-news-collector-2026-09-26T003140Z.json) adds self-improvement and cost-failure evidence. When a harness tries to improve itself or a long-running agent loop scales up, diagnosis should separate sparse-update overfitting, eval leakage, stability-threshold failures, excessive context or tool-definition cost, subagent fan-out, and runaway API-call loops before changing model routes or prompts.

## Practice Boundaries

- Include knowledge-gap canaries or absence tests when diagnosing retrieval-backed agents so fabrication and failure-to-abstain become visible.
- Join traceable tool authorization, completed-task evaluation, reliability, latency, cost, and quality signals before attributing a failure only to model reasoning.

- Separate reasoning, action selection, tool execution, final-state, transcript-review, and repeated-trial failures.
- Prefer deterministic or code-based final-state checks when the task can be inspected through files, APIs, databases, or other structured state.
- Use transcript review to explain why a failure happened, not as a substitute for final-state evidence.
- Run repeated trials when nondeterminism, routing, or tool timing could affect the result.
- Gate recurring prompt, policy, tool, or agent changes through pull-request checks or equivalent reviewable change records.
- Convert incident patterns from [agent incident reporting](../governance-and-risk/agent-incident-reporting.md) into targeted eval cases when the workflow is expected to recur.
- Separate eval leakage, self-improvement overfitting, unstable sparse updates, excessive context growth, tool-definition cost, subagent fan-out, and runaway call loops before treating a failed long-horizon run as only a reasoning failure.

## Authoritative Sources

- [September 24 leaf update watch source](../../../raw/processed/2026-09-24/ai-dev-wiki-leaf-update-watch-2026-09-24T210226-0400.json)
- [September 25 topic news collector source](../../../raw/processed/2026-09-25/ai-dev-wiki-topic-news-collector-2026-09-26T003140Z.json)

- [September 17 topic news collector source](../../../raw/processed/2026-09-17/ai-dev-wiki-topic-news-collector-2026-09-17T003308Z.json)
- [verification loops and evals](verification-loops-and-evals.md)
- [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md)
- [trajectory-level agent evaluation](trajectory-level-agent-evaluation.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification loops and evals](verification-loops-and-evals.md)
- [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md)
- [agent incident reporting](../governance-and-risk/agent-incident-reporting.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-09-25 with knowledge-gap canary, abstention, observability, and completed-task evaluation evidence.
- Maintained on 2026-09-25 with self-improvement overfitting, eval leakage, stability-threshold, context-cost, subagent fan-out, and runaway-loop diagnosis evidence.

- Created on 2026-09-16 from raw-source evidence about practical AI-agent eval design and failure-mode separation; next check should map real failed eval cases to the listed diagnosis buckets before adding more categories.
