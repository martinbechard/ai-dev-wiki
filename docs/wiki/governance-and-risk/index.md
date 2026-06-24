# Governance And Risk

## Current Understanding

Governance and risk covers the boundaries that keep AI-assisted development accountable: permissions, approvals, secrets, audit logs, prompt injection, package-install risk, privacy, licensing, human acceptance, source limits, and cost controls.

This topic owns local operating rules and risk patterns. Provider security announcements, product features, model risk claims, and broad ecosystem security catalogs stay upstream unless the local wiki needs a practice decision, approval point, implementation boundary, or evaluation criterion.

## Governance Leaf Pages

- [governance-controls-for-agents.md](governance-controls-for-agents.md) records the overall local agent-control model and links the specific control leaves.
- [prompt-injection-and-untrusted-content.md](prompt-injection-and-untrusted-content.md) records how untrusted input, retrieved text, files, webpages, tickets, and clippings stay separated from live instructions.
- [agent-governance-infrastructure.md](agent-governance-infrastructure.md) records identity, authorization, monitoring, audit, policy enforcement, and human accountability as infrastructure concerns.
- [sensitive-data-and-supply-chain-controls.md](sensitive-data-and-supply-chain-controls.md) records secret, PII, package-install, dependency, model, source, licensing, and third-party artifact controls.
- [ai-assisted-security-repair-gates.md](ai-assisted-security-repair-gates.md) records validation, maintainer consultation, patching, tests, CI, and disclosure gates for agent-assisted security work.
- [prototype-to-cloud-promotion-gates.md](prototype-to-cloud-promotion-gates.md) records the security boundary between local prototypes and hosted, shared, or data-bearing software.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [OWASP LLM vulnerabilities source](../../../raw/processed/OWASP's Top 10 Ways to Attack LLMs AI Vulnerabilities Exposed.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [federation.md](../federation.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [prompt-and-instructions](../prompt-and-instructions/index.md)
- [retrieval-and-tools](../retrieval-and-tools/index.md)
- [application-patterns](../application-patterns/index.md)
- [adoption-and-operating-model](../adoption-and-operating-model/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 as the local owner for AI-assisted development governance and risk.
- Split on 2026-06-23 into durable governance leaves for prompt-injection handling, governance infrastructure, and sensitive data or supply-chain controls.
- Maintained on 2026-06-23 to add security repair and prototype promotion gates from public AI-assisted development security sources.
