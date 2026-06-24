# Code Retrieval Evidence Patterns

## Current Understanding

Code retrieval for AI-assisted development needs semantic search, exact repository evidence, and runtime truth. The model only sees the files, snippets, command output, tool results, and history that the harness sends in the request, so retrieval choices shape what the model can safely claim.

Repository work should combine exact paths, symbols, tests, diffs, logs, and nearby call sites with broader semantic discovery. Semantic search is useful for finding likely neighborhoods, but build output, failing tests, stack traces, and runtime logs decide whether a claim matches the actual checkout.

This page owns repository retrieval practice. General context packaging is tracked in [context engineering for request packages](../prompt-and-instructions/context-engineering-for-request-packages.md), and document RAG quality is tracked in [RAG provenance ranking and chunking](rag-provenance-ranking-and-chunking.md).

## Practice Boundaries

- Start with repository structure, exact filenames, symbols, and tests when the task changes code.
- Use semantic search to find candidate neighborhoods, then read the exact files and call sites before editing.
- Attach failing tests, compiler errors, logs, screenshots, and tool output when they affect the next action.
- Prefer current runtime evidence over plausible documentation when the two disagree.
- Carry unresolved evidence gaps into Open Questions instead of turning guesses into wiki claims.
- Keep broad product or model retrieval features upstream unless they change local repository practice.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [context engineering for request packages](../prompt-and-instructions/context-engineering-for-request-packages.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [retrieval-and-tools](index.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold code retrieval evidence practice apart from document RAG and tool execution.
