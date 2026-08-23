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

The [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json) adds enterprise structured-output evidence. Structured extraction and drafter flows should preserve schemas, citations, refusal handling, partial-output recovery, and deterministic downstream checks so generated records can be reviewed and retried instead of trusted as prose.

The [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json) reinforces structured output as a layered contract:

- JSON mode, schema-conforming output, business-valid output, and authorized action are separate gates.
- Provider-native structured output or tool-call schemas do not remove deterministic validators.
- Refusal handling, truncation handling, and post-validation authorization checks remain harness responsibilities.

The [August 22 leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json) sharpens the same contract with a source-carrier boundary:

- Valid JSON, schema-conforming objects, business-valid objects, and authorized actions are separate gates.
- Source artifacts such as PDFs, filings, resumes, connected-app records, or hidden formatted text can carry machine-readable instructions a human reviewer may not see.
- Structured extraction should preserve provenance, hidden-content inspection state, refusal or retry state, and downstream authorization evidence before an artifact becomes an action.

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
- Treat structured outputs as validation contracts: schema adherence is useful only when paired with retries, refusal handling, partial-output recovery, provenance fields, and downstream deterministic checks.
- Use structured extraction and drafting to preserve source attribution and reviewable fields rather than hiding uncertain generation behind prose.
- Keep citations, confidence fields, refusal states, and partial-output markers in generated records when enterprise workflows require review or retry.
- Separate syntactic JSON validity, schema conformance, business invariants, and authorization; do not let provider schema features stand in for domain validation or tool-permission gates.
- Inspect source artifacts for hidden, formatted, copied, or machine-readable instruction content before structured extraction results can trigger writes, publication, email, commits, or connected-app actions.
- Preserve provenance, validation stage, business-rule verdict, authorization state, retry count, and refusal or truncation handling as fields that downstream code can audit.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Application harness patterns](application-harness-patterns.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 22 topic news collector source](../../../raw/processed/2026-07-22/ai-dev-wiki-topic-news-collector-2026-07-22T203140-0400.json)
- [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json)
- [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json)
- [August 22 leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json)

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
- Maintained on 2026-07-22 with structured-output validation contracts, recovery handling, provenance fields, and deterministic downstream checks.
- Maintained on 2026-07-24 with citation, confidence, refusal-state, partial-output, review, and retry guidance.
- Maintained on 2026-08-21 with layered JSON, schema, business-validation, refusal, truncation, and authorization gates.
- Maintained on 2026-08-22 with hidden source-carrier inspection, provenance, validation-stage, and authorization-state evidence.
