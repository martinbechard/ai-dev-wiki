# Project Wiki Research: CLI Multi-Agent Orchestration

## Request

Identify leading frameworks and tools that can orchestrate multiple agents, with particular emphasis on command-line operation. Clarify which products actually coordinate agents from a terminal and which merely use a CLI to start, test, or deploy an agent application.

## Existing Wiki Check

Checked on 2026-08-05:

- `docs/wiki/federation.md`
- `docs/wiki/topic-index.md`
- `docs/wiki/application-patterns/declarative-agent-workflow-artifacts.md`
- `upstream-ai-wiki/agentic-frameworks/index.md`
- `upstream-ai-wiki/agentic-frameworks/langchain-stack.md`
- `upstream-ai-wiki/agentic-frameworks/langgraph.md`
- `upstream-ai-wiki/agentic-frameworks/deep-agents.md`
- `upstream-ai-wiki/agentic-frameworks/crewai.md`
- `upstream-ai-wiki/agentic-frameworks/google-adk.md`
- `upstream-ai-wiki/agentic-frameworks/microsoft-agent-framework.md`
- `upstream-ai-wiki/agentic-frameworks/mastra.md`
- `upstream-ai-wiki/agentic-frameworks/openai-agents-sdk.md`

The upstream wiki has individual framework coverage, but neither wiki currently has a focused comparison of terminal-native multi-agent operators versus multi-agent application frameworks with lifecycle CLIs. This report fills that adoption and operating-model gap without creating downstream encyclopedia pages for upstream-owned entities.

## Research Scope

The comparison uses three distinct meanings of “CLI multi-agent orchestration”:

1. **Terminal-native fleet orchestration:** the CLI starts, isolates, assigns, supervises, and reconciles multiple agent processes.
2. **Interactive multi-agent harness:** one terminal agent delegates to subordinate agents and synthesizes their work.
3. **Application-framework CLI:** the framework supports multi-agent applications, while its CLI primarily scaffolds, runs, serves, evaluates, or deploys the application.

“Leading” here means a combination of current official documentation, a usable CLI surface, explicit multi-agent coordination, active public implementation, and a differentiated operating model. Popularity counts were not used as the primary ranking criterion.

Only public vendor documentation and official public repositories were used. Sources were accessed on 2026-08-05.

## Source Inventory

### Terminal-native operators

1. **Agent Orchestrator by ComposioHQ**
   - URL: https://github.com/ComposioHQ/agent-orchestrator
   - Date: official repository accessed 2026-08-05; search index described the repository as published approximately two months earlier.
   - Evidence: `ao start` launches an orchestrator and dashboard; each issue receives an agent in an isolated worktree; CI failures and review comments can be routed back to workers; agent plugins include Claude Code, Codex, Aider, Cursor, OpenCode, and Kimi Code; runtime, workspace, tracker, SCM, notification, and terminal layers are pluggable.
   - Reliability: primary source, official repository.

2. **Gas Town**
   - URL: https://github.com/gastownhall/gastown
   - Integration guide: https://github.com/gastownhall/gastown/blob/main/docs/agent-provider-integration.md
   - Date: official repository accessed 2026-08-05; search index described the repository as published approximately three months earlier.
   - Evidence: multi-agent workspace manager for Claude Code, Copilot, Codex, Gemini, and other agent CLIs; uses persistent git-backed work tracking, identities, roles, mailboxes, handoffs, session lifecycle, and a merge queue; orchestration is loosely coupled through terminal sessions and environment variables.
   - Reliability: primary source, official repository.

3. **Claude Squad**
   - URL: https://github.com/smtg-ai/claude-squad
   - Date: latest indexed release was 2026-05-23; accessed 2026-08-05.
   - Evidence: `cs` is a terminal UI for running multiple Claude Code, Codex, Gemini, OpenCode, Amp, or Aider sessions; it isolates tasks with git worktrees and terminal sessions and lets the operator inspect, resume, commit, push, and check out results.
   - Reliability: primary source, official repository.

