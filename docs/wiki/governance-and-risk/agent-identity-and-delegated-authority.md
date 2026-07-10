---
type: "Governance And Risk"
title: "Agent Identity And Delegated Authority"
description: "Agent identity and delegated authority define who or what acted, on whose behalf, with which permission boundary, and under which policy."
tags: ["governance-and-risk"]
---

# Agent Identity And Delegated Authority

## Current Understanding

Agent identity and delegated authority define who or what acted, on whose behalf, with which permission boundary, and under which policy. The local governance rule is to distinguish the human requester, the agent instance, the connector or service account, the tool server, and the external system touched by the action.

The [topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) records public signals about shared-channel agents, credential revocation, OAuth token limitations, and agent identity ambiguity. Product and standard details remain upstream-owned; this page owns the local operating requirement that agent actions must be attributable and revocable.

Delegated authority also matters in shared work channels. A channel agent can accumulate context, receive requests from multiple people, and act through connected tools. The local boundary is that channel memory, tool access, and approvals should be explicit enough that a future reviewer can tell which human goal authorized the action.

The [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) adds a non-human identity control set: each agent should have an accountable owner, least-privilege access, credential management, recurring access reviews, activity monitoring, and audit evidence. The local practice implication is that agent identity cannot stop at a display name in a chat surface; it needs a revocable authority path and evidence trail.

The [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json) adds a guardian-agent and UI-first operating lens. Agent identity should include inherited-permission analysis, behavioral baselines, stale-credential checks, and runtime policy enforcement. When an agent acts through existing user workflows, the local goal is to preserve the same approval paths and audit artifacts that would apply to the human action.

The [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json) adds an identity-bound authorization lens. The model and local agent host should be treated as untrusted emitters for consequential tool calls; an off-host authorization path should bind the human or system principal, policy, arguments, rate limits, credential broker, and audit chain before side effects occur.

The [GitLost clipping](../../../raw/processed/GitLost is a dream come true for anyone who likes to jailbreak LLMs.md) adds a delegated-authority failure shape for repository automations. Assignment to an issue or an issue-triggered event should not imply authority to traverse private repositories or publish their contents. Delegation should identify the requester or trigger, the repository scope, the response channel, and the policy that allows or blocks any public output.

## Practice Boundaries

- Record the human requester, agent instance, connector identity, delegated scope, approval path, and target system for consequential actions.
- Prefer scoped service accounts or controlled connectors when shared agents would otherwise use unclear personal authority.
- Keep channel access, memory scope, and tool permissions visible for team-facing agents.
- Revoke SSO grants, personal access tokens, SSH keys, OAuth tokens, and connector credentials quickly when an agent or developer environment is suspected compromised.
- Log credential revocation and follow-up review when a compromised credential could have been used by an agent workflow.
- Treat identity gaps as governance findings, not only as implementation details.
- Assign accountable owners to agent identities and review their access periodically like other non-human identities.
- Monitor agent activity against expected scope so delegated authority drift becomes visible before incident review.
- Check inherited permissions and stale credentials before letting an agent act through a connector, tool server, or user-interface workflow.
- Preserve existing approval and audit artifacts when agent execution emulates a human workflow.
- Bind consequential tool calls to a verified principal and policy decision outside the model context.
- Record message-level or request-level authorization evidence when delegated actions can affect code, data, credentials, costs, or external systems.
- Treat event-triggered automation as a distinct delegating principal; do not inherit broad organization access merely because the trigger came from an issue assignment.
- Bind public comments, issue replies, and pull-request messages to an output policy when the agent has access to private or cross-repository context.

## Authoritative Sources

- [Topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json)
- [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json)
- [GitLost clipping](../../../raw/processed/GitLost is a dream come true for anyone who likes to jailbreak LLMs.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance-and-risk](index.md)
- [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [agent ownership rosters](../adoption-and-operating-model/agent-ownership-rosters.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-24 to separate agent instance identity, delegated authority, shared-channel agents, and credential revocation from broader governance infrastructure.
- Maintained on 2026-06-25 with non-human identity controls for owner assignment, least privilege, recurring access review, monitoring, and audit evidence.
- Maintained on 2026-06-29 with inherited-permission analysis, stale-credential checks, runtime enforcement, and UI-first audit preservation.
- Maintained on 2026-07-08 with identity-bound off-host authorization, argument constraints, credential brokering, and audit-chain evidence.
- Maintained on 2026-07-10 with event-triggered delegation boundaries for issue agents, repository scope, and public output authority.
