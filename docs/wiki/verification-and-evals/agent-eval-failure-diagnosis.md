---
type: "Verification And Eval"
title: "Agent Eval Failure Diagnosis"
description: "Agent eval failure diagnosis separates reasoning, action, execution, and final-state failures before changing prompts, tools, or models."
tags: ["verification-and-evals"]
---

# Agent Eval Failure Diagnosis

## Current Understanding

Agent eval failure diagnosis separates reasoning, action, execution, and final-state failures before changing prompts, tools, or models. The [September 17 topic news collector source](../../../raw/processed/2026-09-17/ai-dev-wiki-topic-news-collector-2026-09-17T003308Z.json) records practice guidance for agent evals that use isolated harnesses, code-based checks where possible, repeated trials, transcript review, and pull-request gates for prompt or agent changes. Broad article or vendor background stays upstream-owned; locally, the durable rule is that a single aggregate pass/fail score is too coarse for recurring software agents.

Failure diagnosis should identify the failure class before changing the agent. Common classes include:

- Wrong plan or reasoning path.
- Skipped necessary action.
- Wrong tool or arguments.
- Ignored returned evidence.
- Wrong final state.
- Nondeterministic service behavior.

The evidence package should include the task, initial state, allowed tools, transcript, tool calls, expected final state, actual final state, trial count, and failed check.

## Practice Boundaries

- Separate reasoning, action selection, tool execution, final-state, transcript-review, and repeated-trial failures.
- Prefer deterministic or code-based final-state checks when the task can be inspected through files, APIs, databases, or other structured state.
- Use transcript review to explain why a failure happened, not as a substitute for final-state evidence.
- Run repeated trials when nondeterminism, routing, or tool timing could affect the result.
- Gate recurring prompt, policy, tool, or agent changes through pull-request checks or equivalent reviewable change records.
- Convert incident patterns from [agent incident reporting](../governance-and-risk/agent-incident-reporting.md) into targeted eval cases when the workflow is expected to recur.

## Authoritative Sources

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

- Created on 2026-09-16 from raw-source evidence about practical AI-agent eval design and failure-mode separation; next check should map real failed eval cases to the listed diagnosis buckets before adding more categories.
