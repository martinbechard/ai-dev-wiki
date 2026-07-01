# Context Architecture

## Current Understanding

Context architecture covers the durable instruction and knowledge surfaces that help an AI assistant choose the right evidence for a task. The local model is the context-aware guidance structure from the [folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md): a thin router, a rules layer, a knowledge layer, and documentation organized by lifespan.

This topic owns local guidance for routing, context selection, token discipline, compaction, durable instructions, and source boundaries. It does not own broad product or model catalogs; those stay in the federated [AI wiki](../federation.md).

## Pattern Leaf Pages

- [context-router-and-knowledge-layers.md](context-router-and-knowledge-layers.md) is the overview for the local context-aware guidance structure.
- [thin-context-router.md](thin-context-router.md) records the root router pattern that routes agents to task-specific guidance.
- [rules-and-knowledge-layers.md](rules-and-knowledge-layers.md) records durable conventions and stable project facts.
- [lifespan-organized-documentation.md](lifespan-organized-documentation.md) records active, decision, reference, and archive documentation authority signals.
- [context-selection-and-compaction.md](context-selection-and-compaction.md) records source selection, token discipline, summaries, and context trimming.
- [context-state-externalization-and-rehydration.md](context-state-externalization-and-rehydration.md) records durable task state, progress files, handoffs, cursor checks, and recovery after context loss.
- [compiled-wiki-and-structured-memory.md](compiled-wiki-and-structured-memory.md) records when prose wikis, structured stores, and generated views should own context.
- [self-service-analytics-context-governance.md](self-service-analytics-context-governance.md) records analytics-specific context governance for canonical metrics, metadata, skills, and evals.

## Authoritative Sources

- [Folder organization source note](../../../raw/processed/Folder organization by @AICodethatWorks.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Karpathy wiki versus OpenBrain source](../../../raw/processed/Karpathy's Wiki vs. Open Brain. One Fails When You Need It Most..md)
- [Anthropic analytics source](../../../raw/processed/How Anthropic enables self-service data analytics with Claude.md)
- [Context management source](../../../raw/processed/Why Doesn't Anyone Teach Developers About Context Management?.md)
- [Context loss source](../../../raw/processed/Your AI Agent Already Forgot Half of What You Told It.md)
- [Context collapse source](../../../raw/processed/When Context Collapses Teaching Agents to Detect and Recover from Lost Memory.md)
- [Lost-in-the-middle source](../../../raw/processed/So Long and Thanks for All the Context.md)
- [federation.md](../federation.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [prompt-and-instructions](../prompt-and-instructions/index.md)
- [source-workflows](../source-workflows/index.md)
- [federation.md](../federation.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 as a local practice topic for AI context design.
- Maintained on 2026-06-23 by splitting context architecture concepts into durable leaf pages.
- Maintained on 2026-06-27 with a dedicated state externalization and rehydration leaf for context-loss recovery practice.
