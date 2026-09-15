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

## Practice Boundaries

- Review the exact local diff, commit, or staged change that will become the pull request.
- Use an independent reviewer rather than asking the authoring agent to approve its own work.
- Split findings into safe agent-fix items and human-decision items.
- Keep product, architecture, migration, security, and residual-risk tradeoffs with human reviewers.
- Preserve the inspected revision and reviewer identity in the eventual pull-request evidence package.

## Authoritative Sources

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

- Created on 2026-09-14 from shift-left review evidence in the September 15 topic news collector.
