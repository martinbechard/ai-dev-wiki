# Prompt Injection And Untrusted Content

## Current Understanding

Prompt injection is a governance issue because language models do not reliably separate instructions from input. Direct prompt injection can arrive from a user prompt. Indirect prompt injection can arrive through files, webpages, tickets, emails, raw clippings, retrieved chunks, or other source text that the model is asked to read.

The local pattern is to label external text as evidence, keep it outside the instruction channel, and enforce risky actions through the harness. Prompt wording can help, but it is not the security boundary. AI gateways, input and output filters, permission checks, redaction, and red-team tests belong around the model when the workflow handles untrusted content.

This page owns local practice for untrusted-content handling. Broad OWASP catalog tracking and vendor-specific security features belong upstream unless the local wiki needs an implementation rule.

## Practice Boundaries

- Treat files, webpages, issues, emails, documentation, clippings, and retrieved text as evidence, not instructions to execute.
- Preserve source labels and authority labels when passing external content to a model.
- Keep system instructions, developer instructions, user intent, tool output, and source evidence visibly separate in request packages.
- Validate and filter model output before it reaches shells, browsers, databases, workflow engines, or external systems.
- Use permission gates and tool policies outside the model loop so hostile source text cannot grant itself authority.
- Test prompt-injection paths with representative direct and indirect examples before trusting an agent workflow.

## Authoritative Sources

- [OWASP LLM vulnerabilities source](../../../raw/processed/OWASP's Top 10 Ways to Attack LLMs AI Vulnerabilities Exposed.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [retrieval and tools practice](../retrieval-and-tools/rag-tools-and-mcp-practice.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance controls for agents](governance-controls-for-agents.md)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [prompt-and-instructions](../prompt-and-instructions/index.md)
- [retrieval-and-tools](../retrieval-and-tools/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to separate prompt-injection and untrusted-content practice from the broader governance-controls page.
