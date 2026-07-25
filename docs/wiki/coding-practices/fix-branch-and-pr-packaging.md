---
type: "Coding Practice"
title: "Fix Branch And PR Packaging"
description: "Fix assistants are easier to trust when reproduction, scope, patch, tests, and verification evidence are explicit."
tags: ["coding-practices"]
---

# Fix Branch And PR Packaging

## Current Understanding

Fix assistants are easier to trust when reproduction, scope, patch, tests, and verification evidence are explicit. The local practice is to prove the problem before editing, keep the change scoped to one concern, add or repair regression coverage, and package the result with enough evidence for review.

This page records the coding practice. Repository-specific branch naming, hosting workflows, and pull request automation are project-specific source-workflow concerns when they exist.

The [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json) adds a review-packaging warning from public coding-agent adoption signals: when agent-produced code reaches production with less separate manual review, the fix package itself must carry more explicit acceptance evidence. PR descriptions, branch notes, and closeout reports should state the review path, tests, residual risk, and human decision point instead of assuming a reviewer will rediscover them.

The [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) adds agent-authorship accountability. Fix packages should identify when a coding agent authored or materially shaped commits, attach the security or quality violations found against those commits, and state the human repair owner. Generated-code policy pressure is a packaging concern because maintainers may reject work when authorship, understanding, or repair responsibility is unclear.

The [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json) and [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json) add review-packaging evidence. CI repair agents should preserve the failed check, investigation path, patch scope, created repair branch or PR, and human review request; AI code review automation should leave source-backed comments and setup evidence rather than turning reviewer labor into unstructured cleanup.

## Practice Boundaries

- Reproduce the bug with a failing test, compile error, browser issue, log line, screenshot mismatch, or user scenario before editing.
- Scope the work to one concern and keep unrelated cleanup out of the change.
- Patch the smallest owning module unless the design requires a broader refactor.
- Add or repair regression coverage when behavior changed or drifted.
- Report build, test, lint, runtime, and review evidence with the fix.
- Package review notes around reproduction, scope, patch, verification, and remaining risk.
- Include the review path and human acceptance point when a generated or agent-assisted change is proposed for merge.
- Preserve agent-authorship, violation attribution, and human repair ownership in PR notes when agent-generated commits are part of the fix.
- Preserve failed-check evidence, investigation notes, generated repair branch or PR identity, and review-request state for agent-assisted CI fixes.
- Package AI-review findings with source locations, reproduction or setup evidence, and suggested checks so the human reviewer is not left to rediscover the whole issue.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Generated code refactoring](generated-code-refactoring.md)
- [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json)
- [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [ai-assisted TDD](ai-assisted-tdd.md)
- [intelligent code review](intelligent-code-review.md)
- [source-workflows](../source-workflows/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on fix assistants, branch scope, regression coverage, and review-ready evidence.
- Maintained on 2026-06-29 with review-path packaging for agent-assisted production changes.
- Maintained on 2026-07-07 with agent-authorship, violation-attribution, and human repair ownership packaging.
- Maintained on 2026-07-24 with failed-check repair handoff and source-backed AI-review packaging guidance.
