---
type: "Topic"
title: "Deep Research And Writing Workflows"
description: "Deep research workflows need more autonomy than finished writing workflows."
tags: ["agent-workflows"]
---

# Deep Research And Writing Workflows

## Current Understanding

Deep research workflows need more autonomy than finished writing workflows. The [deep research workshop source](../../../raw/processed/Full Workshop Build Your Own Deep Research Agents - Louis-François Bouchard, Paul Iusztin, Samridhi.md) frames research as a goal-directed loop that plans, searches, inspects sources, pivots, filters evidence, and compiles a cited artifact. The same source treats writing as a tighter workflow with explicit guidance, few-shot examples, and reviewer feedback because writing quality suffers when open-ended exploration leaks into final prose.

The local practice is to separate exploratory research from constrained production. Research agents earn autonomy when the task requires branching across public sources and evidence types. Writing systems should prefer deterministic structure, style examples, review loops, and acceptance criteria so the output is grounded and not generic.

## Practice Boundaries

- Use an agentic loop for research when the system must decide which sources to inspect, when to pivot, and how to gather enough evidence.
- Use a constrained workflow for writing when the output needs consistent voice, structure, citations, and reviewable quality.
- Keep raw findings, source evidence, and compiled claims separate until review validates the synthesis.
- Prefer evaluator-optimizer loops for prose quality only when the reviewer has a clear rubric and examples.
- Treat broad frameworks and MCP products as upstream-owned unless the local page is documenting the research or writing workflow pattern.

## Authoritative Sources

- [Deep research workshop source](../../../raw/processed/Full Workshop Build Your Own Deep Research Agents - Louis-François Bouchard, Paul Iusztin, Samridhi.md)
- [use compose build workflow selection](use-compose-build-workflow-selection.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [use compose build workflow selection](use-compose-build-workflow-selection.md)
- [subagent coordination](subagent-coordination.md)
- [RAG provenance ranking and chunking](../retrieval-and-tools/rag-provenance-ranking-and-chunking.md)
- [judge grader boundaries](../verification-and-evals/judge-grader-boundaries.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold the research-agent versus writing-workflow boundary.
