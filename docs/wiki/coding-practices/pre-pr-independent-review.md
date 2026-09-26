---
type: "Coding Practice"
title: "Pre-PR Independent Review"
description: "Pre-PR independent review asks a separate reviewer to inspect local agent changes before a pull request is opened."
tags: ["coding-practices"]
---

# Pre-PR Independent Review

## Current Understanding

Pre-PR independent review asks a separate reviewer to inspect local committed or uncommitted agent changes before a pull request is opened. It catches reviewable issues while the authoring agent can still make safe local fixes, and it keeps product, architecture, migration, security, and residual-risk decisions with humans.

The [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json) records a shift-left review workflow. Broad product details stay upstream; locally, the durable practice is reviewer independence before PR creation:

1. Load codebase context and team rules.
2. Implement the change.
3. Run tests.
4. Ask an independent reviewer to inspect the local diff or commit.
5. Fix safe findings.
6. Open a pull request only after the independent pass.

This page owns the pre-PR workflow. [Intelligent code review](intelligent-code-review.md) owns the broader review contract for source-backed AI review across implementation surfaces.

The September 15-16 raw sources add two review-pressure signals. The [leaf update watch source](../../../raw/processed/2026-09-15/ai-dev-wiki-leaf-update-watch-2026-09-15T210309-0400.json) records AI reviewer rereview, auto-resolution, shell-tool validation, ensemble review, and independent assurance caveats. The [topic news collector source](../../../raw/processed/2026-09-16/ai-dev-wiki-topic-news-collector-2026-09-16T003033Z.json) records PR triage for agent-created work. Locally, pre-PR review should prove which findings were auto-resolved, which evidence supports resolution, and which changes deserve scarce human attention before opening or escalating the pull request.

The September 22-23 raw sources add review-state and queue-triage evidence. The [leaf update watch source](../../../raw/processed/2026-09-22/ai-dev-wiki-leaf-update-watch-2026-09-22T210151-0400.json) records AI-review overview state, finding groups, resolution reasons, previously missed findings, and generated batch commit messages. The [topic news collector source](../../../raw/processed/2026-09-23/ai-dev-wiki-topic-news-collector-2026-09-23T003135Z.json) records pull-request queue ergonomics such as content-assisted filtering, status-check counts, stack indicators, unread-update indicators, and review-status filters. Locally, pre-PR review should preserve both the finding lifecycle and the queue signal that determines whether an agent-authored change is ready for scarce reviewer attention.

The [September 24 topic news collector source](../../../raw/processed/2026-09-24/ai-dev-wiki-topic-news-collector-2026-09-24T003335Z.json) adds configurable review-default and huge-PR evidence. Local review operations should record who owns default AI review effort, when automatic review triggers, why a team overrides enterprise defaults, and whether the diff surface has performance, probe, and unattended-reproduction evidence before the PR is handed to scarce human review.

The [September 25 topic news collector source](../../../raw/processed/2026-09-25/ai-dev-wiki-topic-news-collector-2026-09-26T003140Z.json) adds review-evidence bottleneck evidence. Pre-PR review should preserve the explanation, semantic diff, system diagram, task state, validation, and independent-review evidence that proves an agent-authored change is safe enough for human review, rather than relying on a raw diff alone. Named review products in that source remain source-specific examples unless verified separately.

## Practice Boundaries

- Review the exact local diff, commit, or staged change that will become the pull request.
- Use an independent reviewer rather than asking the authoring agent to approve its own work.
- Split findings into safe agent-fix items and human-decision items.
- Keep product, architecture, migration, security, and residual-risk tradeoffs with human reviewers.
- Preserve the inspected revision and reviewer identity in the eventual pull-request evidence package.
- Preserve auto-resolution reasons, addressed-commit evidence, and validation output when AI rereview closes comments before a human sees the pull request.
- Triage agent-created changes by priority, risk, ownership, dependency, blocker state, effort, and review depth before consuming human reviewer time.
- Preserve review-state groups, previously missed issue evidence, resolution reasons, generated commit-message review, stack position, status-check count, unread-update state, and review-status filters when they affect whether a PR should be opened, updated, or held.
- Record default AI-review effort owner, automatic-review trigger, enterprise-default override reason, huge-diff performance evidence, runtime probes, and unattended repro loops when PR scale affects reviewability.
- Preserve explanation, semantic-diff, architecture or system-state, task-state, validation, and independent-review evidence before moving high-volume agent changes into human PR review.

## Authoritative Sources

- [September 15 leaf update watch source](../../../raw/processed/2026-09-15/ai-dev-wiki-leaf-update-watch-2026-09-15T210309-0400.json)
- [September 22 leaf update watch source](../../../raw/processed/2026-09-22/ai-dev-wiki-leaf-update-watch-2026-09-22T210151-0400.json)
- [September 23 topic news collector source](../../../raw/processed/2026-09-23/ai-dev-wiki-topic-news-collector-2026-09-23T003135Z.json)
- [September 24 topic news collector source](../../../raw/processed/2026-09-24/ai-dev-wiki-topic-news-collector-2026-09-24T003335Z.json)
- [September 25 topic news collector source](../../../raw/processed/2026-09-25/ai-dev-wiki-topic-news-collector-2026-09-26T003140Z.json)
- [September 16 topic news collector source](../../../raw/processed/2026-09-16/ai-dev-wiki-topic-news-collector-2026-09-16T003033Z.json)
- [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json)
- [intelligent code review](intelligent-code-review.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [coding practices](index.md)
- [intelligent code review](intelligent-code-review.md)
- [layered AI code review roles](layered-ai-code-review-roles.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-09-15 with AI rereview, auto-resolution, shell-validation, ensemble-review, independent-assurance, and PR-triage evidence.
- Maintained on 2026-09-23 with review-state, resolution-reason, generated-commit-message, stack, status-check, unread-update, and review-filter evidence.
- Maintained on 2026-09-24 with review-default ownership, automatic-review trigger, enterprise override, huge-diff performance, runtime-probe, and unattended-repro evidence.
- Maintained on 2026-09-25 with review-evidence bottleneck, semantic-diff, task-state, validation, and independent-review evidence.
- Created on 2026-09-14 from shift-left review evidence in the September 15 topic news collector.
