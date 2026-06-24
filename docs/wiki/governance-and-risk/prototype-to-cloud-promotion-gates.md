# Prototype To Cloud Promotion Gates

## Current Understanding

Prototype-to-cloud promotion gates control when AI-assisted or vibe-coded local software becomes hosted, shared, or data-bearing software. The local pattern is that an app can move from personal prototype to public or team-facing deployment only after ownership, data sensitivity, authentication, threat model, dependency provenance, and repeatable verification have been checked.

The [vibe coding security source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) warns that local prototypes can become risky when they are hosted, shared, or connected to personal or sensitive data. Broad media, product, and standards coverage belongs upstream; this page keeps the local promotion workflow.

Promotion is a boundary change, not a cosmetic deployment step. An agent can help inspect code, generate tests, and draft fixes, but a human must approve the exposure level, data handling, and residual risk before the app reaches users or cloud infrastructure.

## Practice Boundaries

- Identify whether the app remains local, becomes shared internally, becomes public, or handles sensitive data.
- Require a threat-model pass before hosting agent-written or agent-modified software that accepts input, stores data, authenticates users, or calls external services.
- Review authentication, authorization, secret handling, dependency provenance, logging, and data retention before deployment.
- Inspect agent skills, plugins, MCP servers, generated dependencies, and copied code before trusting the promoted workflow.
- Rerun security-focused review after agent-written patches, not only before the first deployment.
- Keep promotion evidence in the handoff so the owner can see what was checked and what remains unresolved.

## Authoritative Sources

- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [delegated coding handoffs](../agent-workflows/delegated-coding-handoffs.md)
- [verification tax and acceptance gates](../verification-and-evals/verification-tax-and-acceptance-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from public source guidance on security risks when AI-assisted prototypes become hosted, shared, or data-bearing applications.
