# Context Engineering For Request Packages

## Current Understanding

Context engineering is the local practice of selecting project data, coding conventions, documentation, source labels, and verification expectations for a specific request. It is broader than prompt wording because it decides which evidence and rules the model can see while doing the work.

The request package should carry enough context for the model to act with less ambiguity without loading unrelated history. The AI-assisted coding deck frames repository understanding as request packaging, context assembly, retrieval, and verification evidence. The Hypervelocity Engineering source describes context engineering as supplying project data, conventions, and documentation so AI work becomes more accurate and can use smaller or task-specialized models.

The local boundary is practical: context engineering decides what to include, [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md) decide where stable guidance lives, and [request packages and file boundaries](request-packages-and-file-boundaries.md) decide how the selected material is labeled inside the request.

## Practice Boundaries

- Start from the task, then select the smallest source set that can support the decision.
- Prefer exact files, nearby call sites, failing assertions, logs, and recent diffs over broad repository dumps.
- Keep stable rules in durable instructions and load them by reference when the harness supports it.
- Trim stale conversation history and long logs so current evidence remains visible.
- Attach verification evidence to the next request when it changes the next action.
- Treat context selection as part of workflow design, not as a late prompt-writing detail.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Hypervelocity engineer source](../../../raw/processed/Hypervelocity engineer @edandersen.md)
- [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md)
- [request packages and file boundaries](request-packages-and-file-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [prompt-and-instructions](index.md)
- [retrieval-and-tools](../retrieval-and-tools/index.md)
- [verification-and-evals](../verification-and-evals/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold the request-package side of context engineering.