4. **Claude Code agent teams**
   - URL: https://code.claude.com/docs/en/agent-teams
   - Parallel-agent comparison: https://code.claude.com/docs/en/agents
   - Date: official documentation accessed 2026-08-05; no stable publication date visible.
   - Evidence: a team lead coordinates independent Claude Code sessions through a shared task list and inter-agent messaging; teammates can self-claim tasks and communicate directly; terminal presentation can be in-process or split-pane. The feature is explicitly experimental, has resumption and shutdown limitations, does not support nested teams, and does not isolate teammates in separate worktrees.
   - Reliability: primary source, official Anthropic documentation.

### Multi-agent frameworks with CLI surfaces

5. **Deep Agents and Deep Agents Code**
   - Subagents: https://docs.langchain.com/oss/python/deepagents/subagents
   - Async subagents: https://docs.langchain.com/oss/python/deepagents/async-subagents
   - Terminal harness: https://docs.langchain.com/oss/python/contributing/code
   - Date: official documentation accessed 2026-08-05; no stable publication date visible.
   - Evidence: Deep Agents supplies supervisor/subagent delegation, filesystem and shell tooling, and parallel asynchronous subagents. CLI users can define subagents through `AGENTS.md`. Deep Agents Code provides an interactive terminal, while `deepagents-cli` supports initialization, development, and deployment.
   - Reliability: primary source, official LangChain documentation.

6. **CrewAI**
   - URL: https://docs.crewai.com/
   - Official repository: https://github.com/crewAIInc/crewAI
   - Concepts: https://docs.crewai.com/core-concepts/Agents
   - Date: indexed repository release 1.14.7 dated 2026-06-11; sources accessed 2026-08-05.
   - Evidence: Crews model autonomous role-based teams; Flows provide deterministic, event-driven control and can invoke Crews. `crewai run` executes a packaged project, and the CLI also supports setup and managed deployment workflows. Hierarchical processes provide a manager that delegates and validates work.
   - Reliability: primary sources, official documentation and repository.

7. **Google Agent Development Kit and Agents CLI**
   - CLI: https://google.github.io/agents-cli/cli/
   - Date: official documentation accessed 2026-08-05; no stable publication date visible.
   - Evidence: the CLI builds, evaluates, runs, and deploys ADK agents. `agents-cli run` can invoke local or remote agents; remote operation supports A2A and ADK streaming. Multi-agent topology is defined in the ADK application, while the CLI invokes its root agent and manages sessions, files, and telemetry.
   - Reliability: primary source, official Google documentation.

8. **LangGraph**
   - CLI: https://docs.langchain.com/langsmith/cli
   - Runtime: https://docs.langchain.com/oss/python/langgraph/overview
   - Multi-agent subgraphs: https://docs.langchain.com/oss/python/langgraph/use-subgraphs
   - Custom multi-agent workflows: https://docs.langchain.com/oss/python/langchain/multi-agent/custom-workflow
   - Date: official documentation accessed 2026-08-05; no stable publication date visible.
   - Evidence: LangGraph is a low-level durable runtime for long-running stateful agents and supports multi-agent graphs, subgraphs, branches, loops, and parallel execution. Its CLI primarily builds, serves, and deploys an Agent Server (`langgraph dev`, `build`, `up`, and related commands); it is not itself an interactive terminal supervisor for an agent fleet.
   - Reliability: primary source, official LangChain documentation.

9. **Microsoft Agent Framework**
   - Orchestrations: https://learn.microsoft.com/en-us/agent-framework/workflows/orchestrations/
   - Handoff orchestration: https://learn.microsoft.com/en-us/agent-framework/user-guide/workflows/orchestrations/handoff
   - Declarative workflows: https://learn.microsoft.com/en-us/agent-framework/workflows/declarative
   - DevUI: https://learn.microsoft.com/en-us/agent-framework/user-guide/devui/
   - Date: DevUI page updated 2026-07-10; sources accessed 2026-08-05.
   - Evidence: built-in sequential, concurrent, handoff, group-chat, and Magentic orchestration patterns; declarative YAML supports agents, tools, control flow, and human input. `devui` is a CLI-launched development and test host, but Microsoft explicitly says it is not for production.
   - Reliability: primary source, official Microsoft documentation.

