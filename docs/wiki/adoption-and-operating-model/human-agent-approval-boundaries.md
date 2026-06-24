# Human Agent Approval Boundaries

## Current Understanding

Human-agent approval boundaries define which work an agent can perform, which work requires review, and which decisions remain human-owned. The local boundary is that humans own goals, tradeoffs, accountability, and final acceptance, while agents can inspect, draft, patch, verify, and report within the approved workflow.

Approval boundaries are both operating practice and governance control. The operating agreement names when a human must decide; [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md) owns the infrastructure controls that enforce permissions, least privilege, audit, and policy.

Consequential actions need explicit approval or policy gates. This includes actions affecting files, dependencies, credentials, external systems, production-like data, or externally visible output.

The [workspace agents source](../../../raw/processed/OpenAI Just Gave Every Team A Free Employee. Here's The Catch..md) and [agent ownership source](../../../raw/processed/You Can't Run AI Agents Without This.md) sharpen the local boundary for recurring team agents: the strongest first candidates are known-path workflows with a clear output, a human reviewer, and a measurable time-saving goal. Agents should not be evaluated first on novel, judgment-heavy, open-ended strategy work where failures cannot be attributed to workflow, context, connectors, rubric, or model behavior.

The [leaf update watch source](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json) adds a public security-control lens: autonomy should increase through verified behavior, sandboxing, monitoring, containment, and incremental permissions rather than one-time trust. Approval boundaries should distinguish low-risk drafting or inspection from actions that expand tool access, touch sensitive systems, or create external effects.

## Practice Boundaries

- Define which tasks can be delegated, which require review, and which require human execution.
- Require an explicit done signal with evidence, not only a fluent summary.
- Keep approval points visible inside the workflow so the human can stop, redirect, or accept the work.
- Treat approval requirements as stronger when the workflow touches security, privacy, costs, credentials, dependencies, or irreversible external state.
- Start recurring team agents on known-path work with a visible reviewer and a clear output standard.
- Reject or redesign agents whose workflow is too ambiguous for the owner to describe in one paragraph.
- Escalate permissions progressively from observed behavior, verification evidence, and sandbox results.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [Workspace agents source](../../../raw/processed/OpenAI Just Gave Every Team A Free Employee. Here's The Catch..md)
- [Agent ownership source](../../../raw/processed/You Can't Run AI Agents Without This.md)
- [Leaf update watch source](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption operating agreements](adoption-operating-agreements.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [delegated coding handoffs](../agent-workflows/delegated-coding-handoffs.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [agent ownership rosters](agent-ownership-rosters.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed approval, delegation, and human-accountability guidance.
- Maintained on 2026-06-23 with public AI control guidance on progressive permissions, sandboxing, monitoring, and containment.
