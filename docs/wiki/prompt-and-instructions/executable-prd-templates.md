---
type: "Prompt And Instructions"
title: "Executable PRD Templates"
description: "Executable PRD templates are product specifications written so coding agents can use them as controlled implementation inputs."
tags: ["prompt-and-instructions"]
---

# Executable PRD Templates

## Current Understanding

The [October 9 topic news collector source](../../../raw/processed/2026-10-09/ai-dev-wiki-topic-news-collector-2026-10-09T003223Z.json) adds spec-driven coding comparison evidence. Executable PRDs should distinguish vibe, agentic, and spec-driven coding inputs by how much intent, constraints, acceptance criteria, and verification evidence are explicit before the agent starts implementation.

Executable PRD templates are product specifications written so coding agents can use them as controlled implementation inputs. The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) records a routing source about PRD templates, and the primary [Product Map PRD guardrails source](https://www.productmap.io/blog/prd-for-ai-agent-guardrails) supports the core boundary that agent-facing PRDs need permissions, approval gates, logging, escalation, and eval-style done criteria. Broad product and coding-agent background stays upstream; locally, the practice is to review PRD templates as prompt and instruction artifacts when agents load them.

An executable PRD should not only describe desired product behavior. It should state:

- The agent's autonomy boundary.
- Allowed tools and actions.
- Human approval points.
- Failure fallback and escalation owner.
- Logging requirements for each run.
- Seed verification checks or eval cases for variable outputs.

The July 27 routing source also mentions cost envelopes and version-controlled template edits, but those fields stay as follow-up routing notes until primary sources corroborate them.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds requirements-to-review workflow evidence. When an AI-native build workflow packages brand or product context, requirements, coding-agent prompts, code review, deployment, analytics, and search into one instructional chain, the executable PRD should identify which fields become coding input, which become review criteria, and which become deployment verification evidence.

The [August 8 topic news collector source](../../../raw/processed/2026-08-08/ai-dev-wiki-topic-news-collector-2026-08-08T203357-0400.json) adds algorithm-outline evidence from an AI-assisted algorithms book listing. The local implication is specification shape: executable PRDs and algorithm outlines should define intended outcomes, invariants, correctness conditions, and acceptance checks in a form that a coding agent can translate into implementation and that a verifier can check.

The [August 27 topic news collector source](../../../raw/processed/2026-08-27/ai-dev-wiki-topic-news-collector-2026-08-27T003207Z.json) adds requirements-validation evidence. MCP access can govern whether an agent may read a requirement, under whose identity, and with what audit record, but it does not prove that the requirement is correct, complete, unambiguous, testable, or endorsed. Locally, executable PRDs should make validated status, ambiguity markers, reviewer perspectives, decision records, and acceptance criteria explicit before requirements become agent-readable implementation input.

The [August 30 leaf update watch source](../../../raw/processed/2026-08-30/ai-dev-wiki-leaf-update-watch-2026-08-30T210135-0400.json) adds public SpecMine and spec-driven development evidence. PRDs become more agent-executable when they link requirement intent to repository evidence and independent verification instead of living as planning prose alone.

The [September 28 topic news collector source](../../../raw/processed/2026-09-28/ai-dev-wiki-topic-news-collector-2026-09-29T003227Z.json) and [September 28 leaf update watch source](../../../raw/processed/2026-09-28/ai-dev-wiki-leaf-update-watch-2026-09-28T210333-0400.json) add architecture-request and context-repository evidence. Agent-facing architecture or PRD packages should make quality attributes measurable, record constraints and tradeoffs, identify which external documents were promoted into reviewed Markdown, and require review of generated tests before those tests become acceptance evidence.

The [October 5 leaf update watch source](../../../raw/processed/2026-10-05/ai-dev-wiki-leaf-update-watch-2026-10-05T210255-0400.json) adds spec-driven development evidence for coding agents. Executable specs should pair behavioral requirements with architectural contracts, repository-knowledge maps, reviewable task breakdowns, automated architecture checks, and human inspection checkpoints so agents do not turn vague intent into unreviewed implementation authority.

## Practice Boundaries

- Include allowed tools, human approval points, fallback or escalation behavior, logging requirements, and verification seeds when a PRD is loaded by a coding agent.
- Keep product decisions and unresolved tradeoffs explicit instead of letting the agent infer them from prose.
- Link implementation plans and review gates back to the PRD fields that created the agent's authority.
- Treat routing newsletters or secondary summaries as pointers until primary template sources are reviewed.
- Keep PRD generation, coding-agent prompts, code review criteria, and deployment verification linked as one chain when a workflow teaches end-to-end AI-assisted builds.
- Capture intended outcomes, invariants, correctness conditions, and acceptance checks explicitly when an algorithm outline becomes coding-agent input.
- Scope agent access to validated requirement sections and make ambiguity, endorsement, reviewer perspective, decision record, and testability fields visible before the PRD authorizes implementation.
- Link executable PRDs or specs to code references, requirement indexes, scope boundaries, and verification criteria when those artifacts drive agent implementation.
- Treat separate verifier-agent expectations as part of the PRD contract when spec drift or requirement ambiguity would otherwise reach merge review late.
- Keep agent-facing specs alive through implementation by pairing requirements, technical design, task breakdown, and verifier expectations with drift checks instead of treating the spec as a one-time prompt.
- For platform-backed app specs, identify official platform context, deterministic CLI routes, privileged MCP access, environment separation, audit logs, scoped permissions, and reversible versions before the agent moves from prompt to production change.
- Make quality attributes, constraints, tradeoffs, promoted source documents, and generated-test review explicit before a PRD authorizes architecture or implementation work.
- Pair behavioral requirements with architectural contracts, repository maps, reviewable task breakdowns, automated architecture checks, and human inspection checkpoints.

## Authoritative Sources

- [October 9 topic news collector source](../../../raw/processed/2026-10-09/ai-dev-wiki-topic-news-collector-2026-10-09T003223Z.json)

- [September 5 leaf update watch source](../../../raw/processed/2026-09-05/ai-dev-wiki-leaf-update-watch-2026-09-05T210231-0400.json)
- [September 5 topic news collector source](../../../raw/processed/2026-09-05/ai-dev-wiki-topic-news-collector-2026-09-06T003226Z.json)
- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [Product Map PRD guardrails source](https://www.productmap.io/blog/prd-for-ai-agent-guardrails)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [August 8 topic news collector source](../../../raw/processed/2026-08-08/ai-dev-wiki-topic-news-collector-2026-08-08T203357-0400.json)
- [August 27 topic news collector source](../../../raw/processed/2026-08-27/ai-dev-wiki-topic-news-collector-2026-08-27T003207Z.json)
- [August 30 leaf update watch source](../../../raw/processed/2026-08-30/ai-dev-wiki-leaf-update-watch-2026-08-30T210135-0400.json)
- [September 28 topic news collector source](../../../raw/processed/2026-09-28/ai-dev-wiki-topic-news-collector-2026-09-29T003227Z.json)
- [September 28 leaf update watch source](../../../raw/processed/2026-09-28/ai-dev-wiki-leaf-update-watch-2026-09-28T210333-0400.json)
- [October 5 leaf update watch source](../../../raw/processed/2026-10-05/ai-dev-wiki-leaf-update-watch-2026-10-05T210255-0400.json)
- [request packages and file boundaries](request-packages-and-file-boundaries.md)
- [instruction hierarchy and artifact boundaries](instruction-hierarchy-and-artifact-boundaries.md)
- [research plan implement review lifecycle](../agent-workflows/research-plan-implement-review-lifecycle.md)
- [lifecycle AI review gates](../governance-and-risk/lifecycle-ai-review-gates.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [request packages and file boundaries](request-packages-and-file-boundaries.md)
- [instruction hierarchy and artifact boundaries](instruction-hierarchy-and-artifact-boundaries.md)
- [research plan implement review lifecycle](../agent-workflows/research-plan-implement-review-lifecycle.md)
- [lifecycle AI review gates](../governance-and-risk/lifecycle-ai-review-gates.md)

## Open Questions

- Primary Product Map evidence for cost envelopes and version-controlled template edits has not yet been captured; keep those as routing notes until corroborated.

## Maintenance Notes

- Maintained on 2026-10-09 with vibe, agentic, and spec-driven coding boundaries for intent, constraints, acceptance criteria, and verification evidence.
- Maintained on 2026-09-05 with living-spec drift checks, requirement/design/task breakdown, official platform context, CLI/MCP routing, environment separation, audit, permissions, and reversible-version evidence.
- Created on 2026-07-27 from July 27 raw-source evidence about PRD templates as executable agent inputs.
- Maintained on 2026-07-30 with PRD-to-code-review-to-deployment workflow chaining for AI-native build instruction.
- Maintained on 2026-08-08 with AI-checkable algorithm outline fields for outcomes, invariants, correctness conditions, and acceptance checks.
- Maintained on 2026-08-26 with requirement-validation status, ambiguity markers, reviewer perspectives, decision records, and testability gates before agent-readable implementation input.
- Maintained on 2026-08-30 with repository-linked spec, reference-index, scope-boundary, verification-criteria, and verifier-agent evidence.
- Maintained on 2026-09-28 with measurable quality attributes, tradeoff, reviewed-context-repository, and generated-test-review evidence.
- Maintained on 2026-10-06 with spec-driven architectural contracts, repository maps, task breakdowns, automated checks, and inspection checkpoints.
