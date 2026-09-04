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

The [GitHub Copilot stacked sessions clipping](../../../raw/processed/github-copilot-stacked-sessions-and-pull-requests.md) adds a managed-app comparison point. Stacked sessions and stacked pull requests solve the same delivery pressure as terminal-native fleets at the source-control layer: keep a modernization effort split into ordered work packages, preserve prior session context, close or redirect an unfit branch, and target each pull request at the branch below it. The local fleet rule is to preserve the same chain evidence even when the coordination surface is a managed app rather than terminals.

The [August 31 leaf update watch source](../../../raw/processed/2026-08-31/ai-dev-wiki-leaf-update-watch-2026-08-31T210122-0400.json) adds coding-agent manager comparison evidence. Fleet selection should compare editor-first agents, terminal agents, cloud delegation, and manager layers by execution location, multi-agent isolation, approval handling, review flow, scheduling, and monitoring support. Broad product coverage stays upstream; locally, the durable rule is that a manager layer is useful only when it improves coordination evidence and review throughput without hiding workspace, permission, or merge-state boundaries.

The September 3 [topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json) adds worktree-isolation and customer-controlled execution evidence:

- Fleet orchestration should assign task, branch, worktree, agent identity, runtime resources, and merge path per worker.
- Managed or cloud agent surfaces should still record where side effects execute and who controls that worker.

## Practice Boundaries

- Distinguish terminal-native fleet orchestration from application-framework lifecycle commands before recommending a CLI tool.
- Prefer worktree or workspace isolation when multiple coding agents mutate the same repository family.
- Require a durable task ledger, owner or coordinator assignment, progress state, and merge or handoff criteria before parallel agent work scales.
- Route issue, pull-request, CI, and review-comment feedback back to the responsible worker or coordinator with auditable state.
- Compare provider-neutral fleet claims by prompt, permission, tool, resume, and result-format compatibility, not only by whether several agent CLIs can launch.
- Stop fan-out when review, verification, or merge-conflict capacity is the bottleneck.
- Preserve stack order, base branch, closed or superseded attempt, dependent pull request, and reviewer handoff evidence when work is split into stacked sessions.
- Treat managed stacked-session products as source-control orchestration surfaces; broad product background remains upstream.
- Compare fleet managers by execution location, multi-agent isolation, approval flow, review surface, scheduling, monitoring, and exported coordination evidence.
- Assign one task, branch, worktree, agent identity, port range, database or volume scope, environment-file owner, and merge path per parallel worker when runtime collisions could affect evidence.
- Record whether side effects run in the local checkout, managed worktree, cloud sandbox, or customer-controlled execution worker before comparing fleet results.

## Authoritative Sources

- [CLI multi-agent orchestration research source](../../../raw/processed/project-wiki-research-2026-08-05-cli-multi-agent-orchestration.md)
- [GitHub Copilot stacked sessions clipping](../../../raw/processed/github-copilot-stacked-sessions-and-pull-requests.md)
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
- [August 31 leaf update watch source](../../../raw/processed/2026-08-31/ai-dev-wiki-leaf-update-watch-2026-08-31T210122-0400.json)
- [September 3 topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json)

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
- Maintained on 2026-08-05 with stacked-session and stacked-pull-request chain evidence for managed app coordination.
- Maintained on 2026-08-31 with execution-location, isolation, approval, review, scheduling, monitoring, and coordination-evidence criteria for coding-agent manager layers.
- Maintained on 2026-09-03 with one-task-one-worktree worker isolation, runtime-resource reservation, customer-controlled execution, and side-effect locality evidence.
