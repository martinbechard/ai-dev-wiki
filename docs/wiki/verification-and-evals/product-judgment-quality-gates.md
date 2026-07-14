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

The [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json) and [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json) add quality and compliance gates. Product judgment should include runtime environment checks, compliance evidence, audit logs, human oversight, and established software-quality dimensions when AI-generated work changes customer-facing or regulated workflows. Those gates should stay separate from vendor or standards background, which belongs upstream unless it changes local acceptance practice.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) adds frontend verification as a product-judgment gate. AI-generated UI should be accepted against realistic user conditions: task completion, accessibility, keyboard interaction, focus behavior, state changes, loading, and error paths. Screenshots and successful renders are supporting evidence, not product acceptance.

## Practice Boundaries

- Use should-build gates when a feature idea may be misaligned, oversized, or weakly justified.
- Use design gates before implementation when user experience, workflow fit, or persona fit is material.
- Use audit gates before merge to inspect security, quality, architecture, documentation, UX, and frontend risk by lane.
- Use acceptance gates to verify that the implementation delivers the intended user-facing experience.
- Keep product, design, and technical context documents maintained because stale judgment context weakens every gate.
- Let small fixes use narrower gates when product or design risk is low.
- Include runtime, compliance, audit, oversight, maintainability, reliability, and security evidence when AI-generated work carries product or regulatory risk.
- Include realistic frontend task checks for accessibility, keyboard use, focus management, state transitions, loading behavior, and error recovery before accepting AI-generated UI.
- Treat screenshots and rendered previews as partial evidence; they do not replace user-flow acceptance for interactive work.

## Authoritative Sources

- [Studious source](../../../raw/processed/jacquardlabsstudious Studious — a product-judgment workflow for Claude Code quality gates, periodic health reviews, and pre-merge audits that examine each piece of work..md)
- [code review evals and rubrics](code-review-evals-and-rubrics.md)
- [verification tax and acceptance gates](verification-tax-and-acceptance-gates.md)
- [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json)
- [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)

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
- Maintained on 2026-07-06 with runtime, compliance, audit, oversight, and software-quality evidence gates.
- Maintained on 2026-07-13 with realistic frontend task checks and screenshot-versus-acceptance boundaries.
