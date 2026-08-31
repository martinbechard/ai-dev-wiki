---
type: "Verification And Eval"
title: "Verification Tax And Acceptance Gates"
description: "Agentic delivery shifts bottlenecks from generation to validation."
tags: ["verification-and-evals"]
---

# Verification Tax And Acceptance Gates

## Current Understanding

Agentic delivery shifts bottlenecks from generation to validation. Generated code, agent actions, and candidate answers can arrive quickly, but review, source grounding, runtime inspection, and human acceptance decide whether the result is usable.

The local operating model should budget a verification tax for AI-assisted work. Faster generation without stronger validation creates more untrusted output, not more finished work. Acceptance gates should match the change surface: source reconciliation for wiki claims, build and tests for code, runtime checks for user-visible behavior, and human review for consequential decisions.

The [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md) adds a reusable-procedure boundary: a skill should define the evidence that must exist before an agent can call the work complete. This page owns the delivery-level acceptance practice. The mechanics of eval graders live in [judge grader boundaries](judge-grader-boundaries.md), and the general workflow loop lives in [verification loops and evals](verification-loops-and-evals.md).

The July 7 raw sources add a verification-cost refinement. The [topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) separates tool-use failures and vulnerability localization from final success labels, while the [leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) adds step-level state scoring and runtime telemetry. Acceptance gates should therefore check the evidence path when tool use, security, or runtime state matters, not only the final answer.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) adds a verification-gap warning. AI coding assistants can reduce generation cost faster than teams increase validation capacity, so acceptance gates should explicitly budget test authoring, maintainability review, architecture judgment, regression ownership, and human acceptance. Throughput is not a success measure until generated changes survive the required verification path.

The [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json) adds a staged-verification refinement. Environment-free patch checking can reduce verification tax when it filters obviously weak candidates before CI, reviewer, or sandbox cost, but it does not replace repository tests, runtime checks, or human acceptance for consequential changes.

The [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json) reinforces acceptance gates as trace and side-effect checks around whole coding-agent systems. Approval checks, sandbox evidence, token or cost signals, and trace assertions should appear before a workflow claims a generated change is review-ready.

The [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json) and [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json) add fleet and grader-capacity signals. Coding-agent fleets, model-routed review, deterministic graders, LLM judges, and human review should be scheduled as one verification system; adding more agents should wait when review queues, benchmark calibration, or human attention are already the limiting resource.

The July 17 raw sources add acceptance-gate refinements for production agents, security remediation, and performance work. The [topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) records dependency remediation and agentic autofix flows that require scanner reruns and draft-PR boundaries, while performance baselines, incremental-build measurements, rollback rules, and user approvals live in [agent-assisted performance optimization gates](agent-assisted-performance-optimization-gates.md). The [leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json) adds online trace, tool-correctness, security, sandbox, and outcome-state gates for production agent workflows.

The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) adds a verifier-health signal from a public CI log. A slow, wedged, or repeatedly red gate can hide unrelated regressions, so acceptance practice should check gate freshness, capacity, and failure-signal quality before treating CI status as meaningful evidence.

The August 15 raw sources add semantic milestone and production-readiness gates. The [topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json) records a CI-red incident where command exit success was mistaken for delivery success, reinforcing that acceptance gates must inspect external CI, deployment, and pull-request state. The [leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) adds durable execution, scoped access, containment, behavior-baseline, memory-poisoning, and repository-baiting evidence. Acceptance should prove the externally meaningful milestone and the control state, not only the agent narrative or final command status.

The August 16 raw sources add a review-capacity planning rule. The [topic news collector source](../../../raw/processed/2026-08-16/ai-dev-wiki-topic-news-collector-2026-08-16T203133-0400.json) argues that faster AI-generated implementation shifts effort toward debugging, review, and explicit defect-risk selection. The [leaf update watch source](../../../raw/processed/2026-08-16/ai-dev-wiki-leaf-update-watch-2026-08-16T210208-0400.json) reinforces small reversible diffs, baselines, and design-owner review for refactoring or optimization. Acceptance gates should therefore size generation throughput against available tests, reviewer ownership, rollback paths, and acceptable defect risk before expanding autonomous loops.

