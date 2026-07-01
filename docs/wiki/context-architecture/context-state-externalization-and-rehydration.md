---
type: "Context Architecture"
title: "Context State Externalization And Rehydration"
description: "Context state externalization is the practice of moving agent working state out of the conversation and onto durable project files before the model needs to rely on it."
tags: ["context-architecture"]
---

# Context State Externalization And Rehydration

## Current Understanding

Context state externalization is the practice of moving agent working state out of the conversation and onto durable project files before the model needs to rely on it. The [context management source](../../../raw/processed/Why Doesn't Anyone Teach Developers About Context Management?.md), [context loss source](../../../raw/processed/Your AI Agent Already Forgot Half of What You Told It.md), [context collapse source](../../../raw/processed/When Context Collapses Teaching Agents to Detect and Recover from Lost Memory.md), and [lost-in-the-middle source](../../../raw/processed/So Long and Thanks for All the Context.md) frame the same local rule: important state should live in files that a fresh or recovering session can read, verify, and continue from.

Externalization has two layers. Task-continuity files describe the purpose, constraints, source authority, and done signal for the work. Execution-continuity files describe the current cursor, completed units, produced artifacts, discrepancies, and next action. Rehydration means reading both layers back, checking them against disk truth, and resuming from the verified state instead of from conversation memory.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) and [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) reinforce that conversation history management is a designed state system. Instructions, memory, tool outputs, retrieval evidence, agent definitions, and progress files should be retained, pruned, summarized, or externalized according to their authority and recovery value instead of being treated as one undifferentiated chat transcript.

This page owns context-state durability and recovery. [Context selection and compaction](context-selection-and-compaction.md) owns what evidence enters a request. [Request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md) owns how a specific request labels evidence, constraints, and done signals. [Persistent agent workspaces](../agent-workflows/persistent-agent-workspaces.md) owns long-running workspace continuity.

## Practice Boundaries

- Store active task state, handoffs, progress cursors, decision rationale, and intermediate observations in project files when later steps depend on them.
- Use task-continuity files for stable purpose, constraints, source authority, and acceptance criteria.
- Use execution-continuity files for changing cursor state, completed units, generated artifacts, errors, and next actions.
- Write output before advancing a progress cursor so startup checks can detect partial work.
- At session start or after suspected context loss, compare progress files against output artifacts and trust disk state when they disagree.
- Require rehydration summaries for long or interrupted work so the agent commits to what it read from disk before continuing.
- Keep context files small enough for the next session to load deliberately; externalization is not a license to dump every transcript into the working set.
- Retain, prune, summarize, or externalize conversation history according to source authority, recovery value, and the risk of stale state.
- Keep instructions, memory, retrieval evidence, tool outputs, and progress files as separate context layers during rehydration.

## Authoritative Sources

- [Context management source](../../../raw/processed/Why Doesn't Anyone Teach Developers About Context Management?.md)
- [Context loss source](../../../raw/processed/Your AI Agent Already Forgot Half of What You Told It.md)
- [Context collapse source](../../../raw/processed/When Context Collapses Teaching Agents to Detect and Recover from Lost Memory.md)
- [Lost-in-the-middle source](../../../raw/processed/So Long and Thanks for All the Context.md)
- [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json)
- [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json)
- [context selection and compaction](context-selection-and-compaction.md)
- [delegated coding handoffs](../agent-workflows/delegated-coding-handoffs.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [context selection and compaction](context-selection-and-compaction.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [persistent agent workspaces](../agent-workflows/persistent-agent-workspaces.md)
- [delegated coding handoffs](../agent-workflows/delegated-coding-handoffs.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-27 from O'Reilly context-management sources covering durable context files, handoffs, cursor checks, rehydration, and lost-in-the-middle mitigation.
- Maintained on 2026-06-28 with conversation-history management as layered retention, pruning, summarization, and rehydration.
