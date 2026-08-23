---
type: "Topic"
title: "Shared Channel Agent Sessions"
description: "Shared channel agent sessions let teams start, steer, and review coding-agent work from collaborative chat while preserving repository controls."
tags: ["agent-workflows"]
---

# Shared Channel Agent Sessions

## Current Understanding

Shared channel agent sessions let teams start, steer, and review coding-agent work from collaborative chat while preserving repository controls. The [August 22 topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json) records qualifying GitHub changelog signals for Copilot sessions in Slack and Microsoft Teams:

- Team members can start or add context to cloud coding-agent work from the conversation.
- Plans, diffs, previews, and pull requests remain inspectable from the shared channel.
- Repository permissions, sandbox policy, billing, and extra pull-request approval stay in the control path.

This page owns the local workflow pattern. Broad GitHub Copilot, Slack, and Microsoft Teams product coverage belongs to the upstream AI wiki; locally, the durable rule is that shared chat is a coordination and evidence surface, not an authority source by itself.

## Practice Boundaries

- Treat chat messages as steering evidence, not standalone authorization for repository writes, sandbox use, paid compute, or merges.
- Preserve channel-visible plans, diffs, preview links, generated pull requests, approval waits, and stop or redirect decisions as part of the task handoff.
- Require repository permission checks before a participant can trigger or steer code changes from a team channel.
- Attribute agent-authored changes to the integration identity and require any repository-specific extra approval before merge.
- Route cloud-sandbox enablement, AI-credit use, separate sandbox billing, budget owner, and cost-center evidence through the same controls used for other delegated coding work.
- Keep private context, secrets, credentials, and restricted repository data out of shared channels unless the repository and collaboration policy explicitly allow that exposure.
- Link shared-channel sessions to [delegated coding handoffs](delegated-coding-handoffs.md) and [runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md) so later reviewers can reconstruct who asked for what, what changed, and which gates passed.

## Authoritative Sources

- [August 22 topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json)
- [GitHub Copilot shared Slack sessions changelog](https://github.blog/changelog/2026-08-21-the-new-github-copilot-experience-in-slack/)
- [GitHub Copilot shared Teams sessions changelog](https://github.blog/changelog/2026-08-21-shared-agentic-work-with-github-copilot-in-microsoft-teams/)
- [delegated coding handoffs](delegated-coding-handoffs.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [delegated coding handoffs](delegated-coding-handoffs.md)
- [event-triggered agent workflows](event-triggered-agent-workflows.md)
- [user-visible progress and runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md)
- [agent identity and delegated authority](../governance-and-risk/agent-identity-and-delegated-authority.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-08-22 from qualifying public-preview evidence for shared Slack and Microsoft Teams coding-agent sessions, keeping product-specific details upstream-owned.
