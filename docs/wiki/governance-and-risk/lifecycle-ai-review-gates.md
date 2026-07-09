---
type: "Governance And Risk"
title: "Lifecycle AI Review Gates"
description: "AI review gates apply before implementation, not only after code exists."
tags: ["governance-and-risk"]
---

# Lifecycle AI Review Gates

## Current Understanding

AI review gates apply before implementation, not only after code exists. Requirements, PRDs, design inputs, threat assumptions, acceptance criteria, and code changes can each be reviewed by an assistant when the source package and acceptance bar are explicit.

The local practice is to place AI review at lifecycle boundaries where ambiguity is cheapest to fix. A review gate should state the artifact under review, the source authorities, the questions the assistant may judge, and the human decision that remains outside the model. Broad company examples from the [topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) remain upstream-owned; this page owns the local lifecycle gate pattern.

Code review remains a specialized downstream gate in [intelligent code review](../coding-practices/intelligent-code-review.md). Lifecycle review gates cover earlier project artifacts and handoff points so implementation work starts with clearer scope, risks, and acceptance evidence.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) reinforce lifecycle gates as platform practice. Specs, GitHub issues, RFCs, review prompts, security checks, and operational feedback can all become reviewable artifacts before or during agent execution. Broad Microsoft, GitHub, Linear, and Kestra product details stay upstream; the local rule is that each lifecycle gate needs a source-of-truth artifact and a human-owned decision boundary.

The [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json) adds public evidence that review is moving both downstream and upstream: generated code is reaching production with less separate manual review, while AI checks are also being applied to PRDs, design inputs, context-aware reviews, and scoped reviewer responsibilities. The local pattern is a chain of gates across requirements, design, implementation, security, and acceptance rather than a single code-review checkpoint.

The [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) reinforces generator-reviewer separation. A coding agent can draft or modify implementation, but a formal gate should use independent evidence, tests, review rubrics, or a separate reviewer path before approval. Self-review by the original generator can be useful triage, but it should not satisfy release readiness on its own.

The [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json) adds execution-security evidence for lifecycle gates. Review should happen before cloned project setup, automated troubleshooting, sandbox promotion, or production-adjacent execution, because repository metadata and generated commands can become the attack path before a diff exists.

## Practice Boundaries

- Review PRDs, design notes, requirements, threat assumptions, and acceptance criteria before asking an agent to implement.
- Attach source authorities and known constraints so review findings can cite the evidence they depend on.
- Ask for decision-relevant gaps, contradictions, missing acceptance checks, risky assumptions, and unresolved ownership.
- Keep final product, architecture, security, and delivery decisions with named humans or established project procedures.
- Convert accepted review findings into source updates, backlog items, tests, or open questions before implementation begins.
- Do not treat lifecycle AI review as a substitute for build, test, lint, runtime, security, or code review gates.
- Use issue, RFC, spec, and workflow artifacts as source authorities for agent work so planning, implementation, review, security, and operations can be checked against the same intent.
- Define which lifecycle gate owns review when generated code, PRD quality, design risk, security posture, and production acceptance are all affected by the same agent workflow.
- Keep generator, reviewer, test, and approver responsibilities separate when the review gate affects release, security, or production acceptance.
- Add pre-execution gates for untrusted repository setup, generated command execution, sandbox promotion, and sensitive-code workflows.
- Treat execution-boundary evidence as part of lifecycle review before accepting an agent-produced implementation or repair.

## Authoritative Sources

- [Topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [intelligent code review](../coding-practices/intelligent-code-review.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [governance controls for agents](governance-controls-for-agents.md)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json)
- [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json)
- [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance-and-risk](index.md)
- [source reconciliation and routing](../source-workflows/source-reconciliation-and-routing.md)
- [product judgment quality gates](../verification-and-evals/product-judgment-quality-gates.md)
- [fix branch and PR packaging](../coding-practices/fix-branch-and-pr-packaging.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-24 from public source signals about AI review moving from code review into PRD and design governance.
- Maintained on 2026-06-25 with platform-lifecycle signals for specs, issues, review prompts, security checks, and operational feedback as reviewable artifacts.
- Maintained on 2026-06-29 with continuous lifecycle review gates across requirements, design, code, security, and acceptance.
- Maintained on 2026-07-01 with generator-reviewer separation for formal lifecycle gates.
- Maintained on 2026-07-08 with pre-execution lifecycle gates for untrusted setup, generated commands, and sensitive-code promotion.
