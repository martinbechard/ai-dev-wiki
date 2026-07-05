---
type: "Retrieval And Tools"
title: "Code Retrieval Evidence Patterns"
description: "Code retrieval for AI-assisted development needs semantic search, exact repository evidence, and runtime truth."
tags: ["retrieval-and-tools"]
---

# Code Retrieval Evidence Patterns

## Current Understanding

Code retrieval for AI-assisted development needs semantic search, exact repository evidence, and runtime truth. The model only sees the files, snippets, command output, tool results, and history that the harness sends in the request, so retrieval choices shape what the model can safely claim.

Repository work should combine exact paths, symbols, tests, diffs, logs, and nearby call sites with broader semantic discovery. Semantic search is useful for finding likely neighborhoods, but build output, failing tests, stack traces, and runtime logs decide whether a claim matches the actual checkout.

This page owns repository retrieval practice. General context packaging is tracked in [context engineering for request packages](../prompt-and-instructions/context-engineering-for-request-packages.md), and document RAG quality is tracked in [RAG provenance ranking and chunking](rag-provenance-ranking-and-chunking.md).

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) reinforces exact repository exploration as part of AI review quality. File exploration tools such as exact text search, path globs, and file viewing are not incidental implementation details; they are evidence-producing steps that should be visible when a review or coding agent claims it inspected the relevant code.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) and [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) add retrieval-depth and engineering-memory signals. AI review should expose depth settings and repository exploration paths, while team memory should include decisions, review discussions, linked tickets, and cross-file dependencies instead of relying on commit history alone.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) adds a scoped-retrieval efficiency signal. Review and coding agents should avoid repository-wide context expansion when a targeted diff, symbol, test, and neighboring-call-site path can support the claim. Reduced context gathering is a quality control only when the resulting retrieval path remains inspectable.

The [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json) reinforces the same pattern for larger corpora. Search-backed retrieval should identify candidate files or passages, then the agent should read targeted evidence before making code, review, or documentation claims. Reading every available file is a scalability and provenance risk when search, facets, and exact paths can narrow the working set.

The [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json) adds a review-memory boundary. Broad codebase RAG is not always worth its maintenance cost for code review when agents can inspect the working tree directly. Retrieval earns its place when it supplies evidence that is hard to rediscover from current files, such as prior PR comments, repeated feedback, team decisions, and project-specific review memory.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) and [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json) reinforce dependency-aware review evidence. Recall-first review and security remediation workflows need enough repository, dependency graph, scanner, test, and runtime evidence to support cross-file findings without turning every review into an unauditable repository dump.

## Practice Boundaries

- Start with repository structure, exact filenames, symbols, and tests when the task changes code.
- Use semantic search to find candidate neighborhoods, then read the exact files and call sites before editing.
- Attach failing tests, compiler errors, logs, screenshots, and tool output when they affect the next action.
- Prefer current runtime evidence over plausible documentation when the two disagree.
- Carry unresolved evidence gaps into Open Questions instead of turning guesses into wiki claims.
- Keep broad product or model retrieval features upstream unless they change local repository practice.
- Make the retrieval path inspectable for review claims: which files, symbols, globs, searches, diffs, and neighboring call sites supported the finding.
- Capture decision history, review discussion, ticket context, and cross-file dependency evidence when they change review or implementation judgment.
- Prefer scoped retrieval paths for code review and repair, then record enough evidence for reviewers to see why broader repository expansion was unnecessary.
- Treat unnecessary context gathering as a cost and distraction risk when it does not add source evidence.
- Use search and metadata filters to narrow large repositories or document corpora before reading exact source files.
- Record the targeted reads that verified retrieved candidates so reduced context remains reviewable.
- Separate source-code retrieval from review-memory retrieval: current files should usually be inspected directly, while durable review history and team decisions need explicit memory capture.
- Measure retrieval value against review quality, latency, cost, maintenance load, and whether the evidence could have been recovered from ordinary repository tools.
- Include dependency graph, scanner output, test, and runtime evidence when review findings depend on cross-file or security-remediation risk.
- Keep recall-first and scan-to-merge retrieval paths auditable so broad detection does not hide unsupported source assumptions.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [context engineering for request packages](../prompt-and-instructions/context-engineering-for-request-packages.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json)
- [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json)

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
- Maintained on 2026-06-25 with explicit retrieval-path evidence for AI review and coding-agent claims.
- Maintained on 2026-06-26 with review-depth settings, repository exploration paths, and engineering-memory retrieval signals.
- Maintained on 2026-06-27 with scoped retrieval and context-gathering efficiency as review evidence controls.
- Maintained on 2026-07-01 with search-backed corpus narrowing, metadata filters, targeted reads, and reviewable reduced-context evidence.
- Maintained on 2026-07-03 with code-review memory boundaries and retrieval economics for prior review decisions.
- Maintained on 2026-07-04 with dependency-aware review retrieval and scan-to-merge evidence paths.
