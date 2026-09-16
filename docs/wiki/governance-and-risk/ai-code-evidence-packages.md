---
type: "Governance And Risk"
title: "AI Code Evidence Packages"
description: "AI code evidence packages preserve the model, source, review, and security records needed before generated code is trusted."
tags: ["governance-and-risk"]
---

# AI Code Evidence Packages

## Current Understanding

AI code evidence packages preserve the model, source, review, and security records needed before generated code is trusted. They make AI-generated or AI-modified code visible as unverified input until normal review, testing, and risk-specific approval have run.

The [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json) records DoD-style guidance that developers and teams remain accountable for AI-generated code, that security- or safety-critical AI-generated changes need human review, that normal review and security testing still apply, and that software evidence should record models, versions, and significant datasets. The local practice is to preserve enough evidence for accountability without turning product-specific government procedure into local policy.

The September 15-16 raw sources add repository metadata, system-of-record workflow, and verified-inventory evidence. The [leaf update watch source](../../../raw/processed/2026-09-15/ai-dev-wiki-leaf-update-watch-2026-09-15T210309-0400.json) records AI-suggested repository custom-property values and governed agentic SDLC dashboards, while the [topic news collector source](../../../raw/processed/2026-09-16/ai-dev-wiki-topic-news-collector-2026-09-16T003033Z.json) adds enforced security baselines and evidence-based pull-request triage. Locally, evidence packages should preserve the taxonomy, policy, ruleset, dashboard, and review-capacity signals that decide whether AI-generated changes receive the right gate.

This page owns the generated-code evidence package. [Intelligent code review](../coding-practices/intelligent-code-review.md) owns review execution, and [governance controls for agents](governance-controls-for-agents.md) owns the broader local control model.

## Practice Boundaries

- Treat AI-generated or AI-modified code as unverified input until review and tests pass.
- Record the model or assistant route, version, and significant source data when those facts affect risk or reproducibility.
- Apply ordinary review and security testing to generated code instead of accepting generation as evidence.
- Require explicit human review for security- or safety-critical generated changes.
- Keep accountability with the developer or team that accepts the change.
- Treat AI-suggested repository metadata as draft evidence until policy owners confirm the taxonomy and ruleset mapping.
- Preserve inventory, usage-dashboard, verified-agent, MCP/tool, and kill-switch evidence when those signals decide review depth or production gates.
- Include priority, risk, owner, blocker, dependency, and effort signals when generated pull-request volume exceeds ordinary reviewer capacity.

## Authoritative Sources

- [September 15 leaf update watch source](../../../raw/processed/2026-09-15/ai-dev-wiki-leaf-update-watch-2026-09-15T210309-0400.json)
- [September 16 topic news collector source](../../../raw/processed/2026-09-16/ai-dev-wiki-topic-news-collector-2026-09-16T003033Z.json)
- [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json)
- [intelligent code review](../coding-practices/intelligent-code-review.md)
- [governance controls for agents](governance-controls-for-agents.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance and risk](index.md)
- [intelligent code review](../coding-practices/intelligent-code-review.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-09-15 with repository metadata, system-of-record workflow, verified-inventory, security-baseline, and PR-triage evidence.
- Created on 2026-09-14 from AI-assisted software development procedure evidence in the September 15 topic news collector.
