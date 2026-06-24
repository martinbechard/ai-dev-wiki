# Agent Governance Infrastructure

## Current Understanding

Agent governance works best as infrastructure around the model loop. Policies for identity, authorization, allowed actions, monitoring, audit, rate limits, and accountability need to be enforced by the harness, gateway, platform, or tool server so the boundary still holds when a prompt, retrieved document, or generated action is hostile or mistaken.

The local governance questions before an agent acts are: which agent or tool actor is acting, who authorized it, what it is allowed to do, whether it is behaving as expected, and whether the action can be audited. Human accountability remains named even when the agent performs implementation work. Security and platform owners define policy boundaries; engineering teams build agents within those boundaries.

This page owns the local infrastructure pattern. Named platforms, cloud products, provider governance features, and broad agent-framework comparisons belong upstream unless they are needed to explain a local control boundary.

The [workspace agents source](../../../raw/processed/OpenAI Just Gave Every Team A Free Employee. Here's The Catch..md) is relevant locally because it describes governance as the adoption gate for agents that cross enterprise tools. The local pattern is least privilege by default: control who can build, publish, run, connect tools, approve actions, use personal connections, inspect history, analyze usage, and suspend an agent.

The [topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) adds public signals that agentic development governance is moving toward runtime inventory, policy enforcement, MCP and tool visibility, generated-output validation, verifiable identity, policy versioning, execution-environment evidence, and tool-call transcripts. Vendor-specific product coverage belongs upstream; locally, these signals support treating agent governance as run-level evidence infrastructure.

## Practice Boundaries

- Give each agent, workflow, and tool surface a clear identity and allowed-action set.
- Require human approval or policy approval for high-risk file, network, dependency, credential, external-system, or production-like actions.
- Validate tool requests through deterministic code before execution.
- Keep audit evidence for tool calls and materially important model-assisted actions when the work needs reviewability.
- Enforce budget, rate-limit, and consumption controls outside prompt wording.
- Keep user-visible transparency when an application experience lets an agent act on a user's behalf.
- Keep policy ownership separate from agent implementation so security rules are not rewritten by ordinary agent behavior.
- Prefer service accounts and scoped connectors for shared team agents when personal connections would create unclear delegation.
- Audit published agents regularly for audience, connector scope, approval requirements, and run history.
- Inventory installed agents, tool servers, MCP servers, plugins, and connectors that can affect development workflows.
- Capture run-level evidence for identity, policy version, execution environment, approvals, tool calls, and generated outputs when auditability matters.

## Authoritative Sources

- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [retrieval and tools practice](../retrieval-and-tools/rag-tools-and-mcp-practice.md)
- [Workspace agents source](../../../raw/processed/OpenAI Just Gave Every Team A Free Employee. Here's The Catch..md)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance controls for agents](governance-controls-for-agents.md)
- [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [application-patterns](../application-patterns/index.md)
- [adoption-and-operating-model](../adoption-and-operating-model/index.md)
- [agent ownership rosters](../adoption-and-operating-model/agent-ownership-rosters.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to separate infrastructure enforcement, identity, authorization, audit, and accountability from the broader governance-controls page.
- Maintained on 2026-06-23 with public runtime governance signals for agent inventory, policy enforcement, governed MCP, and run-level evidence.
