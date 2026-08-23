---
type: "Governance And Risk"
title: "Execution Edge Authorization"
description: "Execution edge authorization treats each model-to-tool, agent-to-agent, user-to-agent, and agent-to-system connection as an enforceable authorization boundary."
tags: ["governance-and-risk"]
---

# Execution Edge Authorization

## Current Understanding

Execution edge authorization treats each model-to-tool, agent-to-agent, user-to-agent, and agent-to-system connection as an enforceable authorization boundary. The [August 22 topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json) and [August 22 leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json) add the local rule that reachability is not authorization: an agent seeing a tool, channel, connected app, database surface, sandbox, or payment-like action does not mean it may use that edge.

This page owns the edge-level authorization lens. [Agent governance infrastructure](agent-governance-infrastructure.md) owns the broader control plane, [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md) owns tool-call validation, [governed database agent access](../retrieval-and-tools/governed-database-agent-access.md) owns database boundaries, and [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md) owns hostile source carriers.

## Practice Boundaries

- Record the acting human, agent identity, integration identity, target system, action class, data class, credential scope, budget scope, and approval state for each high-impact edge.
- Treat team chat, database tools, connected apps, cloud sandboxes, memory stores, agent-to-agent calls, and billable services as separate edges with separate authority.
- Preserve execution evidence from harness events, gateway policy decisions, IAM records, downstream logs, audit trails, and trust receipts when the edge can change code, data, spend, memory, or external state.
- Do not treat hidden tool schemas, reduced tool discovery, or a convenient channel command as authorization.
- Require mandate evidence, spend caps, prompt-injection screening, and delegated-intent checks before an agent can spend money or trigger paid services.
- Require pause or escalation criteria when edge evidence shows sandbox escape, unexpected network use, hidden source instructions, connected-app exfiltration risk, or production-data access outside the approved task.

## Authoritative Sources

- [August 22 topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json)
- [August 22 leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance controls for agents](governance-controls-for-agents.md)
- [agent identity and delegated authority](agent-identity-and-delegated-authority.md)
- [governed database agent access](../retrieval-and-tools/governed-database-agent-access.md)
- [user-visible progress and runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-08-22 from raw-source evidence about graph-edge governance, paid agent actions, connected apps, database agents, sandbox pauses, and trust receipts.
