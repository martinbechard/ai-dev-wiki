---
type: "Governance And Risk"
title: "Sensitive Data And Supply-Chain Controls"
description: "Sensitive data and supply-chain controls protect prompts, raw artifacts, tools, dependencies, models, and third-party source material."
tags: ["governance-and-risk"]
---

# Sensitive Data And Supply-Chain Controls

## Current Understanding

Sensitive data and supply-chain controls protect prompts, raw artifacts, tools, dependencies, models, and third-party source material. The local rule is to keep secrets, credentials, PII, company-internal content, proprietary source, and license-sensitive material out of prompts and public raw artifacts unless the human explicitly approves that use.

Package installs and third-party artifacts deserve explicit review because they can introduce vulnerable, malicious, unnecessary, or license-incompatible dependencies. The same supply-chain lens applies to model artifacts, training data, retrieved source collections, MCP servers, browser extensions, workflow plugins, and copied prompt or skill libraries. HVE Core is useful as a source example because it exposes license, third-party notice, security, governance, and responsible-AI signals alongside reusable agent artifacts.

The [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) adds agent-configuration risk: coding-agent tool manifests, skills, MCP servers, tool descriptions, and editor or workspace connectors are supply-chain inputs. They need provenance, review, inventory, and change detection because prompt injection or malicious behavior can live in tool descriptions and reusable agent artifacts, not only in package code.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) add installation-source and runtime-security controls. Enterprise marketplace allowlists, MCP server review, plugin-source restrictions, prompt-injection screening for consumed dependencies, and credential brokering all treat agent tooling as part of the software supply chain. Product feature histories stay upstream; locally, no agent tool should become trusted merely because it is convenient to install.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) adds package-account and plugin-consent signals. Registry account safeguards, marketplace restrictions, project-settings plugin activation, and usage of recovery credentials all matter to agent-assisted package operations because a coding agent can trigger installs, dependency updates, or publication-adjacent workflows faster than a human reviewer can inspect them.

This page owns the local acceptance and routing rules. Broad provider security announcements, model catalogs, package ecosystem watchlists, and product-specific vulnerability tracking belong upstream unless a local approval rule depends on them.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) adds two supply-chain signals. Workflow actions from unverified sources and package-account compromise controls should feed local review gates for agent-generated CI, dependency, and install changes. Platform details stay upstream; locally, agents should not add actions or packages without provenance, lockfile, and risk review.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) reinforces data-control as a development-workflow gate. Source code, logs, code review material, internal docs, raw artifacts, and private context should be classified before they are sent to external models, hosted tools, browser agents, or third-party analysis surfaces. The local control is not product-specific; it is a rule that intelligence access cannot silently trade away data ownership, retention, or auditability.

The [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) and [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json) add dependency, extension, and sample-analysis signals. Agent-authored package installs, IDE extension use, MCP server metadata, malware samples, reverse-engineering artifacts, and tool-supplied sensitive records are all supply-chain or sensitive-data surfaces. The local acceptance rule is to review provenance, necessity, lockfiles, account security, data classification, and tool parameter leakage before an agent can install, publish, analyze, or exfiltrate through a connected tool.

## Practice Boundaries

- Keep secrets, credentials, PII, and company-internal material outside prompts, raw artifacts, screenshots, logs, and public source collectors unless explicitly approved.
- Review package installs for necessity, provenance, maintenance health, security posture, and license fit before accepting them.
- Vet model artifacts, retrieved data, source collections, MCP servers, workflow plugins, and copied prompt libraries before allowing them into the local workflow.
- Preserve license and third-party notice signals when source artifacts are used to shape local instructions, prompts, skills, or governance pages.
- Use access controls on model endpoints, source data, tool servers, and stored artifacts when sensitive information may be present.
- Record unresolved source or license uncertainty as an open question instead of converting it into an implied approval.
- Inventory agent skills, tool manifests, MCP servers, plugins, and connector descriptions as development supply-chain artifacts.
- Review changes to agent configuration with the same seriousness as changes to dependencies or workflow automation.
- Restrict extension, plugin, and marketplace sources for agent-enabled developer environments when those tools can influence code, credentials, or delivery systems.
- Keep reusable secrets out of agent context; prefer brokers, scoped connectors, or request-bound credential exchange patterns.
- Treat package-publishing accounts, recovery credentials, project-settings plugins, and dependency-update workflows as high-impact supply-chain surfaces.
- Block or escalate workflow actions from unverified sources when an agent edits CI or automation files.
- Require provenance, lockfile, account-security, and necessity review before accepting agent-proposed package installs or dependency updates.
- Classify source, logs, review material, internal docs, raw artifacts, and private context before sharing them with external AI services or hosted tools.
- Reject tool paths that obscure data retention, ownership, or auditability for development context unless the human explicitly accepts the risk.
- Review IDE extensions, MCP tool metadata, package registries, malware-analysis artifacts, and tool parameters as supply-chain or sensitive-data surfaces when agents can read or act through them.
- Apply DLP, source classification, and human approval to tool arguments that could carry sensitive records out through otherwise approved actions.

## Authoritative Sources

- [OWASP LLM vulnerabilities source](../../../raw/processed/OWASP's Top 10 Ways to Attack LLMs AI Vulnerabilities Exposed.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json)
- [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json)
- [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [source-workflows](../source-workflows/index.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance controls for agents](governance-controls-for-agents.md)
- [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [source-workflows](../source-workflows/index.md)
- [retrieval-and-tools](../retrieval-and-tools/index.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to separate sensitive-data, package-install, dependency, model-artifact, source, and licensing controls from the broader governance-controls page.
- Maintained on 2026-06-24 with agent skill, tool manifest, MCP server, and connector configuration supply-chain controls.
- Maintained on 2026-06-25 with marketplace allowlists, runtime agent-security checks, and credential-broker controls for agent tooling.
- Maintained on 2026-06-26 with package-account protection and plugin-consent controls for agent-enabled development environments.
- Maintained on 2026-06-27 with unverified workflow-action and package-account review gates for agent-generated changes.
- Maintained on 2026-06-28 with data-control gates for source, logs, reviews, and private development context.
- Maintained on 2026-07-01 with package, IDE extension, MCP metadata, malware-analysis, and tool-parameter controls for agent workflows.
