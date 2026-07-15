---
type: "Coding Practice"
title: "Intelligent Code Review"
description: "Intelligent code review uses an AI reviewer to compare a change against project rules, source references, risk tiers, contracts, tests, security expectations, and runtime behavior."
tags: ["coding-practices"]
---

# Intelligent Code Review

## Current Understanding

Intelligent code review uses an AI reviewer to compare a change against project rules, source references, risk tiers, contracts, tests, security expectations, and runtime behavior. The reviewer reduces human review load only when it is given the evidence needed to produce actionable findings.

The local practice is source-backed review. Review requests should embed repository instructions, architecture standards, important files, design docs, schema references, known risky modules, and tier-specific checklists. Coherence checks matter because generated changes can make front-end assumptions drift from backend contracts, generated clients, database fields, feature flags, or authorization rules.

The [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json) adds a boundary for diff-focused AI review agents: they can critique pull request changes, compare surrounding code, and suggest fixes before merge, but they are not full QA, SAST policy ownership, or end-to-end acceptance. The [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) adds that AI review can move earlier into PRD and design governance; that broader lifecycle pattern lives in [lifecycle AI review gates](../governance-and-risk/lifecycle-ai-review-gates.md).

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) adds a review-configuration lens: AI review depth, repository exploration tools, and cost-quality measurements should be visible configuration surfaces instead of hidden model behavior. Broad Copilot product coverage stays upstream; locally, review prompts and rubrics should record how deeply the reviewer is expected to inspect files and what retrieval path supports findings.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) adds a review-efficiency signal: context gathering should be targeted to the changed files, neighboring code, tests, and relevant policies. Faster review is only acceptable when findings remain source-backed and the retrieval path is visible enough for a human to audit.

The [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json) reinforces review as a control point rather than optional ceremony. Public sources describe AI-generated changes reaching production with less separate human review, governance struggling to keep up with generation speed, and AI review moving earlier into PRD and design checks. The local rule is that review requests should keep acceptance evidence, retrieval depth, reviewer scope, and final human decision boundaries explicit even when AI review reduces manual effort.

The [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json) and [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json) add review-capacity and reviewer-attention evidence. AI code generation can increase throughput faster than review, validation, provenance, and maintainability controls can absorb it. Review assistants therefore need signal controls, configurable noise levels, source-backed findings, and clear human repair responsibility rather than broader automatic coverage alone.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) and [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json) reinforce recall-first review as an operating choice. Broad detection at the merge boundary can be useful when a filtering layer protects reviewer attention, but the workflow still needs repository and dependency evidence, configurable noise tolerance, and a human-owned repair path for correctness, design, release, and risk tradeoffs.

The [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json) adds deployment and context-aware selection criteria. Review tooling should be selected against source exposure, deployment location, audit evidence, whole-repository context, workflow integration, actionability, team-standard customization, and latency rather than vendor ranking alone.

The [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json) adds review capacity and compliance pressure. As AI-generated code volume grows, review gates should use automated compliance checks, quality gates, runtime evidence, and software-quality taxonomies to protect reviewer attention. Manual review remains necessary for tradeoffs and final judgment, but it should receive evidence packages instead of raw generated-code volume.

The July 7 raw sources add authorship, policy, and localization signals. The [leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) records agent-authored commit visibility and contribution-policy pressure; locally, reviews should preserve agent authorship, violation attribution, and human repair accountability. The [topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) adds security-eval evidence that vulnerability classification is weaker without compilable context, contamination controls, and line-level localization checks.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) adds organization-level review targeting and hostile-repository review risk. Review controls should be scoped by repository risk and owner policy, and autonomous review of untrusted third-party code should run in disposable workspaces with constrained commands, deterministic scanners, and explicit human approval before shell execution or dependency setup.

