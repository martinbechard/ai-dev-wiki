---
type: "Governance And Risk"
title: "AI Code Evidence Packages"
description: "AI code evidence packages preserve the model, source, review, and security records needed before generated code is trusted."
tags: ["governance-and-risk"]
---

# AI Code Evidence Packages

## Current Understanding

The [October 27 leaf update watch source](../../../raw/processed/2026-10-27/ai-dev-wiki-leaf-update-watch-2026-10-27T210202-0400.json) adds repair-pipeline evidence. A source-attributed find-fix-deploy workflow should retain distinct discovery, validation, sandboxed-draft, human-review, canary, and SRE-monitoring records so completion by any one agent does not collapse the acceptance chain. The vendor workflow is an operating example, not a universal automation claim.

The [October 20 leaf update watch source](../../../raw/processed/2026-10-20/ai-dev-wiki-leaf-update-watch-2026-10-20T205851-0400.json) adds two evidence boundaries. Agentic remediation packages should retain the affected scope, rationale, draft change, and fresh scanner result; evaluator packages should separately record access bounds, independence conditions, publication rights, redaction rules, and retained evidence rather than using an “independent” label as a substitute for the underlying controls.

The [October 9 topic news collector source](../../../raw/processed/2026-10-09/ai-dev-wiki-topic-news-collector-2026-10-09T003223Z.json) adds software-audit-trail evidence. Generated-code evidence packages should preserve who or what made the change, source evidence, prompt or spec input, review path, linked work item, security or privacy checks, acceptance decision, and the audit trail that lets a future reviewer reconstruct why the change was trusted.

AI code evidence packages preserve the model, source, review, and security records needed before generated code is trusted. They make AI-generated or AI-modified code visible as unverified input until normal review, testing, and risk-specific approval have run.

The [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json) records DoD-style guidance that developers and teams remain accountable for AI-generated code, that security- or safety-critical AI-generated changes need human review, that normal review and security testing still apply, and that software evidence should record models, versions, and significant datasets. The local practice is to preserve enough evidence for accountability without turning product-specific government procedure into local policy.

The September 15-16 raw sources add repository metadata, system-of-record workflow, and verified-inventory evidence. The [leaf update watch source](../../../raw/processed/2026-09-15/ai-dev-wiki-leaf-update-watch-2026-09-15T210309-0400.json) records AI-suggested repository custom-property values and governed agentic SDLC dashboards, while the [topic news collector source](../../../raw/processed/2026-09-16/ai-dev-wiki-topic-news-collector-2026-09-16T003033Z.json) adds enforced security baselines and evidence-based pull-request triage. Locally, evidence packages should preserve the taxonomy, policy, ruleset, dashboard, and review-capacity signals that decide whether AI-generated changes receive the right gate.

The [September 21 topic news collector source](../../../raw/processed/2026-09-21/ai-dev-wiki-topic-news-collector-2026-09-22T003230Z.json) adds pipeline-governance evidence from vendor analysis. Broad CloudBees company and product coverage stays upstream; locally, generated-code evidence packages should make owner, reviewer, approval state, cost attribution, build, test, scan, and release-pipeline visibility inspectable together rather than scattered across separate tools.

The September 22 [leaf update watch source](../../../raw/processed/2026-09-22/ai-dev-wiki-leaf-update-watch-2026-09-22T210151-0400.json) adds AI-review lifecycle, feature-engagement, and change-level governance evidence. Broad GitHub, Copilot, DETENT, and CloudBees coverage stays upstream; locally, evidence packages should preserve review overview state, open or resolved findings, previously missed findings, resolution reasons, generated commit-message evidence, feature-specific engagement, customization adoption metrics, owner and reviewer state, build or scan results, cost attribution, and human acceptance evidence as one inspectable record.

