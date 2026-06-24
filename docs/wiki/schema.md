# Wiki Schema

The wiki is a maintained synthesis layer. It summarizes and links project knowledge but does not replace authoritative sources.

## Authority Order

1. Code and tests describe actual behavior.
2. Functional specifications and requirements describe intended behavior.
3. AGENTS.md, README files, and procedure files describe workflow obligations.
4. Defect and feature backlog files describe tracked work. Status headings or explicit status fields determine whether an item is open, fixed, completed, or otherwise closed.
5. Architecture and plan documents describe design intent.
6. Help, RAG, or generated documentation describes the current documentation and retrieval surface.
7. Wiki pages summarize and navigate the above sources.

## Topic Page Sections

Topic pages should include:

```markdown
# Topic Name

## Current Understanding

## Authoritative Sources

## Related Code

## Related Tests

## Related Backlog Items

## Related Wiki Pages

## Open Questions

## Maintenance Notes
```

## Maintenance Rules

- Update the wiki when a task changes current behavior, intended behavior, workflow obligations, backlog state, or the meaning of a project concept.
- Prefer granular pages over monolithic pages.
- Use topic folders with index.md hub pages when related concepts, providers, components, snapshots, workflows, or decisions belong together.
- Use the local topic folders for downstream practice. The accepted roots are context-architecture, source-workflows, prompt-and-instructions, agent-workflows, coding-practices, retrieval-and-tools, verification-and-evals, application-patterns, governance-and-risk, and adoption-and-operating-model.
- When processing raw source files, create or update durable entity leaf pages for products, companies, models, frameworks, techniques, protocols, standards, workflows, notable features, and security issues mentioned in the source.
- If a raw source does not explain a named entity enough for a useful leaf, use focused research and cite the sources.
- Create monthly development digests under docs/wiki/digests. Keep each digest entry to at most three lines and link to the entity leaves that hold the details.
- Keep dated research, news, meeting notes, raw-source synthesis, and migration history as leaf pages under durable topic folders.
- After raw files are fully processed into entity leaves and the monthly digest, move them under raw/processed and update wiki source links to the processed path.
- Mention local files and wiki pages as Markdown links, not as bare filenames or paths.
- Prefer contextual links in the relevant explanation. Use Related Wiki Pages only when a short linked cross-reference adds navigation value.
- Keep steady-state explanations free of historical comparison unless the page is documenting a migration or maintenance note.
- Preserve unresolved contradictions in Open Questions.
- Review unresolved questions with python3 ~/.codex/skills/project-wiki/scripts/wiki_ops.py questions. Ask one question at a time, update the wiki from the answer, rerun questions to confirm the item is gone, then run lint.
- Never invent source paths, test coverage, backlog status, or fallback behavior.
- For one-way wiki federation, search the upstream topic index before creating local entity leaves. Link upstream entity pages and keep local pages focused on the downstream practice, workflow, governance, or adoption lens.
- Public update feeds run source-first. Topic collectors and leaf update watches save raw artifacts only; the raw project-wiki monitor owns wiki page refresh, digest updates, lint, and processed-source moves.
- Do not schedule duplicate feeds for upstream-owned companies, models, products, agentic frameworks, MCP servers, general developer tools, or broad techniques. Local feeds should watch practice, workflow, evaluation, governance, adoption, and implementation patterns.
- Keep local source artifacts in [raw](../../raw), fully processed source artifacts in [raw/processed](../../raw/processed), human-saved source notes in [Clippings](../../Clippings), and repository-local wiki helper scripts in [scripts](../../scripts).
- During ingest, normalize synonyms and aliases into the best durable page, factor common ideas into the page that owns the shared concept, keep source-specific ideas attributed to their source, and preserve unresolved conflicting ideas as Open Questions.
