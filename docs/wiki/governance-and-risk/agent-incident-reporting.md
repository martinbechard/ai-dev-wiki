---
type: "Governance And Risk"
title: "Agent Incident Reporting"
description: "Agent incident reporting records unexpected or concerning agent behavior as an engineering governance event."
tags: ["governance-and-risk"]
---

# Agent Incident Reporting

## Current Understanding

Agent incident reporting records unexpected or concerning agent behavior as an engineering governance event. The [September 17 topic news collector source](../../../raw/processed/2026-09-17/ai-dev-wiki-topic-news-collector-2026-09-17T003308Z.json) captures [OpenAI](../../../upstream-ai-wiki/companies/openai.md)'s model-misalignment reporting framework as a local template for coding-agent and automation anomalies. Broad OpenAI and model-safety background stays upstream-owned; locally, the durable practice is to preserve enough incident context for escalation, audit, mitigation, and later eval design.

An agent incident record should distinguish the observed behavior from speculation about the model or tool. Useful fields include:

- Severity, affected users or systems, and affected third parties.
- Discovery path, agent or model route when known, and tool or connector scope.
- Mitigation state, unresolved questions, and escalation or disclosure decision.
- Failure class such as generation, tool use, delegated authority, source handling, memory or state, or governance-control failure.

## Practice Boundaries

- Record observed behavior, severity, affected scope, discovery path, mitigation state, unresolved questions, and escalation or disclosure decision for material agent anomalies.
- Keep incident reports separate from ordinary failed-task notes when the behavior affects authority, safety, third parties, public output, data boundaries, or repeated workflow reliability.
- Preserve tool-call, prompt, source, approval, denial, and audit evidence needed to reconstruct what the agent could see and do.
- Convert repeated or severe incident patterns into eval cases, policy checks, approval gates, or runbook changes.
- Route broad model-provider safety claims to the upstream AI wiki; keep this page focused on local coding-agent and automation incident practice.

## Authoritative Sources

- [September 17 topic news collector source](../../../raw/processed/2026-09-17/ai-dev-wiki-topic-news-collector-2026-09-17T003308Z.json)
- [governance controls for agents](governance-controls-for-agents.md)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance controls for agents](governance-controls-for-agents.md)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [agent eval failure diagnosis](../verification-and-evals/agent-eval-failure-diagnosis.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-09-16 from raw-source evidence about model-misalignment reporting adapted to local coding-agent anomaly reporting; next check should verify actual incident templates capture owner, reproducer, authority, and containment fields.