The [September 25 topic news collector source](../../../raw/processed/2026-09-25/ai-dev-wiki-topic-news-collector-2026-09-26T003140Z.json) adds decision-log evidence. Agentic coding can increase decision throughput faster than organizational memory, so generated-code evidence packages should preserve rationale for consequential changes, alternatives considered, tradeoffs, operational implications, and revisit triggers when those decisions affect future review, onboarding, incidents, or audits.

The September 29 raw sources add self-managed governance, security-scan, enterprise-record, and oversized-change evidence. The [topic news collector source](../../../raw/processed/2026-09-29/ai-dev-wiki-topic-news-collector-2026-09-30T003135Z.json) records self-managed agentic code governance with context and constraints before writing, independent verification, remediation controls, centralized model governance, dependency-risk checks, and compliance reporting. The [leaf update watch source](../../../raw/processed/2026-09-29/ai-dev-wiki-leaf-update-watch-2026-09-29T210353-0400.json) adds scheduled or commit-triggered security scans, governed data inputs, durable records of agent-produced decisions or documents, and anecdotal review failures where oversized generated PRs hide invented APIs, misplaced code, or authorization changes.

The [October 6 leaf update watch source](../../../raw/processed/2026-10-06/ai-dev-wiki-leaf-update-watch-2026-10-06T210155-0400.json) adds evidence-channel risk. PixelLeak-style screenshot exposure is a reminder that proof artifacts can become data-loss channels when agents satisfy review needs by placing private evidence in public or weakly governed locations. Evidence packages should record:

- Artifact location, visibility, and retention.
- Runtime controls and reviewer access.
- Agent inventory plus package or skill provenance.
- Whether screenshots, logs, traces, or generated evidence are safe to use as proof.

The [October 13 topic news collector source](../../../raw/processed/2026-10-13/ai-dev-wiki-topic-news-collector-2026-10-13T003447Z.json) adds evidence-scoped verification language for AI review. Generated-review findings belong in the evidence package as claims, while verification records should name executed checks, covered code or workflow areas, results, residual unchecked areas, and the human owner who accepted or rejected the risk.

The October 14 raw ingest adds managed telemetry and rollout-metric evidence. The [October 13 leaf update watch source](../../../raw/processed/2026-10-13/ai-dev-wiki-leaf-update-watch-2026-10-13T210852-0400.json) and [October 14 topic news collector source](../../../raw/processed/2026-10-14/ai-dev-wiki-topic-news-collector-2026-10-14T003403Z.json) distinguish user attribution from optional content capture, including prompts, responses, tool arguments, tool outputs, and policy details that can expose code, paths, commands, or tool results. The same topic source records AI security-scan metrics and quality-finding audit events as evidence-package inputs when teams need to review remediation rates, repository coverage, manual dismissals, reopenings, and human acceptance.

This page owns the generated-code evidence package. [Intelligent code review](../coding-practices/intelligent-code-review.md) owns review execution, and [governance controls for agents](governance-controls-for-agents.md) owns the broader local control model.

## Practice Boundaries

- Preserve separate discovery, validation, sandboxed-draft, human-review, canary, and monitored-release records for agentic remediation; no single agent-completion signal proves acceptance.
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
- Include context/constraint evidence, independent verification, remediation control state, centralized model policy, dependency-risk checks, compliance reports, security-scan receipts, and durable agent-produced records when generated code moves toward acceptance.
- Flag oversized generated pull requests as evidence-incomplete when they cannot explain touched files, API assumptions, code placement, dependency choices, or authorization-path changes.
- Treat screenshots, logs, traces, and generated proof artifacts as governed evidence channels whose storage location, visibility, retention, runtime controls, and provenance need review before they can support acceptance.
- Store generated review findings separately from verification evidence, and require the package to say what was checked, what was not checked, and who accepted the remaining risk.
- Separate identity attribution from content capture, and record which telemetry classes are enabled before prompts, responses, tool arguments, tool outputs, commands, paths, or policy details become evidence.
- Preserve AI security-scan rollout metrics and quality-finding override events as adoption evidence only when they remain linked to repository scope, remediation status, and human acceptance.

