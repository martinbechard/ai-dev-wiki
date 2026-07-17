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

## Authoritative Sources

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

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold verification-tax and acceptance-gate practice for agentic delivery.
- Maintained on 2026-06-23 to connect reusable skill contracts to proof standards.
- Maintained on 2026-07-07 with evidence-path gates for tool-use, localization, step-state, and runtime telemetry failures.
- Maintained on 2026-07-11 with verification-gap guidance for validation capacity, maintainability review, and regression ownership.
- Maintained on 2026-07-12 with staged verifier triage, trace assertions, side-effect safety, and sandbox evidence for coding-agent acceptance.
- Maintained on 2026-07-16 with fleet, model-routed review, grader, judge, and human-attention capacity budgeting.
