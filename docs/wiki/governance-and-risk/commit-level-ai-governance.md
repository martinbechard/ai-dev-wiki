---
type: "Governance And Risk"
title: "Commit-Level AI Governance"
description: "Commit-level AI governance attaches approved-model policy, AI-use traces, and attribution evidence to source-control decisions."
tags: ["governance-and-risk"]
---

# Commit-Level AI Governance

## Current Understanding

Commit-level AI governance attaches approved-model policy, AI-use traces, and attribution evidence to source-control decisions. The control point is the commit or changeset, not only a later vulnerability scan or dashboard.

The [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json) records Secure Code Warrior-style governance signals: visibility into AI-assisted development, approved-model policies, commit-level AI usage tracing, repository and contributor risk signals, and audit-ready records of who or what generated code. Product details stay upstream; locally, the durable pattern is source-control-attached governance evidence.

The September 15 [leaf update watch source](../../../raw/processed/2026-09-15/ai-dev-wiki-leaf-update-watch-2026-09-15T210309-0400.json) adds centrally managed agent-operation permissions and custom-property suggestions as source-control governance signals. The September 16 [topic news collector source](../../../raw/processed/2026-09-16/ai-dev-wiki-topic-news-collector-2026-09-16T003033Z.json) adds enterprise-enforced security configurations and repository metadata suggestions. Locally, commit-level governance should record which enterprise policy, repository taxonomy, security baseline, and agent-operation rule applied when a change was proposed or accepted.

This page owns commit-level governance. [Governance controls for agents](governance-controls-for-agents.md) owns the broader local control model across agent tools, data, identity, and approvals.

## Practice Boundaries

- Preserve approved-model policy evidence when the model route affects code acceptance.
- Attach AI-use traces to the commit, pull request, or changeset under review.
- Record who or what generated, modified, reviewed, and accepted the code when that attribution affects accountability.
- Use repository and contributor risk signals as triage inputs, not as automatic acceptance or rejection.
- Keep audit-ready records close enough to source control that later incident review can reconstruct the accepted change.
- Record central shell, file, network, and security-configuration policies when they affect what an agent could inspect, edit, or execute for a commit.
- Keep repository custom-property and ruleset evidence close to the commit when metadata decides required scans, approvals, or security baselines.

## Authoritative Sources

- [September 15 leaf update watch source](../../../raw/processed/2026-09-15/ai-dev-wiki-leaf-update-watch-2026-09-15T210309-0400.json)
- [September 16 topic news collector source](../../../raw/processed/2026-09-16/ai-dev-wiki-topic-news-collector-2026-09-16T003033Z.json)
- [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json)
- [governance controls for agents](governance-controls-for-agents.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance and risk](index.md)
- [AI code evidence packages](ai-code-evidence-packages.md)
- [intelligent code review](../coding-practices/intelligent-code-review.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-09-15 with central agent-operation policy, repository taxonomy, and enforced security-baseline governance evidence.
- Created on 2026-09-14 from commit-level AI software governance evidence in the September 15 topic news collector.