## Authoritative Sources

- [October 27 leaf update watch source](../../../raw/processed/2026-10-27/ai-dev-wiki-leaf-update-watch-2026-10-27T210202-0400.json)
- [October 20 leaf update watch source](../../../raw/processed/2026-10-20/ai-dev-wiki-leaf-update-watch-2026-10-20T205851-0400.json)
- [October 9 topic news collector source](../../../raw/processed/2026-10-09/ai-dev-wiki-topic-news-collector-2026-10-09T003223Z.json)

- [September 21 topic news collector source](../../../raw/processed/2026-09-21/ai-dev-wiki-topic-news-collector-2026-09-22T003230Z.json)
- [September 25 topic news collector source](../../../raw/processed/2026-09-25/ai-dev-wiki-topic-news-collector-2026-09-26T003140Z.json)
- [September 29 leaf update watch source](../../../raw/processed/2026-09-29/ai-dev-wiki-leaf-update-watch-2026-09-29T210353-0400.json)
- [September 29 topic news collector source](../../../raw/processed/2026-09-29/ai-dev-wiki-topic-news-collector-2026-09-30T003135Z.json)
- [September 22 leaf update watch source](../../../raw/processed/2026-09-22/ai-dev-wiki-leaf-update-watch-2026-09-22T210151-0400.json)
- [September 15 leaf update watch source](../../../raw/processed/2026-09-15/ai-dev-wiki-leaf-update-watch-2026-09-15T210309-0400.json)
- [September 16 topic news collector source](../../../raw/processed/2026-09-16/ai-dev-wiki-topic-news-collector-2026-09-16T003033Z.json)
- [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json)
- [October 6 leaf update watch source](../../../raw/processed/2026-10-06/ai-dev-wiki-leaf-update-watch-2026-10-06T210155-0400.json)
- [October 13 topic news collector source](../../../raw/processed/2026-10-13/ai-dev-wiki-topic-news-collector-2026-10-13T003447Z.json)
- [October 13 leaf update watch source](../../../raw/processed/2026-10-13/ai-dev-wiki-leaf-update-watch-2026-10-13T210852-0400.json)
- [October 14 topic news collector source](../../../raw/processed/2026-10-14/ai-dev-wiki-topic-news-collector-2026-10-14T003403Z.json)
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

- Maintained on 2026-10-27 with source-attributed discovery-to-monitored-release evidence-chain fields for agentic remediation.
- Maintained on 2026-10-20 with remediation and independent-evaluator evidence-package boundaries.
- Maintained on 2026-10-09 with software-audit-trail, source-evidence, prompt/spec input, review-path, work-item, security/privacy check, and acceptance-decision evidence.
- Maintained on 2026-10-14 with telemetry-class, user-attribution, AI-scan metric, quality-finding override, and remediation-status evidence.
- Maintained on 2026-10-13 with generated-review-claim, verification-scope, unchecked-area, and human-risk-acceptance evidence.
- Maintained on 2026-09-29 with self-managed governance, security-scan, remediation-control, dependency-risk, compliance, durable-record, and oversized-generated-PR evidence.
- Maintained on 2026-10-07 with proof-artifact location, visibility, retention, runtime-control, agent-inventory, package-provenance, and reviewer-access evidence.
- Maintained on 2026-09-21 with pipeline-governance evidence package scope from the topic news collector.
- Maintained on 2026-09-22 with AI-review lifecycle, feature-engagement, customization-telemetry, and acceptance-chain evidence.
- Maintained on 2026-09-25 with decision-log, rationale, alternatives, tradeoff, operational implication, and revisit-trigger evidence.
- Maintained on 2026-09-15 with repository metadata, system-of-record workflow, verified-inventory, security-baseline, and PR-triage evidence.
- Created on 2026-09-14 from AI-assisted software development procedure evidence in the September 15 topic news collector.
