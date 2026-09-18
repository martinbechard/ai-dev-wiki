---
type: "Governance And Risk"
title: "Agent Incident Reporting"
description: "Agent incident reporting records unexpected or concerning agent behavior as an engineering governance event."
tags: ["governance-and-risk"]
---

# Agent Incident Reporting

## Current Understanding

Agent incident reporting records unexpected or concerning agent behavior as an engineering governance event. The [September 17 topic news collector source](../../../raw/processed/2026-09-17/ai-dev-wiki-topic-news-collector-2026-09-17T003308Z.json) captures [OpenAI](../../../upstream-ai-wiki/companies/openai.md)'s model-misalignment reporting framework as a local template for coding-agent and automation anomalies. Broad OpenAI and model-safety background stays upstream-owned; locally, the durable practice is to preserve enough incident context for escalation, audit, mitigation, and later eval design.

The [September 17 leaf update watch source](../../../raw/processed/2026-09-17/ai-dev-wiki-leaf-update-watch-2026-09-17T210120-0400.json) and [September 18 topic news collector source](../../../raw/processed/2026-09-18/ai-dev-wiki-topic-news-collector-2026-09-18T003153Z.json) add authorization-boundary and anomaly-monitoring evidence. Incident records should capture unauthorized uploads, hidden notes, inter-agent communication, concealment or evasion signals, tool misuse, identity or privilege abuse, resource exhaustion, delayed blocking, and whether a control plane detected the behavior before harm.

An agent incident record should distinguish the observed behavior from speculation about the model or tool. Useful fields include:

- Severity, affected users or systems, and affected third parties.
- Discovery path, agent or model route when known, and tool or connector scope.
- Mitigation state, unresolved questions, and escalation or disclosure decision.
- Failure class such as generation, tool use, delegated authority, source handling, memory or state, or governance-control failure.
- Authorization boundary, public-output path, inter-agent communication, concealment or evasion evidence, and trace or anomaly-monitor verdict.

## Practice Boundaries

- Record observed behavior, severity, affected scope, discovery path, mitigation state, unresolved questions, and escalation or disclosure decision for material agent anomalies.
- Keep incident reports separate from ordinary failed-task notes when the behavior affects authority, safety, third parties, public output, data boundaries, or repeated workflow reliability.
- Preserve tool-call, prompt, source, approval, denial, and audit evidence needed to reconstruct what the agent could see and do.
- Preserve trace-level anomaly evidence, callback thresholds, delayed-blocking decisions, and affected connector identity when monitoring detects suspicious agent behavior.
- Treat unauthorized public uploads, unsanctioned inter-agent coordination, or hidden agent notes as incident triggers even when the final task output looks successful.
- Convert repeated or severe incident patterns into eval cases, policy checks, approval gates, or runbook changes.
- Route broad model-provider safety claims to the upstream AI wiki; keep this page focused on local coding-agent and automation incident practice.

## Authoritative Sources

- [September 17 topic news collector source](../../../raw/processed/2026-09-17/ai-dev-wiki-topic-news-collector-2026-09-17T003308Z.json)
- [September 17 leaf update watch source](../../../raw/processed/2026-09-17/ai-dev-wiki-leaf-update-watch-2026-09-17T210120-0400.json)
- [September 18 topic news collector source](../../../raw/processed/2026-09-18/ai-dev-wiki-topic-news-collector-2026-09-18T003153Z.json)
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
- Maintained on 2026-09-17 with authorization-boundary, unauthorized-upload, inter-agent coordination, concealment, trace-anomaly, tool-misuse, identity-abuse, and delayed-blocking incident fields.
