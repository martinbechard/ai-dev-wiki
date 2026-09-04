---
type: "Governance And Risk"
title: "Prototype To Cloud Promotion Gates"
description: "Prototype-to-cloud promotion gates control when AI-assisted or vibe-coded local software becomes hosted, shared, or data-bearing software."
tags: ["governance-and-risk"]
---

# Prototype To Cloud Promotion Gates

## Current Understanding

Prototype-to-cloud promotion gates control when AI-assisted or vibe-coded local software becomes hosted, shared, or data-bearing software. The local pattern is that an app can move from personal prototype to public or team-facing deployment only after ownership, data sensitivity, authentication, threat model, dependency provenance, and repeatable verification have been checked.

The [vibe coding security source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) warns that local prototypes can become risky when they are hosted, shared, or connected to personal or sensitive data. Broad media, product, and standards coverage belongs upstream; this page keeps the local promotion workflow.

Promotion is a boundary change, not a cosmetic deployment step. An agent can help inspect code, generate tests, and draft fixes, but a human must approve the exposure level, data handling, and residual risk before the app reaches users or cloud infrastructure.

The [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json) and [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) add sensitive-code and execution-security signals. Promotion should require sandbox, network, credential, audit, approval, and provenance checks before coding agents work on production-like repositories, sensitive code, or hosted systems.

The [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) adds production-agent readiness evidence. Promotion should prove durable execution, checkpoint recovery, scoped access, component identity, runtime containment, complete activity logging, behavior baselines, and memory/source quarantine before a prototype or agent workflow is trusted in cloud, enterprise, or externally reachable environments.

The August 28 and 29 raw sources add prototype-to-deployment trust evidence. The [topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) records an accelerator-style prototype-to-product signal and managed coding-agent policy controls, while the [leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json) records production AI-generated-code gates and durable runtime readiness. Locally, promotion should require user trust, deployment readiness, retention and billing review, sandbox scope, review depth, rollback, and post-launch verification.

The September 3 raw sources add governed deployment and data-agent promotion evidence:

- The [leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json) reinforces ERP rule validation, approval thresholds, revocation, workspace isolation, least privilege, SIEM export, and before-go-live validation.
- The [topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json) supports mediated deployment execution through scoped access, policy-as-code guardrails, permissions, and audit logging.

## Practice Boundaries

- Identify whether the app remains local, becomes shared internally, becomes public, or handles sensitive data.
- Require a threat-model pass before hosting agent-written or agent-modified software that accepts input, stores data, authenticates users, or calls external services.
- Review authentication, authorization, secret handling, dependency provenance, logging, and data retention before deployment.
- Inspect agent skills, plugins, MCP servers, generated dependencies, and copied code before trusting the promoted workflow.
- Rerun security-focused review after agent-written patches, not only before the first deployment.
- Keep promotion evidence in the handoff so the owner can see what was checked and what remains unresolved.
- Require sandbox boundaries, deny-by-default network posture, credential separation, session audit evidence, and human approval before promoting sensitive-code agent workflows.
- Include execution-boundary hardening in promotion criteria when an agent can run setup commands, generated code, or delegated tools.
- Require checkpoint recovery, component identity, activity logging, behavior baselines, memory quarantine, and containment evidence before promotion to standing production or cloud-agent operation.
- Require mediated deployment execution, policy-as-code guardrails, approval thresholds, revocation controls, workspace isolation, least privilege, SIEM export, and before-go-live validation when an agent can affect cloud, ERP, or enterprise data.

## Authoritative Sources

- [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json)
- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [September 3 leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json)
- [September 3 topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json)

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

- Maintained on 2026-08-29 with prototype-to-product trust, retention, billing, sandbox, review-depth, rollback, and post-launch verification gates.
- Created on 2026-06-23 from public source guidance on security risks when AI-assisted prototypes become hosted, shared, or data-bearing applications.
- Maintained on 2026-07-08 with sensitive-code sandbox, network, credential, audit, approval, and execution-boundary promotion checks.
- Maintained on 2026-08-15 with durable execution, checkpoint recovery, scoped access, component identity, runtime containment, activity logging, behavior-baseline, and memory-quarantine promotion gates.
- Maintained on 2026-09-03 with mediated deployment, policy-as-code, ERP rule validation, approval thresholds, revocation, workspace isolation, least privilege, SIEM export, and before-go-live validation gates.
