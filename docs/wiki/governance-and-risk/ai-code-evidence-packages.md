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

The [September 21 topic news collector source](../../../raw/processed/2026-09-21/ai-dev-wiki-topic-news-collector-2026-09-22T003230Z.json) adds pipeline-governance evidence from vendor analysis. Broad CloudBees company and product coverage stays upstream; locally, generated-code evidence packages should make owner, reviewer, approval state, cost attribution, build, test, scan, and release-pipeline visibility inspectable together rather than scattered across separate tools.

The September 22 [leaf update watch source](../../../raw/processed/2026-09-22/ai-dev-wiki-leaf-update-watch-2026-09-22T210151-0400.json) adds AI-review lifecycle, feature-engagement, and change-level governance evidence. Broad GitHub, Copilot, DETENT, and CloudBees coverage stays upstream; locally, evidence packages should preserve review overview state, open or resolved findings, previously missed findings, resolution reasons, generated commit-message evidence, feature-specific engagement, customization adoption metrics, owner and reviewer state, build or scan results, cost attribution, and human acceptance evidence as one inspectable record.

The [September 25 topic news collector source](../../../raw/processed/2026-09-25/ai-dev-wiki-topic-news-collector-2026-09-26T003140Z.json) adds decision-log evidence. Agentic coding can increase decision throughput faster than organizational memory, so generated-code evidence packages should preserve rationale for consequential changes, alternatives considered, tradeoffs, operational implications, and revisit triggers when those decisions affect future review, onboarding, incidents, or audits.

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
- Keep pipeline evidence, cost attribution, reviewer identity, approval state, build/test/scan results, and release visibility joined when generated changes move toward production.
- Preserve AI-review finding lifecycle, resolution reason, generated commit-message, feature-engagement, customization telemetry, and human acceptance-chain evidence when they affect whether generated code is trusted.
- Include decision-log entries for consequential AI-assisted changes when the rationale, alternatives, tradeoffs, operational implications, or revisit triggers affect future trust in the code.

## Authoritative Sources

- [September 21 topic news collector source](../../../raw/processed/2026-09-21/ai-dev-wiki-topic-news-collector-2026-09-22T003230Z.json)
- [September 25 topic news collector source](../../../raw/processed/2026-09-25/ai-dev-wiki-topic-news-collector-2026-09-26T003140Z.json)
- [September 22 leaf update watch source](../../../raw/processed/2026-09-22/ai-dev-wiki-leaf-update-watch-2026-09-22T210151-0400.json)
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

- Maintained on 2026-09-21 with pipeline-governance evidence package scope from the topic news collector.
- Maintained on 2026-09-22 with AI-review lifecycle, feature-engagement, customization-telemetry, and acceptance-chain evidence.
- Maintained on 2026-09-25 with decision-log, rationale, alternatives, tradeoff, operational implication, and revisit-trigger evidence.
- Maintained on 2026-09-15 with repository metadata, system-of-record workflow, verified-inventory, security-baseline, and PR-triage evidence.
- Created on 2026-09-14 from AI-assisted software development procedure evidence in the September 15 topic news collector.
