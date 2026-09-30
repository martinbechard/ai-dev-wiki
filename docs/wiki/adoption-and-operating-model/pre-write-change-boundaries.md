---
type: "Adoption And Operating Model"
title: "Pre-Write Change Boundaries"
description: "Pre-write change boundaries shape agent work before implementation starts so review and governance are not left until the pull request."
tags: ["adoption-and-operating-model"]
---

# Pre-Write Change Boundaries

## Current Understanding

Pre-write change boundaries shape agent work before implementation starts so review and governance are not left until the pull request. The local practice is to define ticket scope, architectural constraints, protected paths, merge gates, and drift checks before an agent begins editing code.

The [September 29 topic news collector source](../../../raw/processed/2026-09-29/ai-dev-wiki-topic-news-collector-2026-09-30T003135Z.json) records a practitioner model where agent-started work is gated before code is written: tickets are checked against current architecture decisions, CI rules block merge paths, billing or pricing folders require human review, and agent-maintained solution documents are periodically checked against code and documentation drift. Broad product and company coverage stays upstream; locally, the durable rule is to reduce review overload by constraining agent change shape before implementation starts.

This page owns the pre-write boundary practice. [Adoption operating agreements](adoption-operating-agreements.md) owns the team-level agreement map, and [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md) owns enforcement evidence when boundaries become runtime or repository policy.

## Practice Boundaries

- Baseline tickets against current architecture decisions before assigning agent implementation.
- Mark protected paths that require human review, such as billing, pricing, credentials, deployment, or authorization-sensitive code.
- Encode stable merge restrictions in CI or repository rules instead of relying only on final reviewer memory.
- Require agents to explain which architecture decision, acceptance criterion, or protected-path rule permits the planned change.
- Periodically check agent-maintained solution documents against code and documentation so drift does not become hidden implementation context.
- Treat pre-write gates as review-load controls: they do not replace tests, code review, security review, or human acceptance.

## Authoritative Sources

- [September 29 topic news collector source](../../../raw/processed/2026-09-29/ai-dev-wiki-topic-news-collector-2026-09-30T003135Z.json)
- [adoption operating agreements](adoption-operating-agreements.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption and operating model](index.md)
- [adoption operating agreements](adoption-operating-agreements.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [AI code evidence packages](../governance-and-risk/ai-code-evidence-packages.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-09-29 with ticket-baseline, architecture-decision, protected-path, CI-merge-gate, human-review, and document-drift evidence from the September 29 topic news collector.
