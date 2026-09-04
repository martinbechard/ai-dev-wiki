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

The August 28 and 29 raw sources add review-load and production-risk evidence. The [leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json) records public guidance that AI-generated code reaching production still needs tool-agnostic security controls, workflow integration, and shared accountability across security, engineering, and leadership. The [topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) adds developer-experience evidence that agent-heavy coding can increase review load and reduce collaborative learning when review work is not explicitly staffed.

The September 3 [leaf update watch](../source-workflows/leaf-update-watch.md) source adds security-repair and governance-role evidence:

- The [source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json) separates vulnerability discovery, triage, critic/review, sandboxed reproduction, architecture or threat-model review, and human-curated acceptance.
- It also separates pull-request reviewer accuracy from repository-fleet trend, policy, and audit controls.

Locally, layered review should keep those roles distinct when generated fixes can reach production.

## Practice Boundaries

- Declare which review roles are active before an AI reviewer comments.
- Keep implementation, architecture, and security findings separate when they imply different owners or acceptance gates.
- Treat SAST and SCA results as evidence for the security role, not as a substitute for architecture or generated-code intent review.
- Preserve human review for design tradeoffs, security context, and final acceptance.
- Evaluate layered review by source-backed findings, missed risks, repair evidence, and reviewer attention cost rather than comment volume.
- Keep AI security-review triage separate from deterministic rules and human security acceptance so generated comments do not become final assurance.
- Size developer, architect, security, and human learning roles to review load; do not let one fluent agent review stream hide ownership for production risk or team skill health.
- Keep discovery, triage, critic/review, sandboxed reproduction, architecture/threat-model review, and fleet governance separate when security repair work uses agents.
- Do not treat repository-fleet policy trends or audit coverage as proof that a specific pull request was reviewed deeply enough.

## Authoritative Sources

- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [intelligent code review](intelligent-code-review.md)
- [code review evals and rubrics](../verification-and-evals/code-review-evals-and-rubrics.md)
- [lifecycle AI review gates](../governance-and-risk/lifecycle-ai-review-gates.md)
- [August 28 topic news collector source](../../../raw/processed/2026-08-28/ai-dev-wiki-topic-news-collector-2026-08-28T003339Z.json)
- [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json)
- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [September 3 leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json)

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
- Maintained on 2026-08-29 with production AI-generated-code accountability and review-load evidence for role-scoped review.
- Maintained on 2026-09-03 with vulnerability discovery, triage, critic-review, sandboxed reproduction, architecture/threat-model evidence, and fleet-governance role separation.
