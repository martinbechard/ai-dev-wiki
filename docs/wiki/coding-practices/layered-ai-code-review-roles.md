---
type: "Coding Practice"
title: "Layered AI Code Review Roles"
description: "Layered AI code review separates implementation, architecture, and security review expectations for AI-authored changes."
tags: ["coding-practices"]
---

# Layered AI Code Review Roles

## Current Understanding

Layered AI code review separates implementation, architecture, and security review expectations for AI-authored changes. The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) records a vendor brief that frames AI review through developer, architect, and security-engineer roles. Broad product coverage stays upstream; locally, the reusable pattern is that one fluent reviewer comment stream is weaker than explicit role-scoped findings.

Role responsibilities:

- Developer-style review checks changed code against local conventions, tests, interfaces, and maintainability.
- Architect-style review checks design intent, invariants, boundaries, cross-file effects, and whether generated implementation still matches the system shape.
- Security-style review checks vulnerability classes, dependency exposure, unsafe tool or data flow, and whether scanner output misses design-level risk.

The [August 28 topic news collector source](../../../raw/processed/2026-08-28/ai-dev-wiki-topic-news-collector-2026-08-28T003339Z.json) adds security-review augmentation evidence. AI can triage, explain, and route likely security findings, but deterministic rules and human security judgment remain separate gates for high-risk changes.

## Practice Boundaries

- Declare which review roles are active before an AI reviewer comments.
- Keep implementation, architecture, and security findings separate when they imply different owners or acceptance gates.
- Treat SAST and SCA results as evidence for the security role, not as a substitute for architecture or generated-code intent review.
- Preserve human review for design tradeoffs, security context, and final acceptance.
- Evaluate layered review by source-backed findings, missed risks, repair evidence, and reviewer attention cost rather than comment volume.
- Keep AI security-review triage separate from deterministic rules and human security acceptance so generated comments do not become final assurance.

## Authoritative Sources

- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [intelligent code review](intelligent-code-review.md)
- [code review evals and rubrics](../verification-and-evals/code-review-evals-and-rubrics.md)
- [lifecycle AI review gates](../governance-and-risk/lifecycle-ai-review-gates.md)
- [August 28 topic news collector source](../../../raw/processed/2026-08-28/ai-dev-wiki-topic-news-collector-2026-08-28T003339Z.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [intelligent code review](intelligent-code-review.md)
- [code review evals and rubrics](../verification-and-evals/code-review-evals-and-rubrics.md)
- [lifecycle AI review gates](../governance-and-risk/lifecycle-ai-review-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-27 from July 27 raw-source evidence about developer, architect, and security-engineer AI review roles.
- Maintained on 2026-08-27 with AI security-review augmentation boundaries for triage, deterministic rules, and human security judgment.