10. **Mastra**
    - Multi-agent workflow example: https://mastra.ai/en/examples/agents/multi-agent-workflow
    - Current documentation index: https://mastra.ai/en/docs/scorers/overview
    - CLI Actions: https://mastra.ai/articles/api-cli-mcp
    - Date: CLI Actions article dated 2026-07-17; sources accessed 2026-08-05.
    - Evidence: TypeScript agents can be chained in workflows and coordinated with supervisor/worker patterns. The CLI covers initialization, development, build, start, and lint; CLI Actions expose production actions in the terminal. Agent Networks provide higher-level coordination but are marked experimental in current documentation.
    - Reliability: primary source, official Mastra documentation.

## Synthesis

### The key distinction

A CLI does not make a framework CLI-native. LangGraph, Google ADK, Microsoft Agent Framework, CrewAI, and Mastra all have command-line tools, but most of those commands operate the lifecycle of an application whose multi-agent topology was defined in code or configuration. Agent Orchestrator, Gas Town, Claude Squad, and Claude Code agent teams instead make the terminal itself part of the coordination surface.

### Leading choices for direct command-line orchestration

| Candidate | What the terminal actually controls | Provider posture | Best fit | Main caveat |
|---|---|---|---|---|
| Agent Orchestrator | Worker creation, worktree isolation, issue/PR lifecycle, CI and review feedback, session supervision | Multiple coding-agent CLIs through plugins | A team wants one operational layer above Codex, Claude Code, Aider, Cursor, or OpenCode | Young project; optimized for software-delivery agents rather than arbitrary business-agent graphs |
| Gas Town | Persistent work ledger, roles, dispatch, mail, handoffs, sessions, and merge queue | Multiple coding-agent CLIs through loose terminal integration | Long-running local agent fleets where work must survive context and process restarts | Heavier operating model and prerequisites; introduces its own role and work-tracking vocabulary |
| Claude Code agent teams | Lead/teammate creation, shared tasks, self-claiming, direct inter-agent messaging, terminal panes | Claude Code only | The best integrated terminal team experience when Anthropic lock-in is acceptable | Experimental; no nested teams, no team-level worktree isolation, and known resume/shutdown limitations |
| Claude Squad | Multiple isolated sessions and worktrees in a compact TUI | Multiple local agent CLIs | A human wants a simple console for several independent coding tasks | Multiplexes sessions but does not provide a rich autonomous coordinator, shared task ledger, or inter-agent protocol |

**Assessment:** Agent Orchestrator is the strongest direct match for “orchestrate several coding agents from the command line” when provider choice and delivery lifecycle matter. Gas Town is stronger when durable shared work state and larger persistent fleets matter. Claude Squad is the simplest option, but it is a terminal manager more than a multi-agent framework. Claude Code agent teams provide the most vertically integrated experience, at the cost of provider lock-in and current experimental constraints.

### Leading choices for building a CLI-invoked multi-agent application

| Candidate | Multi-agent abstraction | CLI role | Best fit | Main caveat |
|---|---|---|---|---|
| CrewAI | Role-based Crews plus deterministic Flows; hierarchical manager process | Scaffold, install, run, and deploy a packaged crew/flow | Fastest route to an understandable Python multi-agent application | Less explicit control over durable graph state than LangGraph; managed operations point toward CrewAI AMP |
| Deep Agents | Supervisor/subagent harness with shell, filesystem, and parallel background work | Interactive terminal harness plus init/dev/deploy tooling | Coding, research, and long-horizon agents that need an opinionated batteries-included shell | Remains part of the LangChain/LangGraph product family, so it is not a competing independent stack |
| Google ADK + Agents CLI | Composable agents and remote handoffs, including A2A | Build, evaluate, run, deploy, and remotely invoke a root agent | Google Cloud/Gemini environments or A2A-oriented interoperability | Multi-agent coordination is authored in the application rather than interactively assembled by the CLI |
| LangGraph | Explicit durable state graph with subgraphs, handoffs, loops, branches, and parallelism | Run/build/deploy an Agent Server | Bespoke, stateful, auditable orchestration where control matters more than convenience | The CLI is a server lifecycle interface, not a fleet console |
| Microsoft Agent Framework | Sequential, concurrent, handoff, group-chat, Magentic, and declarative workflows | Launch DevUI and development/test hosts | .NET/Python enterprise systems, Azure alignment, or YAML-authored workflows | DevUI is not a production runtime; the framework is not primarily terminal-operated |
| Mastra | TypeScript workflows and experimental Agent Networks | Dev/build/start plus CLI Actions | TypeScript teams wanting one agent/workflow/API/CLI toolchain | The higher-level Network abstraction is experimental |

