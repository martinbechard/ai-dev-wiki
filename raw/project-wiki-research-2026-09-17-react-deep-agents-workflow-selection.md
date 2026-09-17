# Project Wiki Research: ReAct, Deep Agents, and Workflow Selection

## Request

Capture the source-backed knowledge behind the conversation comparing LangGraph ReAct agents with Deep Agents and asking what a non-ReAct agent is. Prepared by Northstar on 2026-09-17 for later ingest.

## Existing Wiki Check

The first conversational answer checked local coverage and upstream LangGraph and Deep Agents leaves, then consulted current official documentation. The second answer was an unsourced general explanation. This report verifies and refines it; the conversation itself is not factual authority.

Checked local topic-index.md, agent-workflows/index.md, and federation.md, plus upstream topic-index.md and the LangGraph, Deep Agents, and LangChain stack leaves. Searches for ReAct and plan-and-execute in local workflows and upstream techniques/frameworks found no dedicated comparison. A LlamaIndex Workflows mention describes an example, not the conceptual distinction. Other React hits concern the UI library or ordinary prose. Existing framework pages establish the runtime/harness relationship but do not cleanly explain the architecture-selection question. Wiki status reported 125 pages, no missing required files, and zero lint findings earlier in this conversation.

## Research Scope

Local scope: selecting and evaluating control flow for AI-assisted development. Broad technique definitions and framework API facts are supporting evidence owned upstream. No durable wiki edits or upstream mutations are part of this capture.

## Source Inventory

All sources accessed 2026-09-17. Undated documentation is a current snapshot, not evidence of a release date.

