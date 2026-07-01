---
type: "Governance And Risk"
title: "Governance Controls For Agents"
description: "AI-assisted development and AI application features need boundaries in the harness. The local control model treats prompts as guidance and treats harness rules as enforcement."
tags: ["governance-and-risk"]
---

# Governance Controls For Agents

## Current Understanding

AI-assisted development and AI application features need boundaries in the harness. The local control model treats prompts as guidance and treats harness rules as enforcement. Permissions, approval points, secret handling, audit logs, prompt-injection resistance, package-install policy, source privacy, licensing review, cost controls, and human acceptance sit around model output rather than inside model wording alone.

Agents expand the attack surface because they combine generated text, retrieved content, tool calls, dependency installs, and credential-adjacent workflows. The local rule is to preserve source boundaries, least privilege, explicit authorization, visible approval points, and audit evidence.

Provider security announcements and product feature catalogs belong upstream. This page owns the local practice implications.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) reinforce that controls need to cover the full agent operating surface: installation sources, tool catalogs, MCP trust boundaries, non-human identity, credential exposure, shadow AI, runtime filtering, red teaming, and audit trails. Product-specific controls from GitHub, Snyk, and governance vendors remain upstream-owned unless they define a local acceptance rule.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) and [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) add policy-surface evidence for model enablement, plugin consent, marketplace restrictions, permission-denial transcripts, runner controls, package-account protection, and deterministic agent configuration. The local rule is to keep these as enforceable controls around the agent loop, with auditable evidence for why a tool, model, environment, or package action was allowed.

The [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json) reinforces that agent governance needs deterministic guardrails, runtime policy enforcement, inherited-permission review, observability, audit trails, escalation rules, and human oversight. The control boundary should cover both coding-agent workflows and enterprise agents that act through existing user interfaces or connected tools.

The detailed control leaves are:

- [prompt-injection-and-untrusted-content.md](prompt-injection-and-untrusted-content.md) owns direct and indirect prompt-injection handling, source labels, and untrusted-content boundaries.
- [agent-governance-infrastructure.md](agent-governance-infrastructure.md) owns identity, authorization, allowed actions, monitoring, audit, policy enforcement, and human accountability chains.
- [sensitive-data-and-supply-chain-controls.md](sensitive-data-and-supply-chain-controls.md) owns secrets, PII, package installs, dependencies, model or source artifacts, licensing, and third-party notices.

## Practice Boundaries

- Keep secrets, credentials, PII, and company-internal content outside prompts and raw source artifacts unless the human explicitly approves that use.
- Treat external source text as untrusted evidence and route prompt-injection controls through [prompt-injection-and-untrusted-content.md](prompt-injection-and-untrusted-content.md).
- Require approval or policy gates for actions that affect files, network services, dependencies, credentials, external systems, or production-like state.
- Log tool calls and materially important model-assisted actions when the workflow needs auditability, accountability, or incident review.
- Evaluate package installs, model artifacts, data sources, and third-party content for necessity, provenance, maintenance, security, and license fit before accepting them.
- Keep human intent and acceptance explicit even when an agent performs implementation work.
- Validate model outputs before they reach browsers, shells, databases, workflow engines, or other execution surfaces.
- Constrain agent tools, plugins, and external systems through the infrastructure boundaries in [agent-governance-infrastructure.md](agent-governance-infrastructure.md).
- Rate-limit, budget, and monitor expensive model operations to reduce denial-of-service and denial-of-wallet exposure.
- Treat tool installation, plugin marketplaces, MCP server onboarding, and connector authorization as governance decisions, not only developer convenience steps.
- Use runtime security checks, red-team cases, and audit trails to validate whether prompt-level rules are enforced by the surrounding system.
- Require evidence for model enablement, plugin installation consent, marketplace allowlists, runner access, and package-affecting actions when those surfaces can change software delivery risk.
- Check inherited permissions, stale credentials, escalation paths, and audit evidence before allowing autonomous or semi-autonomous agents to act.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [OWASP LLM vulnerabilities source](../../../raw/processed/OWASP's Top 10 Ways to Attack LLMs AI Vulnerabilities Exposed.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [retrieval and tools practice](../retrieval-and-tools/rag-tools-and-mcp-practice.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [adoption operating agreements](../adoption-and-operating-model/adoption-operating-agreements.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from local source guidance on agent boundaries, package-install risk, security, and human accountability.
- Updated on 2026-06-23 with OWASP LLM risk mapping, infrastructure governance boundaries, and HVE Core licensing and responsible AI signals.
- Split on 2026-06-23 so recurring governance controls live in focused leaves while this page keeps the local agent-control model.
- Maintained on 2026-06-25 with full-surface agent controls for installation, MCP onboarding, connector authorization, runtime checks, red teaming, and audit evidence.
- Maintained on 2026-06-26 with model-policy, plugin-consent, marketplace, runner, package-account, and deterministic configuration controls.
- Maintained on 2026-06-29 with inherited-permission checks, runtime enforcement, escalation, and audit-control evidence.