The August 17 topic news collector adds release-tax and frontend-agent evaluation signals. Acceptance should measure defect escape, change failure, trust, deployed behavior, retries, tool-call traces, and recovery evidence when AI coding increases delivery speed. Throughput remains a weak success measure until the resulting workflow proves release confidence and user-visible behavior.

The [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json) reinforces verification capacity as an adoption bottleneck:

- AI code factories should be evaluated against user-flow verification and E2E capacity.
- Flake handling and feedback loops should be scaled before generation throughput increases.
- Reviewable evidence matters more than generated lines or PR count.

The August 23 raw sources add runtime-proof and policy-gate refinements. The [topic news collector source](../../../raw/processed/2026-08-23/ai-dev-wiki-topic-news-collector-2026-08-24T003154Z.json) emphasizes that AI review, browser testing, enterprise agent trials, and toolchain layers should produce reviewable proof in the issue, pull request, or operating record. The [leaf update watch source](../../../raw/processed/2026-08-23/ai-dev-wiki-leaf-update-watch-2026-08-23T210505-0400.json) adds execution-policy gates for generated code, business-impact controls for governed AI systems, and high-risk action gates for regulated agent work.

The August 28 and 29 raw sources add verification-capacity evidence for review defaults, prototype promotion, and human review load. The [topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) records policy changes, default review effort, prototype-to-deployment trust, and developer-experience concerns about review burden. The [leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json) records durable runtime, AI-generated-code production, prompt-versioning, and structured-output eval evidence. Locally, acceptance gates should measure review capacity, policy defaults, durable runtime proof, and product trust before throughput is counted as success.

The August 30 raw sources add spec-linked and production-reliability acceptance evidence. The [leaf update watch source](../../../raw/processed/2026-08-30/ai-dev-wiki-leaf-update-watch-2026-08-30T210135-0400.json) treats specs as measurable implementation inputs, while the [topic news collector source](../../../raw/processed/2026-08-30/ai-dev-wiki-topic-news-collector-2026-08-31T003307Z.json) reinforces that agent-generated code needs fail-first proof plus reviewable production gates.

## Practice Boundaries

- Decide the acceptance gate before claiming a task is complete.
- Use build, test, lint, runtime checks, source checks, and human review according to the risk of the change.
- Report material verification results in completion notes so trust is attached to evidence.
- Treat blocked verification as a blocker or residual risk, not as a successful result.
- Budget review time when agentic workflows increase output volume.
- Keep human acceptance explicit for consequential changes, external actions, or uncertain evidence.
- Encode recurring proof standards in skills and runbooks so completion checks travel with the procedure.
- Add trace, step-state, tool-result-use, localization, and runtime telemetry gates when final output can hide the failure mode.
- Treat validation capacity as the bottleneck for AI-assisted delivery and plan review, tests, maintainability checks, and regression ownership before increasing generation throughput.
- Use cheap verifier triage to allocate scarce CI, sandbox, or reviewer attention, while keeping authoritative gates tied to the repository and risk surface.
- Require trace assertions, side-effect safety, approval checks, and sandbox evidence when a coding-agent harness claims a change is ready for review.
- Treat coding-agent fleet size, model-routed review, deterministic grading, LLM judging, and human attention as one verification-capacity budget.
- Require scanner reruns and draft-PR boundaries when agents propose security remediation, and route baseline measurements, representative workload evidence, rollback rules, and user approvals for optimization work through the performance optimization gates.
- Gate production agents on online traces, right-tool and right-argument evidence, outcome-state checks, security checks, and sandbox evidence before treating results as accepted.
- Verify the verifier by checking gate freshness, runner capacity, and hidden-failure risk when CI failures or long queues can mask the actual regression signal.
- Require milestone gates to check external CI, deployment, pull-request, containment, memory, repository-provenance, and behavior-baseline evidence before accepting a long-running agent's completion claim.
- Treat generated-code throughput as a verification-capacity input; require explicit defect-risk tolerance, test depth, reviewer ownership, and rollback evidence before increasing autonomy.
- Require small reversible diffs, design-owner review, regression baselines, and measurement evidence when agent-assisted refactoring or optimization changes risk.
- Measure defect escape, change failure, trust, deployed behavior, retries, tool-call traces, and recovery evidence before treating faster AI-assisted delivery as accepted work.
- Treat user-flow verification, E2E capacity, flake handling, feedback loops, and reviewable evidence as scaling constraints for AI code factories and high-throughput agent workflows.
- Require browser screenshots, recordings, reproducible failure reports, runtime traces, or policy-gate records to land in the review surface when the claim depends on executed behavior.
- Gate generated or AI-carried code on behavior and execution-policy evidence when source provenance alone cannot prove runtime safety.
- Treat regulated or business-impacting agent actions as acceptance-gate decisions requiring explicit risk class, approval evidence, execution trace, and rollback or escalation path.
- Require agent-readable specs to name verification criteria, expected contract evidence, and independent verifier responsibilities when the requirement becomes implementation input.
- Treat expected-failure proof, layered test results, review notes, documentation intent, and deterministic CI as the acceptance package for production-oriented agent TDD.