The [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json) adds an operating-model signal for AI-authored pull requests. Code review should protect understanding retention, reviewer capacity, explicit responsibility, and machine-assisted evidence together. When agents author complete PRs, the review workflow needs clear ownership for what the human reviewer must understand, what automated checks can cover, and what evidence the submitting agent must provide.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) and [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json) add four review-quality signals: multimodal pull-request artifacts can hide agent-readable instructions, model choice is only one part of governed review, full-repository context is needed for security and design findings, and AI-discovered security issues still need patch verification. Review should therefore include binary or image handling rules, repository-context requirements, signal-to-noise controls, and source-to-patch evidence rather than accepting fluent comments as coverage.

The [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json) adds adversarial multi-agent review as a workflow signal, not a blanket acceptance rule. Coordinated implementation and adversarial review can be useful when the topology, reviewer independence, regression proof, and repair ownership are visible; broad runtime or product news stays upstream.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) adds risk-based review and review-surrender signals. Review policy should state when line-by-line reading is mandatory, when tests, static analysis, runtime evidence, and trace evidence can carry the review, and how reviewers record residual risk. Adoption pressure can increase AI-authored pull requests faster than reviewer capacity; local review gates should protect against shallow approval by requiring clear evidence packages and human accountability for the accepted change.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) adds on-demand and pull-request security review signals. AI security review can run inside the active coding loop and ordinary PR surfaces, but findings need labels, severity, confidence, actionable repair suggestions, re-verification, policy enablement, and spend awareness. The local review rule is to keep AI detections distinguishable from deterministic scanners and to require human triage before a generated security finding becomes acceptance evidence.

## Practice Boundaries

