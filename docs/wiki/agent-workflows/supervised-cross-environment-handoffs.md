---
type: "Topic"
title: "Supervised Cross-Environment Handoffs"
description: "Supervised cross-environment handoffs coordinate agents that work across browser, desktop, terminal, repository, or cloud surfaces."
tags: ["agent-workflows"]
---

# Supervised Cross-Environment Handoffs

## Current Understanding

Supervised cross-environment handoffs coordinate agents that work across browser, desktop, terminal, repository, or cloud surfaces. The local rule is that each surface can change what evidence is available, what credentials are exposed, and how a human can intervene.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds a supervised UI automation signal: browser, desktop, planning, automation, and summarization roles need an orchestration owner and shared summary artifact when work crosses UI environments. Broad platform and product identity stays upstream-owned; locally, the durable practice is the handoff contract.

The [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json) adds browser-use and conversation-to-knowledge handoff signals. When an agent crosses from browser action or shared channel context into repository, workflow, or external-system action, the handoff should name the visible context used, private context excluded, browser or channel evidence captured, and the human decision required before the next environment changes state.

The [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json) adds model-to-model continuation evidence from the Handoff Tax paper. Broad benchmark and model background stays upstream-owned; locally, the handoff contract should preserve repository state separately from model trajectory, record which trajectory summary or scratchpad is handed over, and choose how much prior reasoning to pass based on handoff direction, cost, and quality risk.

This page complements [delegated coding handoffs](delegated-coding-handoffs.md) and [subagent coordination](subagent-coordination.md). Those pages own the general handoff and subagent contract; this page owns cross-environment supervision, state transfer, and evidence normalization.

## Practice Boundaries

- Name the orchestration owner before multiple environment-specific agents act on one task.
- Record which surface each agent used, including browser, desktop, terminal, repository, cloud, or hosted workflow context.
- Preserve screenshots, logs, changed files, command output, summaries, or structured state that can be reviewed from outside the original surface.
- Require human supervision or approval when a handoff crosses from observation into file writes, shell execution, credentials, external systems, or public output.
- Make the final summary identify environment boundaries, unresolved state, and verification evidence rather than only describing task progress.
- Record visible channel context, excluded private context, browser-structure evidence, generated draft artifacts, and the human review or redirect point when handoffs cross from conversation or browser work into executable action.
- Preserve repository state, changed files, verification evidence, and unresolved decisions separately from model trajectory when handing work between agents or models.
- Record whether the receiving agent should inherit detailed reasoning, a compact summary, or only task state when continuation direction creates cost or quality risk.

## Authoritative Sources

- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json)
- [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json)
- [delegated coding handoffs](delegated-coding-handoffs.md)
- [subagent coordination](subagent-coordination.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [delegated coding handoffs](delegated-coding-handoffs.md)
- [subagent coordination](subagent-coordination.md)
- [persistent agent workspaces](persistent-agent-workspaces.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-30 from public evidence about supervised browser, desktop, planning, automation, and summary handoffs.
- Maintained on 2026-08-20 with browser-use, shared-channel context, private-context exclusion, and human redirect evidence for cross-environment handoffs.
- Maintained on 2026-08-26 with model-to-model continuation evidence, repository-state preservation, trajectory-summary selection, and direction-sensitive handoff cost or quality risk.
