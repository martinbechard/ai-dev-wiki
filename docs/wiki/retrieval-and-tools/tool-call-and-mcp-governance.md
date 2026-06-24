# Tool Call And MCP Governance

## Current Understanding

Tool calls turn model intent into software-mediated action. The model requests an action with arguments, the harness validates schema and permissions, software executes outside the model, and the result becomes context for a continuation or final answer.

Dynamic context tools sit between retrieval and action. They let a model request targeted additional information when the application cannot know all needed context upfront. Action tools perform governed operations such as reading, writing, scheduling, querying, transforming, or updating external systems.

MCP is the local practice boundary for standardized tool access. It exposes typed tools through a server and client arrangement while credentials remain in the connector or server. Broad MCP ecosystem coverage belongs to the upstream [AI wiki MCP server index](../../../upstream-ai-wiki/mcp-servers/index.md); this page owns how local AI-assisted workflows should treat MCP as a governed access layer.

The [topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) adds a governed-execution lens for MCP and agent tools: tool governance should account for the acting identity, policy version, execution environment, runtime inventory, tool-call transcript, and generated-output validation. Vendor-specific governed MCP products remain upstream-owned; the local rule is that tool access should produce reviewable evidence when it can change code, data, infrastructure, or external systems.

## Practice Boundaries

- Describe tools with names, argument schemas, output contracts, and permission expectations.
- Validate tool arguments, user authority, workflow limits, and approval requirements before execution.
- Keep credentials in the harness, connector, or MCP server rather than exposing them in prompts.
- Log material tool requests, approvals, results, and failures when the workflow needs auditability.
- Prefer upfront retrieval when context is predictable and tool loops would add unnecessary cost.
- Use dynamic context tools when missing information is targeted and too large or uncertain for upfront context.
- Treat MCP servers as governed connectors, not as permission to bypass local approval rules.
- Record identity, policy, environment, approval, tool-call, and result evidence for high-impact agent tool use.
- Validate generated code or configuration outputs before they are accepted as tool results or committed artifacts.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [federation.md](../federation.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [RAG provenance ranking and chunking](rag-provenance-ranking-and-chunking.md)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [retrieval-and-tools](index.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold dynamic context, action-tool, and MCP governance practice.
- Maintained on 2026-06-23 with public governed-MCP and runtime agent governance signals.
