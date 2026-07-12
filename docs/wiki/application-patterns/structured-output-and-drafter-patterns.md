---
type: "Application Pattern"
title: "Structured Output And Drafter Patterns"
description: "Structured output makes model intent executable by giving deterministic code a schema, DSL, or typed artifact to validate."
tags: ["application-patterns"]
---

# Structured Output And Drafter Patterns

## Current Understanding

Structured output makes model intent executable by giving deterministic code a schema, DSL, or typed artifact to validate. The drafter pattern uses the model for fuzzy translation, then lets normal code validate, execute, retry, persist, and audit the result.

This pattern fits filters, transformations, workflow steps, UI changes, business actions, and tool arguments where plain prose would be too ambiguous for downstream execution. The model drafts the artifact; the harness owns schema validation, permission checks, execution behavior, and failure handling.

The [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) adds latency and verification-cost evidence for structured agent outputs. Function-call arguments, JSON payloads, and repeated reasoning trace shapes can be predictable enough for drafter-style acceleration, but the local rule is still that validators, permissions, and audit decide acceptance. Speed improvements only matter when schema validity, latency, and failure evidence are measured across the whole agent loop.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) adds an artifact-producing agent lens. When agents produce spreadsheets, slides, documents, web apps, or other finished files, the harness should treat each artifact as a structured output with source traceability, connector scope, local-file access rules, approval pauses, validation checks, and audit evidence before delivery.

## Practice Boundaries

- Use structured output when downstream code must execute, validate, store, or audit model intent.
- Keep schemas, permissions, validators, retries, and audit rules outside the model output.
- Treat a DSL as a narrow contract for the workflow, not as a general replacement for application logic.
- Prefer deterministic validators for syntax, allowed fields, executable actions, and policy gates.
- Feed validator failures back into the harness loop when the workflow can safely retry.
- Track latency and verification cost for repeated structured-output shapes across the whole agent loop, not only at one model call.
- Do not trade away schema validation, permission checks, or auditability for faster drafted tool arguments or JSON payloads.
- Treat generated documents, spreadsheets, slide decks, web apps, and other delivered files as auditable artifacts, not only as chat answers.
- Require source traceability, connector-scope evidence, file-access boundaries, approval state, and validation checks before accepting a generated artifact.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Application harness patterns](application-harness-patterns.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [ai process layer and workflow state](ai-process-layer-and-workflow-state.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from the application harness source guidance on structured output, DSLs, and model-drafted executable artifacts.
- Maintained on 2026-07-07 with structured-output latency, drafter verification cost, and whole-loop validation guidance.
- Maintained on 2026-07-11 with artifact-producing agent boundaries for files, connector scope, approval state, and audit evidence.