## Authoritative Sources

- [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json)
- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json)
- [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json)
- [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json)
- [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json)
- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [August 15 topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [August 16 topic news collector source](../../../raw/processed/2026-08-16/ai-dev-wiki-topic-news-collector-2026-08-16T203133-0400.json)
- [August 16 leaf update watch source](../../../raw/processed/2026-08-16/ai-dev-wiki-leaf-update-watch-2026-08-16T210208-0400.json)
- [August 17 topic news collector source](../../../raw/processed/2026-08-17/ai-dev-wiki-topic-news-collector-2026-08-17T203101-0400.json)
- [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json)
- [August 23 topic news collector source](../../../raw/processed/2026-08-23/ai-dev-wiki-topic-news-collector-2026-08-24T003154Z.json)
- [August 23 leaf update watch source](../../../raw/processed/2026-08-23/ai-dev-wiki-leaf-update-watch-2026-08-23T210505-0400.json)
- [August 30 leaf update watch source](../../../raw/processed/2026-08-30/ai-dev-wiki-leaf-update-watch-2026-08-30T210135-0400.json)
- [August 30 topic news collector source](../../../raw/processed/2026-08-30/ai-dev-wiki-topic-news-collector-2026-08-31T003307Z.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification-and-evals](index.md)
- [generated code refactoring](../coding-practices/generated-code-refactoring.md)
- [portable agent skills and runbooks](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [agent-assisted performance optimization gates](agent-assisted-performance-optimization-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-08-29 with review-capacity, default review-effort, prototype trust, durable-runtime, prompt-version, structured-output, and human-review-load acceptance evidence.
- Created on 2026-06-23 to hold verification-tax and acceptance-gate practice for agentic delivery.
- Maintained on 2026-06-23 to connect reusable skill contracts to proof standards.
- Maintained on 2026-07-07 with evidence-path gates for tool-use, localization, step-state, and runtime telemetry failures.
- Maintained on 2026-07-11 with verification-gap guidance for validation capacity, maintainability review, and regression ownership.
- Maintained on 2026-07-12 with staged verifier triage, trace assertions, side-effect safety, and sandbox evidence for coding-agent acceptance.
- Maintained on 2026-07-16 with fleet, model-routed review, grader, judge, and human-attention capacity budgeting.
- Maintained on 2026-07-17 with separate security remediation, production-agent trace, tool-correctness, sandbox, outcome-state, and performance-optimization gate routing.
- Maintained on 2026-07-27 with CI gate freshness, capacity, and hidden-failure verification guidance.
- Maintained on 2026-08-15 with semantic CI/deployment milestone, containment, memory-provenance, repository-provenance, behavior-baseline, and control-state acceptance gates.
- Maintained on 2026-08-16 with review-capacity planning, defect-risk tolerance, reversible-diff, baseline, and design-owner acceptance evidence.
- Maintained on 2026-08-17 with release-tax, defect-escape, change-failure, trust, deployed-behavior, retry, trace, and recovery-evidence acceptance signals.
- Maintained on 2026-08-21 with user-flow verification, E2E capacity, flake handling, feedback-loop, and reviewable-evidence scaling constraints.
- Maintained on 2026-08-23 with browser-test proof, execution-policy, business-impact, and regulated-action gate evidence.
- Maintained on 2026-08-30 with spec-linked verification criteria, independent verifier responsibility, expected-failure proof, layered-test, review, documentation, and deterministic-CI acceptance evidence.
