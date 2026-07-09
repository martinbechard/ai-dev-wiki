---
type: "Topic"
title: "Orient Inspect Patch Verify Loop"
description: "AI-assisted coding is a controlled loop, not a single answer. The local loop is orient, inspect, plan, patch, verify, and carry evidence forward."
tags: ["agent-workflows"]
---

# Orient Inspect Patch Verify Loop

## Current Understanding

AI-assisted coding is a controlled loop, not a single answer. The local loop is orient, inspect, plan, patch, verify, and carry evidence forward. Each pass should produce new evidence from files, tests, tool output, or runtime behavior before the next action.

Tool calls are the bridge between model text and repository reality. The agent should inspect source state before editing, explain scope while working, make targeted changes, run the relevant checks, and report the evidence that supports completion. Subagents fit this loop when independent investigations can stay separate until the main agent integrates the result.

Named coding agents, agentic frameworks, and autonomous engineering platforms are upstream-owned ecosystem entities. This page keeps the local operating pattern for using them.

The broader [research plan implement review lifecycle](research-plan-implement-review-lifecycle.md), [use compose build workflow selection](use-compose-build-workflow-selection.md), [subagent coordination](subagent-coordination.md), and [delegated coding handoffs](delegated-coding-handoffs.md) have their own leaves. This page owns the controlled-change loop that keeps each pass grounded in fresh evidence.

The [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) frames coding-agent orchestration as a cost-sensitive sequence of evidence gathering, refinement, verification, and stopping decisions. The local loop should not run checks mechanically or skip them for speed; each pass should choose the next evidence step based on uncertainty, risk, and verifier cost.

The [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) adds PR-repair delegation signals from mobile and cloud-agent flows. The local loop can accept an agent handoff for merge conflicts, failing workflows, review comments, tests, or follow-up changes only when the returned diff is reviewable and the verification evidence is carried back into the same inspect, patch, and verify cycle.

## Practice Boundaries

- Orient from repository state, procedures, and existing wiki pages before proposing changes.
- Inspect the files or runtime surfaces that control the behavior.
- Plan visibly when scope or sequencing matters.
- Patch narrowly and keep unrelated changes out of the ingest or implementation.
- Verify with build, test, lint, runtime checks, or source reconciliation as appropriate.
- Carry unresolved evidence gaps into Open Questions instead of presenting guesses as settled.
- Link multi-phase lifecycle guidance to [research-plan-implement-review-lifecycle.md](research-plan-implement-review-lifecycle.md).
- Link workflow strategy decisions to [use-compose-build-workflow-selection.md](use-compose-build-workflow-selection.md).
- Choose the next inspect, refine, verify, or stop step according to uncertainty, change risk, and verification cost.
- Treat delegated PR repair as another pass through the loop: inspect the conflict or failure, patch narrowly, run the relevant checks, and report reviewable evidence before merge.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [federation.md](../federation.md)
- [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [research plan implement review lifecycle](research-plan-implement-review-lifecycle.md)
- [delegated coding handoffs](delegated-coding-handoffs.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from the local source decks covering agent loops, tool calls, visible planning, and subagent use.
- Split on 2026-06-23 so RPI lifecycle, use-compose-build selection, subagent coordination, and handoffs live in durable leaf pages.
- Maintained on 2026-06-28 with cost-sensitive evidence gathering, refinement, verification, and stop decisions.
- Maintained on 2026-07-08 with delegated PR repair loops for conflicts, failing workflows, review comments, tests, and follow-up changes.