**Assessment:** CrewAI is the clearest independent framework competitor to the LangChain stack when ease of multi-agent authoring and `crewai run` matter. Google ADK is the strongest ecosystem-backed alternative with a serious lifecycle CLI. Microsoft Agent Framework is stronger for enterprise orchestration patterns than for terminal operation. Mastra is the most interesting TypeScript-native option, but its agent-network layer is not yet the safest default.

### Where OpenAI Agents SDK fits

OpenAI Agents SDK remains a leading multi-agent library, particularly for handoffs, agents-as-tools, tracing, and OpenAI-hosted model workflows. It was not placed in the CLI-leading table because it does not currently present a canonical general-purpose CLI that supervises a multi-agent application or external coding-agent fleet. Codex itself is a terminal agent product, not the SDK's orchestration shell. This exclusion is about the requested CLI emphasis, not the quality of the SDK.

### Practical shortlist

- **Orchestrate Codex, Claude Code, Aider, or similar coding agents across issues and PRs:** start with Agent Orchestrator.
- **Run a durable local “agent organization” with persistent tasks, mail, roles, and merge coordination:** evaluate Gas Town.
- **Manage several independent terminal agents with minimal ceremony:** use Claude Squad.
- **Accept Anthropic lock-in for a cohesive lead/teammate terminal:** test Claude Code agent teams, but treat it as experimental.
- **Build a provider-flexible Python multi-agent application with a simple run command:** start with CrewAI.
- **Build an explicit durable state machine:** use LangGraph; add Deep Agents when an opinionated supervisor/subagent shell is useful.
- **Prioritize A2A and Google deployment workflows:** use Google ADK plus Agents CLI.
- **Prioritize .NET/Azure or declarative enterprise workflows:** use Microsoft Agent Framework.
- **Use TypeScript end to end:** evaluate Mastra, while isolating experimental Agent Network dependencies.

### Direction of travel

The market is not converging on one universal framework. It is splitting into three layers:

1. **Durable application runtimes** are becoming servers and deployment targets; their CLIs operate builds, local development, evaluation, and deployment.
2. **Coding-agent fleet managers** are becoming process- and repository-level control planes, using terminal sessions, worktrees, task ledgers, issue trackers, CI, and pull requests. These tools often interoperate with agents from several vendors because the integration boundary is the agent CLI and repository, not the model API.
3. **Vertically integrated agent products** are absorbing coordination into the native terminal experience. Claude Code agent teams are the clearest current example: the coordination UX is strong, but workers, task machinery, permissions, and runtime are all inside one vendor product.

This means CLI-first multi-agent orchestration is trending away from being merely a feature of an application SDK. For software delivery, the most interoperable layer is increasingly above the individual agent CLI, where worktrees, tasks, CI, and PRs provide common coordination primitives.

## Named Entities And Concepts

- Agent Orchestrator
- ComposioHQ
- Gas Town
- Claude Squad
- Claude Code
- Claude Code agent teams
- Codex CLI
- Aider
- OpenCode
- Gemini CLI
- Deep Agents
- Deep Agents Code
- LangGraph
- LangChain
- LangSmith
- CrewAI
- CrewAI AMP
- Google Agent Development Kit
- Agents CLI
- Agent2Agent Protocol (A2A)
- Microsoft Agent Framework
- DevUI
- Mastra
- Agent Networks
- OpenAI Agents SDK
- terminal-native fleet orchestration
- interactive multi-agent harness
- application-framework CLI
- git worktrees
- terminal sessions
- persistent task ledger
- inter-agent messaging
- supervisor/worker pattern
- handoff orchestration
- durable execution

## Candidate Wiki Destinations

Recommended downstream ingest destinations:

