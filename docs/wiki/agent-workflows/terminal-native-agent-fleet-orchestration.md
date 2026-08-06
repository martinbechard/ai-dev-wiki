---
type: "Topic"
title: "Terminal-Native Agent Fleet Orchestration"
description: "Terminal-native agent fleet orchestration coordinates multiple coding-agent sessions through terminals, worktrees, task ledgers, and review handoffs."
tags: ["agent-workflows"]
---

# Terminal-Native Agent Fleet Orchestration

## Current Understanding

Terminal-native agent fleet orchestration coordinates multiple coding-agent sessions through terminals, worktrees, task ledgers, and review handoffs. It differs from a framework CLI that only scaffolds, serves, evaluates, or deploys a multi-agent application whose topology lives in code.

The [CLI multi-agent orchestration research source](../../../raw/processed/project-wiki-research-2026-08-05-cli-multi-agent-orchestration.md) separates terminal-native fleet managers from interactive subagent harnesses and application-framework CLIs. Broad Agent Orchestrator, Gas Town, Claude Squad, Claude Code, CrewAI, LangGraph, Deep Agents, Google ADK, Microsoft Agent Framework, Mastra, OpenAI Agents SDK, and provider background belongs upstream; locally, this page owns the selection rule for software-delivery fleets that run above individual coding-agent CLIs.

A terminal-native fleet manager is relevant when the coordination surface is the repository, task tracker, worktree, CI run, pull request, terminal session, and merge queue. The operating question is not only which model or framework is strongest, but whether the fleet layer preserves isolation, durable task state, review capacity, conflict handling, permission boundaries, and reproducible handoffs across multiple agents.

Application-framework CLIs remain useful, but they should not be evaluated as fleet consoles unless the terminal actually starts, assigns, supervises, and reconciles independent workers. A development CLI that runs a local server or invokes one root agent may be part of the harness lifecycle while leaving multi-agent coordination inside the application.

## Practice Boundaries

- Distinguish terminal-native fleet orchestration from application-framework lifecycle commands before recommending a CLI tool.
- Prefer worktree or workspace isolation when multiple coding agents mutate the same repository family.
- Require a durable task ledger, owner or coordinator assignment, progress state, and merge or handoff criteria before parallel agent work scales.
- Route issue, pull-request, CI, and review-comment feedback back to the responsible worker or coordinator with auditable state.
- Compare provider-neutral fleet claims by prompt, permission, tool, resume, and result-format compatibility, not only by whether several agent CLIs can launch.
- Stop fan-out when review, verification, or merge-conflict capacity is the bottleneck.

## Authoritative Sources

- [CLI multi-agent orchestration research source](../../../raw/processed/project-wiki-research-2026-08-05-cli-multi-agent-orchestration.md)
- [subagent coordination](subagent-coordination.md)
- [delegated coding handoffs](delegated-coding-handoffs.md)
- [persistent agent workspaces](persistent-agent-workspaces.md)
- [terminal agent workflows](terminal-agent-workflows.md)
- [upstream AI coding agents hub](../../../upstream-ai-wiki/developer-tools/ai-coding-agents-and-autonomous-engineering-platforms.md)
- [upstream LangGraph](../../../upstream-ai-wiki/agentic-frameworks/langgraph.md)
- [upstream Deep Agents](../../../upstream-ai-wiki/agentic-frameworks/deep-agents.md)
- [upstream CrewAI](../../../upstream-ai-wiki/agentic-frameworks/crewai.md)
- [upstream Google ADK](../../../upstream-ai-wiki/agentic-frameworks/google-adk.md)
- [upstream Microsoft Agent Framework](../../../upstream-ai-wiki/agentic-frameworks/microsoft-agent-framework.md)
- [upstream Mastra](../../../upstream-ai-wiki/agentic-frameworks/mastra.md)
- [upstream OpenAI Agents SDK](../../../upstream-ai-wiki/agentic-frameworks/openai-agents-sdk.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [subagent coordination](subagent-coordination.md)
- [delegated coding handoffs](delegated-coding-handoffs.md)
- [persistent agent workspaces](persistent-agent-workspaces.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Open Questions

- Which terminal-native fleet managers can export task, session, review, and merge evidence in a provider-neutral format suitable for long-term audit?

## Maintenance Notes

- Created on 2026-08-05 from focused research on CLI multi-agent orchestration and terminal-native coding-agent fleet managers.
