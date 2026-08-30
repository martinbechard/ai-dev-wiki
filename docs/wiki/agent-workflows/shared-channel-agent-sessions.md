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

The [August 23 leaf update watch source](../../../raw/processed/2026-08-23/ai-dev-wiki-leaf-update-watch-2026-08-23T210505-0400.json) adds a shared-workspace refinement. Channel-native coding agents can expose live previews, feedback, approvals, and task tabs beside ordinary chat, but the local control remains unchanged: channel visibility helps coordination and audit, while write access, repository permissions, approval authority, admin policy, and merge gates still need separate evidence.

The [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) adds shared-agent and IDE agent evidence. Shared sessions and IDE-native custom agents should preserve trigger identity, catalog source, usage visibility, thinking effort, context-window pressure, model capability, and pre-PR review evidence before chat-visible or IDE-visible work is treated as review-ready.

The [August 29 leaf update watch source](../../../raw/processed/2026-08-29/ai-dev-wiki-leaf-update-watch-2026-08-29T210148-0400.json) and [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-30T003150Z.json) add collaboration-load and shared-session evidence:

- Shared Slack or Teams sessions should make work state recoverable for the team.
- Cross-application continuation and interrupted-session restore should preserve steering context.
- Review queue pressure and task switching remain visible operating costs rather than hidden side effects of solo agent delegation.

## Practice Boundaries

- Treat chat messages as steering evidence, not standalone authorization for repository writes, sandbox use, paid compute, or merges.
- Preserve channel-visible plans, diffs, preview links, generated pull requests, approval waits, and stop or redirect decisions as part of the task handoff.
- Require repository permission checks before a participant can trigger or steer code changes from a team channel.
- Attribute agent-authored changes to the integration identity and require any repository-specific extra approval before merge.
- Route cloud-sandbox enablement, AI-credit use, separate sandbox billing, budget owner, and cost-center evidence through the same controls used for other delegated coding work.
- Keep private context, secrets, credentials, and restricted repository data out of shared channels unless the repository and collaboration policy explicitly allow that exposure.
- Link shared-channel sessions to [delegated coding handoffs](delegated-coding-handoffs.md) and [runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md) so later reviewers can reconstruct who asked for what, what changed, and which gates passed.
- Treat channel-visible feedback, previews, and approval widgets as evidence inputs; require repository and admin-control records before accepting them as authorization for code changes.

## Authoritative Sources

- [August 29 leaf update watch source](../../../raw/processed/2026-08-29/ai-dev-wiki-leaf-update-watch-2026-08-29T210148-0400.json)
- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-30T003150Z.json)
- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [August 22 topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json)
- [August 23 leaf update watch source](../../../raw/processed/2026-08-23/ai-dev-wiki-leaf-update-watch-2026-08-23T210505-0400.json)
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

- Maintained on 2026-08-29 with shared Slack and Teams session, cross-app continuation, interrupted-session restore, review-load, and task-switching evidence.
- Maintained on 2026-08-29 with shared-agent trigger, custom-agent catalog, usage visibility, effort, context-window, model-capability, and pre-PR review evidence.
- Created on 2026-08-22 from qualifying public-preview evidence for shared Slack and Microsoft Teams coding-agent sessions, keeping product-specific details upstream-owned.
- Maintained on 2026-08-23 with shared-workspace feedback, preview, approval-widget, write-access, and admin-control evidence.
