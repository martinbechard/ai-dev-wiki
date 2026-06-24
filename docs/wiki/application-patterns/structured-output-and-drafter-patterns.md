# Structured Output And Drafter Patterns

## Current Understanding

Structured output makes model intent executable by giving deterministic code a schema, DSL, or typed artifact to validate. The drafter pattern uses the model for fuzzy translation, then lets normal code validate, execute, retry, persist, and audit the result.

This pattern fits filters, transformations, workflow steps, UI changes, business actions, and tool arguments where plain prose would be too ambiguous for downstream execution. The model drafts the artifact; the harness owns schema validation, permission checks, execution behavior, and failure handling.

## Practice Boundaries

- Use structured output when downstream code must execute, validate, store, or audit model intent.
- Keep schemas, permissions, validators, retries, and audit rules outside the model output.
- Treat a DSL as a narrow contract for the workflow, not as a general replacement for application logic.
- Prefer deterministic validators for syntax, allowed fields, executable actions, and policy gates.
- Feed validator failures back into the harness loop when the workflow can safely retry.

## Authoritative Sources

- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Application harness patterns](application-harness-patterns.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)

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
