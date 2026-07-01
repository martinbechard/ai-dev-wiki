---
type: "Verification And Eval"
title: "Product Judgment Quality Gates"
description: "Product judgment gates check whether the right thing is being built and whether the delivered experience works for the intended user."
tags: ["verification-and-evals"]
---

# Product Judgment Quality Gates

## Current Understanding

Product judgment gates check whether the right thing is being built and whether the delivered experience works for the intended user. The [Studious source](../../../raw/processed/jacquardlabsstudious Studious — a product-judgment workflow for Claude Code quality gates, periodic health reviews, and pre-merge audits that examine each piece of work..md) frames these gates as lightweight review rhythms around AI-assisted building: should-build review, design review, implementation audit, acceptance review, periodic project health review, and context-document maintenance.

The local practice is to pair implementation workflow with judgment workflow. Coding agents can make building cheaper, but product review, design review, audit, and acceptance checks keep the team from shipping the wrong work or a weak experience. These gates complement [code review evals and rubrics](code-review-evals-and-rubrics.md) by reviewing product fit and user-facing delivery, not only code risk.

## Practice Boundaries

- Use should-build gates when a feature idea may be misaligned, oversized, or weakly justified.
- Use design gates before implementation when user experience, workflow fit, or persona fit is material.
- Use audit gates before merge to inspect security, quality, architecture, documentation, UX, and frontend risk by lane.
- Use acceptance gates to verify that the implementation delivers the intended user-facing experience.
- Keep product, design, and technical context documents maintained because stale judgment context weakens every gate.
- Let small fixes use narrower gates when product or design risk is low.

## Authoritative Sources

- [Studious source](../../../raw/processed/jacquardlabsstudious Studious — a product-judgment workflow for Claude Code quality gates, periodic health reviews, and pre-merge audits that examine each piece of work..md)
- [code review evals and rubrics](code-review-evals-and-rubrics.md)
- [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [code review evals and rubrics](code-review-evals-and-rubrics.md)
- [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold product judgment gates separately from code-review eval practice.
