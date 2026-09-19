---
type: "Topic"
title: "Agent Control Flow Selection"
description: "Agent control flow selection chooses fixed workflows, iterative agents, planner-executor structures, or harnessed long-horizon agents by development-task shape."
tags: ["agent-workflows"]
---

# Agent Control Flow Selection

## Current Understanding

Agent control flow selection chooses the outer orchestration pattern before choosing a framework or model. The [ReAct, Deep Agents, and workflow-selection research source](../../../raw/processed/project-wiki-research-2026-09-17-react-deep-agents-workflow-selection.md) distinguishes fixed workflows, iterative tool-using agents, planner-executor designs, and long-horizon harnesses as separate local development choices. Broad [LangGraph](../../../upstream-ai-wiki/agentic-frameworks/langgraph.md), [Deep Agents](../../../upstream-ai-wiki/agentic-frameworks/deep-agents.md), and LangChain stack facts stay upstream-owned.

Fixed workflows fit development tasks whose stages and transitions are known before execution, such as lint, test, approval, release, or checklist-driven validation. Iterative ReAct-style loops fit investigations where the next useful file, tool, or evidence source depends on previous observations. Planner-executor designs fit work where dependencies can be represented up front, while still allowing replanning when execution disproves the plan. Harnessed long-horizon agents fit only when context offloading, file work, delegated subagents, state persistence, and recovery justify the extra control surface.

The useful local rule is to classify the outer orchestration and inner executor separately. A fixed workflow can contain a ReAct-style node, a planner can delegate to iterative executors, and a Deep Agents-style harness can contain multiple control-flow shapes. Multiple agents, todos, or reactions to observations do not by themselves prove that ReAct is the governing architecture.

The September 18 raw sources add a productized coordinator-worker signal from [Claude Projects coverage](../../../raw/processed/2026-09-18/ai-dev-wiki-leaf-update-watch-2026-09-18T210205-0400.json) and the [topic news collector source entry for the Anthropic announcement](../../../raw/processed/2026-09-18/ai-dev-wiki-topic-news-collector-2026-09-19T003318Z.json). Broad Claude and Claude Code facts stay upstream-owned; locally, project-level agent orchestration should record:

- The coordinator that owns the goal.
- The worker thread or branch that owns each slice.
- The shared-memory update path.
- The merge or conflict evidence that proves workers rejoined the project safely.

## Practice Boundaries

- Prefer fixed workflows when required stages, evidence gates, and approvals are known before execution.
- Prefer iterative agent loops when investigation determines which tool or source should be inspected next.
- Prefer planner-executor separation when dependencies can be represented up front and execution results may require replanning.
- Evaluate long-horizon harnesses when file work, context offloading, delegated investigation, persistence, or recovery are required by the task.
- Classify outer orchestration separately from inner executors so framework names do not hide workflow control.
- Treat coordinator-worker project surfaces as long-horizon harnesses when they combine shared goals, parallel threads, per-thread branches, project memory, and conflict resolution.
- Measure completion quality, tool and model calls, latency, recovery, context handling, and gate observance before claiming one control flow is better.
- Route broad ReAct, LangGraph, Deep Agents, and planning-architecture background to the upstream AI wiki.

## Authoritative Sources

- [September 18 leaf update watch source](../../../raw/processed/2026-09-18/ai-dev-wiki-leaf-update-watch-2026-09-18T210205-0400.json)
- [September 18 topic news collector source](../../../raw/processed/2026-09-18/ai-dev-wiki-topic-news-collector-2026-09-19T003318Z.json)
- [ReAct, Deep Agents, and workflow-selection research source](../../../raw/processed/project-wiki-research-2026-09-17-react-deep-agents-workflow-selection.md)
- [use compose build workflow selection](use-compose-build-workflow-selection.md)
- [subagent coordination](subagent-coordination.md)
- [persistent agent workspaces](persistent-agent-workspaces.md)
- [upstream LangGraph](../../../upstream-ai-wiki/agentic-frameworks/langgraph.md)
- [upstream Deep Agents](../../../upstream-ai-wiki/agentic-frameworks/deep-agents.md)
- [upstream LangChain stack](../../../upstream-ai-wiki/agentic-frameworks/langchain-stack.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent workflows](index.md)
- [use compose build workflow selection](use-compose-build-workflow-selection.md)
- [subagent coordination](subagent-coordination.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-09-18 with coordinator-worker project orchestration, per-thread branch, shared-memory, and conflict-resolution evidence.
- Created on 2026-09-17 from source-backed research on ReAct, Deep Agents, planner-executor patterns, and workflow selection; next check should verify whether upstream technique leaves cover ReAct and planning architectures before adding more local detail.
