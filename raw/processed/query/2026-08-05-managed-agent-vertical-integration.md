# Query Fragment: Managed Agent Vertical Integration

## Query Asked

Does vertically integrated agent infrastructure mean that complementary cross-cutting concerns are proprietary and do not interoperate with non-vendor tools?

## Answer Summary

Vertical integration means one vendor supplies several adjacent layers, such as the model, agent harness, built-in tools, session state, sandbox execution, control plane, and hosted operations. It does not by itself mean that every layer is closed.

For Claude Managed Agents, the tool and execution edges are extensible: agents can call custom JSON-Schema tools, connect to MCP servers, and use self-hosted sandboxes. The portability boundary is higher in the stack. Managed agents require Claude models, use Anthropic-specific agent, session, event, permission, and versioning semantics, and retain managed session history, sandbox state, and outputs server-side. A self-hosted sandbox keeps execution and selected data in customer infrastructure, but Anthropic still owns the managed control plane and agent-loop contract.

The practical selection rule is to evaluate portability layer by layer. Tool interoperability can be strong while model substitution, runtime substitution, state migration, and operational-control portability remain weak.

## Wiki Pages Consulted

- [Portable Agent Skills And Runbooks](../../docs/wiki/adoption-and-operating-model/portable-agent-skills-and-runbooks.md)
- [Durable Instructions And Skill Files](../../docs/wiki/adoption-and-operating-model/durable-instructions-and-skill-files.md)
- [Agent Harness Components](../../docs/wiki/application-patterns/agent-harness-components.md)
- [Tool Call And MCP Governance](../../docs/wiki/retrieval-and-tools/tool-call-and-mcp-governance.md)

## Authoritative Sources Consulted

- [Claude Managed Agents overview](https://platform.claude.com/docs/en/managed-agents/overview)
- [Claude Managed Agents agent setup](https://platform.claude.com/docs/en/managed-agents/agent-setup)
- [Claude Managed Agents tools](https://platform.claude.com/docs/en/managed-agents/tools)
- [Claude Managed Agents self-hosted sandbox security](https://platform.claude.com/docs/en/managed-agents/self-hosted-sandboxes-security)
- [Claude Agent SDK Python repository](https://github.com/anthropics/claude-agent-sdk-python)

## Durable Concepts Detected

- Vertical integration is distinct from closed integration.
- Portability should be evaluated separately for models, prompts and skills, tools and protocols, execution environments, durable state, telemetry, and control-plane semantics.
- MCP and custom tools reduce tool lock-in but do not make a vendor-managed agent runtime model-neutral or control-plane-neutral.
- Self-hosted execution does not necessarily mean a self-hosted agent control plane.
- Domain state and business records should remain outside vendor session state when provider substitution or audit portability matters.

## Candidate Wiki Destinations

- Extend `docs/wiki/adoption-and-operating-model/portable-agent-skills-and-runbooks.md` with a layer-by-layer portability evaluation rule.
- Consider a focused adoption leaf for managed-agent portability and vendor control-plane boundaries if future sources add cross-provider comparisons.

## Existing Pages To Link

- `docs/wiki/application-patterns/agent-harness-components.md`
- `docs/wiki/retrieval-and-tools/tool-call-and-mcp-governance.md`
- `docs/wiki/adoption-and-operating-model/durable-instructions-and-skill-files.md`

## Open Questions

- Which agent, session, trace, and memory artifacts can each managed provider export in a provider-neutral format?
- Which self-hosted modes relocate only execution, and which also relocate orchestration state and the control plane?

## Privacy And Sensitivity Notes

Only public vendor documentation and public repository information were used. No private, proprietary, personal, or company-internal information is included.

## Ingest Rationale

The query establishes a reusable framework-selection rule that applies across managed agent platforms and is not captured cleanly by the existing skills-portability pages. It should enter the normal raw ingest workflow rather than changing durable wiki pages directly.
