# Context Selection And Compaction

## Current Understanding

Context selection decides what evidence the model sees for a request. The model does not remember the repository; every step only knows the instructions, selected history, file excerpts, command output, tool results, and task details that the harness provides.

More context can reduce guessing, but it can also increase cost, latency, and distraction. Compaction summarizes, drops, or selects context so the useful evidence stays in view while unrelated history, stale files, and oversized tool output stay out of the request.

The [ADLC source](../../../raw/processed/ADLC Claude Code's New Lifecycle for AI Coding.md), [deep research workshop source](../../../raw/processed/Full Workshop Build Your Own Deep Research Agents - Louis-François Bouchard, Paul Iusztin, Samridhi.md), and [agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md) converge on the same operating rule: large context windows do not remove the need for selection. Context can rot before the nominal window is full, so the harness needs explicit context ownership, compaction rules, and source routing.

The [context engineering source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) reinforces the local production-infrastructure lens: scoped inputs, durable knowledge layers, retrieval rules, and context governance need to be designed before agents are allowed to run multi-step development or operations workflows. Broad context-engineering taxonomy stays upstream; this page keeps the local selection and compaction rule.

## Practice Boundaries

- Orient from repository structure, relevant modules, tests, package boundaries, and existing conventions before selecting context.
- Attach compiler errors, failing tests, stack traces, screenshots, runtime logs, and recent diffs when they are the evidence for the next step.
- Keep stable rules, exact file excerpts, failing assertions, recent diffs, and rerun commands in the request package when they support the task.
- Avoid sending the whole policy manual, full history, or unrelated exports when a targeted excerpt is enough.
- Use summaries for prior turns when exact transcripts are less useful than the current decision state.
- Re-select context after tool calls or verification output changes the diagnosis.
- Treat context rot as an operating risk, not only a token-limit problem.
- Keep context ownership visible so stale examples, stale policies, and obsolete source files can be removed from the agent diet.
- Define context sources, retrieval rules, and compaction ownership before enabling recurring or multi-step agent workflows.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Context router and knowledge layers](context-router-and-knowledge-layers.md)
- [Request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [ADLC source](../../../raw/processed/ADLC Claude Code's New Lifecycle for AI Coding.md)
- [Deep research workshop source](../../../raw/processed/Full Workshop Build Your Own Deep Research Agents - Louis-François Bouchard, Paul Iusztin, Samridhi.md)
- [Agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [thin context router](thin-context-router.md)
- [rules and knowledge layers](rules-and-knowledge-layers.md)
- [ai process layer and workflow state](../application-patterns/ai-process-layer-and-workflow-state.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on request context, token discipline, context windows, compaction, and evidence selection.
- Maintained on 2026-06-23 with public context-engineering guidance framed as production infrastructure for multi-step agents.