- S1: [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629). Submitted 2022-10-06; revised 2023-03-10. Primary research, authoritative for the original method.
- S2: [Deep Agents overview, Python](https://docs.langchain.com/oss/python/deepagents/overview). No visible publication date. Official, version-sensitive capabilities and defaults.
- S3: [Deep Agents subagents](https://docs.langchain.com/oss/python/deepagents/subagents). No visible publication date. Official configuration and composition guidance.
- S4: [LangGraph v1 migration guide](https://docs.langchain.com/oss/python/migrate/langgraph-v1). No visible publication date. Official migration authority.
- S5: [Plan-and-Execute Agents](https://www.langchain.com/blog/planning-agents). Published 2024-02-13. Primary vendor architecture explanation; performance claims are not independent benchmarks.
- S6: [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents). Published 2024-12-19. Primary vendor taxonomy; the page warns that tooling has changed since publication. Use architectural distinctions, not historical tooling recommendations.

## Synthesis

### ReAct and the stack

ReAct interleaves model reasoning with actions and observations, letting external results inform subsequent decisions [S1]. In contemporary tool-calling discussions, “ReAct-style” often describes the model/tool feedback loop; this does not establish use of the original paper's exact prompting format or require exposing private reasoning traces. That distinction is an interpretive clarification.

The LangGraph prebuilt create_react_agent factory is deprecated in favor of langchain.agents.create_agent [S4]. This is an API migration, not the removal of the iterative agent pattern.

Deep Agents uses the same underlying tool-calling loop and adds a harness for context management and delegation. It provides filesystem tools with configurable backends, conversation summarization, and tool-result offloading. Filesystem support does not imply unrestricted host access; shell execution depends on backend support. The current Python overview says todo tracking is opt-in starting with v0.7, through TodoListMiddleware; earlier defaults differ. Persistent memory needs the appropriate storage configuration [S2].

Deep Agents subagents handle delegated work in separate contexts. Specialized configurations can use distinct prompts, tools, and models. A CompiledSubAgent can wrap a custom LangGraph graph, including an agent created with create_agent. Thus a ReAct-style agent may be a component inside a Deep Agents system [S3].

### Alternatives and correction to the conversation

Anthropic distinguishes predefined, code-directed workflows from agents whose models dynamically direct tool use. Under that taxonomy, a fixed pipeline or one-shot router is usually a workflow or component, not a full autonomous agent [S6]. Calling every non-ReAct system an agent obscures this boundary.

LangChain describes plan-and-execute as a planner plus executors, with replanning after execution. Therefore the earlier description of a complete upfront plan followed without reconsideration is only a restricted variant. ReWOO is a clearer named alternative: a planner defines tool steps and references to intermediate results; a worker resolves them; a solver produces the answer. LLMCompiler instead schedules a dependency graph and can replan or finish through a joiner [S5].

Inference: classify the outer orchestration and inner executor separately. A planner can delegate to ReAct executors; a fixed workflow can contain a ReAct node. Multiple agents, a todo list, or reacting to observations does not alone determine whether the implementation uses ReAct.

### Development selection and evaluation implications

The following are recommendations inferred from the sources, not measured results or an adopted project decision:

- Use a fixed workflow when required stages and transitions are known, such as validation and approval gates.
- Use an iterative agent when investigation determines which tool or evidence is needed next.
- Evaluate Deep Agents when substantial file work, context offloading, and delegated investigation justify its harness configuration.
- Consider planner/executor separation when dependencies can be represented upfront. Do not assume lower latency, cost, or higher accuracy without workload measurements.
- Evaluate completion quality, tool/model calls, latency, recovery, context handling, and observance of required gates. A plan or harness does not itself prove reliable completion.

## Named Entities And Concepts

ReAct; LangGraph; LangChain create_agent; Deep Agents; CompiledSubAgent; TodoListMiddleware; ReWOO; LLMCompiler; plan-and-execute; workflow versus agent; control-flow ownership; context isolation; harness selection.

## Candidate Wiki Destinations

- Local: a focused agent-workflows leaf for choosing and evaluating agent control flow, linked from its hub. Preserve only the development-practice lens.
- Upstream AI wiki: technique definitions for ReAct and planning architectures, and API/default updates in the existing framework leaves. Record an upstream routing request during ingest; do not create local encyclopedia duplicates or mutate upstream through its symlink.

## Existing Pages To Link

- [Local workflow hub](../docs/wiki/agent-workflows/index.md)
- [Local workflow selection](../docs/wiki/agent-workflows/use-compose-build-workflow-selection.md)
- [Local subagent coordination](../docs/wiki/agent-workflows/subagent-coordination.md)
- [Federation rules](../docs/wiki/federation.md)
- [Upstream LangGraph](../upstream-ai-wiki/agentic-frameworks/langgraph.md)
- [Upstream Deep Agents](../upstream-ai-wiki/agentic-frameworks/deep-agents.md)
- [Upstream LangChain stack](../upstream-ai-wiki/agentic-frameworks/langchain-stack.md)

## Conflicts Or Uncertainties

“Agent” has no universal boundary; attribute the workflow distinction to its source. The original ReAct method and modern ReAct-style tool loops should not be treated as exact synonyms. Deep Agents defaults differ by version and language; Python v0.7 planning behavior must not be generalized to all versions. This report does not establish a currently installed package version.

## Excluded Sources Or Claims

Excluded search snippets, forums, and mirrored documentation as final authority. Initial fetches of the Anthropic engineering page and API reference failed; the Anthropic research URL resolved successfully, and the official migration guide supplies the API evidence. Excluded the earlier robot-policy example from durable synthesis because no robotics source was researched. No universal performance advantage, guaranteed autonomy, or mandatory multi-agent topology is claimed.

## Privacy And Sensitivity Notes

Public sources and public conceptual questions only. No credentials or private project content were sent to external services. Local wiki links record coverage and routing, not public evidence.

## Follow-Up For Ingest

Keep this file in raw until normal synthesis and verification complete. Extract the local workflow-selection lens, route broad facts upstream, retain the plan-and-execute correction, and recheck version-sensitive defaults. No docs/wiki files were changed by this research capture.
