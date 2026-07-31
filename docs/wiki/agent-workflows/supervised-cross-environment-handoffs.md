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

This page complements [delegated coding handoffs](delegated-coding-handoffs.md) and [subagent coordination](subagent-coordination.md). Those pages own the general handoff and subagent contract; this page owns cross-environment supervision, state transfer, and evidence normalization.

## Practice Boundaries

- Name the orchestration owner before multiple environment-specific agents act on one task.
- Record which surface each agent used, including browser, desktop, terminal, repository, cloud, or hosted workflow context.
- Preserve screenshots, logs, changed files, command output, summaries, or structured state that can be reviewed from outside the original surface.
- Require human supervision or approval when a handoff crosses from observation into file writes, shell execution, credentials, external systems, or public output.
- Make the final summary identify environment boundaries, unresolved state, and verification evidence rather than only describing task progress.

## Authoritative Sources

- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
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