1. `docs/wiki/agent-workflows/subagent-coordination.md` — add the distinction between in-process subagents, communicating agent teams, and external CLI fleets.
2. `docs/wiki/application-patterns/agent-harness-components.md` — add terminal fleet manager, worktree isolation, persistent task ledger, and delivery feedback loop as separable harness components.
3. `docs/wiki/agent-workflows/delegated-coding-handoffs.md` — add issue/PR/CI feedback routing and restart-safe handoff considerations.
4. `docs/wiki/application-patterns/declarative-agent-workflow-artifacts.md` — link declarative workflow configuration to CLI lifecycle operation without implying that a development CLI is a production orchestrator.
5. Upstream AI wiki — create or update broad entity leaves for Agent Orchestrator, Gas Town, and Claude Squad if they are judged durable enough for ecosystem coverage.

## Existing Pages To Link

- `docs/wiki/federation.md`
- `docs/wiki/agent-workflows/subagent-coordination.md`
- `docs/wiki/agent-workflows/delegated-coding-handoffs.md`
- `docs/wiki/application-patterns/agent-harness-components.md`
- `docs/wiki/application-patterns/declarative-agent-workflow-artifacts.md`
- `upstream-ai-wiki/agentic-frameworks/langgraph.md`
- `upstream-ai-wiki/agentic-frameworks/deep-agents.md`
- `upstream-ai-wiki/agentic-frameworks/crewai.md`
- `upstream-ai-wiki/agentic-frameworks/google-adk.md`
- `upstream-ai-wiki/agentic-frameworks/microsoft-agent-framework.md`
- `upstream-ai-wiki/agentic-frameworks/mastra.md`
- `upstream-ai-wiki/agentic-frameworks/openai-agents-sdk.md`

## Conflicts Or Uncertainties

- Agent Orchestrator and Gas Town are recent projects. Their scope is unusually relevant, but operational maturity should be validated through a bounded pilot before organizational adoption.
- “Provider-neutral” for terminal fleet managers means they can launch several vendors' agent CLIs. It does not mean prompts, permissions, tool semantics, resumability, or result formats are standardized across those agents.
- Claude Code agent teams have a strong coordination model, but the official documentation labels the feature experimental and lists concrete lifecycle limitations.
- Mastra's CLI and ordinary workflows are established surfaces, while Agent Networks are explicitly experimental.
- A development server, playground, or deployment CLI is not evidence that the terminal itself performs live multi-agent coordination.
- The recommended ranking is task-relative. Application agents, coding agents, and long-running software-delivery fleets have different orchestration requirements.

## Excluded Sources Or Claims

- Third-party comparison articles and generic “best multi-agent framework” lists were excluded because official product documentation was available.
- Repository star counts were observed but not used as decisive evidence of production maturity or architectural fit.
- Marketing claims about performance, enterprise readiness, or maximum fleet size were not treated as independently validated benchmarks.
- OpenAI Agents SDK was excluded from the CLI-leading ranking because its official multi-agent surface is library-first rather than a general multi-agent operator CLI.
- AutoGen, Semantic Kernel, LlamaIndex Workflows, PydanticAI, Agno, and Haystack remain relevant application frameworks, but the reviewed official surfaces did not make them stronger answers to this specifically CLI-centered request than the shortlisted candidates.

## Privacy And Sensitivity Notes

No private workspace content, personal data, company-confidential information, credentials, or local source code was sent to external services. Web research used public vendor documentation and official public repositories only.

## Follow-Up For Ingest

1. Verify Agent Orchestrator and Gas Town with small, disposable repositories before making durability, security, or fleet-scale claims.
2. Decide whether the downstream wiki should add a durable “CLI agent fleet orchestration” practice leaf or distribute the concepts across the existing coordination, harness, and handoff pages.
3. Route broad entity coverage for Agent Orchestrator, Gas Town, and Claude Squad to the upstream AI wiki.
4. During ingest, preserve the three-way distinction between terminal-native operators, interactive multi-agent harnesses, and application-framework CLIs.
5. Recheck the experimental status of Claude Code agent teams and Mastra Agent Networks before relying on them in prescriptive guidance.