- Attach project rules, source references, and relevant diffs before asking for review.
- Use tier-specific checks for UI, app server, data, infrastructure, and security-sensitive changes.
- Check coherence across front-end assumptions, backend contracts, generated clients, database fields, and feature flags.
- Include security checks for secret exposure, authorization gaps, unsafe tool use, prompt injection surfaces, and risky dependencies.
- Keep review output finding-focused so humans can decide whether to accept, reject, or request a fix.
- Treat review as evidence, not as final acceptance.
- Distinguish diff-focused review findings from test results, security policy enforcement, and product acceptance.
- Route pre-code artifact review to lifecycle review gates so code-review pages stay focused on implementation evidence.
- Record the expected review depth and retrieval path when using AI review, especially when cost, latency, or review confidence is part of the tradeoff.
- Prefer targeted retrieval over broad repository scans when it preserves source grounding and reduces review latency or cost.
- Report which context was skipped or considered unnecessary when that omission affects residual risk.
- Keep review gates explicit when generated-code throughput increases or separate manual review becomes less common.
- Tie AI review findings to the artifact under review, whether that artifact is a PRD, design input, code diff, test result, or operational signal.
- Treat review capacity as an operating constraint: generated-code volume must be matched with standards, tests, provenance, maintainability checks, and reviewer-attention controls.
- Keep AI review comments actionable and adjustable so low-signal noise does not consume the human attention the workflow was meant to protect.
- Require the submitting workflow to remain able to repair reviewed code; generated changes that cannot be explained, tested, or fixed are not review-ready.
- Treat recall, precision, filtering, and reviewer attention as separate review-configuration choices.
- Require repository and dependency evidence before a recall-first reviewer claims cross-file or merge-boundary risk.
- Keep human repair and release judgment explicit even when AI review broadens defect detection.
- Treat deployment model, source exposure, audit evidence, and data residency as review-tool selection criteria before measuring review quality.
- Evaluate whether the reviewer understands repository-wide architecture and team standards, not only the changed hunk.
- Use automated compliance checks, quality gates, and runtime evidence to reduce reviewer load without hiding final human judgment.
- Include established software-quality dimensions when reviewing AI-generated changes that are larger than a local fix.
- Preserve agent-authorship and violation-attribution metadata so reviewers can distinguish agent-introduced risk from ordinary human edits.
- Require the submitter to understand, repair, and explain generated code before treating it as review-ready.
- Separate security classification from localization, proof quality, compilation context, and contamination-aware evaluation.
- Scope automated review enablement by repository risk, owner policy, and exception management rather than enabling every repository uniformly.
- Run autonomous review of untrusted third-party repositories inside disposable workspaces with constrained execution and human-approved setup steps.
- Treat AI-authored PR review as a capacity and understanding-retention problem, not only as a defect-detection problem.
- Require submitters to provide source, test, trace, and design evidence that lets reviewers retain system understanding while relying on machine-assisted checks.
- Include image, binary, and generated-asset handling rules when a review or follow-on coding agent can inspect multimodal pull-request content.
- Evaluate AI review systems by repository context, actionable findings, false-positive control, fix validation, and human judgment support rather than model branding alone.
- Require patch-verification evidence for AI-assisted security findings before treating a vulnerability report as resolved.
- Treat adversarial multi-agent review claims as useful only when reviewer independence, regression proof, implementation ownership, and repair accountability are inspectable.
- Keep prompt-injection and untrusted-content gates active during review when the reviewer can inspect issue text, PR assets, generated artifacts, or runtime files.
- Define risk tiers for AI-authored changes so critical paths, security-sensitive work, data migrations, and unclear generated code still require direct human reading.
- Allow evidence-led review only when tests, static analysis, runtime checks, trace evidence, and source links are strong enough for a reviewer to document residual risk.
- Watch for review-surrender pressure when AI adoption is driven by peer or manager visibility; a pull request is not ready just because an agent produced it quickly.
- Treat on-demand AI security review as a pre-merge guardrail whose findings need labels, severity, confidence, suggested repair, and re-verification evidence.
- Keep AI security detections separate from deterministic scanner results in PR review summaries, policy decisions, and residual-risk notes.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [Generated code refactoring](generated-code-refactoring.md)
- [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json)
- [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json)
- [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json)
- [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json)
- [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json)
- [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json)
- [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [fix branch and PR packaging](fix-branch-and-pr-packaging.md)
- [lifecycle AI review gates](../governance-and-risk/lifecycle-ai-review-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on intelligent self-code-review, source references, tier-specific review, coherence checks, and security checks.
- Maintained on 2026-06-24 with diff-focused review boundaries and routing to lifecycle review gates for PRD or design review.
- Maintained on 2026-06-25 with review depth, retrieval path, and cost-quality measurement as explicit AI review configuration surfaces.
- Maintained on 2026-06-27 with targeted context gathering and skipped-context residual-risk reporting.
- Maintained on 2026-06-29 with review-gate evidence for higher generated-code throughput and earlier lifecycle review.
- Maintained on 2026-07-03 with review-capacity, reviewer-attention, generated-code repairability, and configurable review-signal controls.
- Maintained on 2026-07-04 with recall-first review, filtering, repository evidence, and human repair boundaries.
- Maintained on 2026-07-05 with deployment-model, source-exposure, audit, repository-context, actionability, customization, and latency selection criteria.
- Maintained on 2026-07-06 with compliance checks, runtime evidence, software-quality dimensions, and reviewer-load controls.
- Maintained on 2026-07-07 with agent-authorship metadata, violation attribution, contribution-policy accountability, and security-localization eval controls.
- Maintained on 2026-07-09 with organization-scoped review targeting and untrusted-repository autonomous review boundaries.
- Maintained on 2026-07-10 with AI-authored PR review capacity, understanding-retention, and evidence-package requirements.
- Maintained on 2026-07-11 with multimodal PR review, repository-context, signal-to-noise, and patch-verification requirements.
- Maintained on 2026-07-12 with adversarial multi-agent review topology, reviewer independence, regression proof, and repair-accountability requirements.
- Maintained on 2026-07-13 with risk-based review, review-surrender controls, and evidence-led acceptance boundaries for AI-authored changes.
- Maintained on 2026-07-14 with on-demand security review, AI-labeled PR detections, confidence, re-verification, and human-triage requirements.
