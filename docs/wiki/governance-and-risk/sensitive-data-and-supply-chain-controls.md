---
type: "Governance And Risk"
title: "Sensitive Data And Supply-Chain Controls"
description: "Sensitive data and supply-chain controls protect prompts, raw artifacts, tools, dependencies, models, and third-party source material."
tags: ["governance-and-risk"]
---

# Sensitive Data And Supply-Chain Controls

## Current Understanding

Sensitive data and supply-chain controls protect prompts, raw artifacts, tools, dependencies, models, and third-party source material. The local rule is to keep secrets, credentials, PII, company-internal content, proprietary source, and license-sensitive material out of prompts and public raw artifacts unless the human explicitly approves that use.

Package installs and third-party artifacts deserve explicit review because they can introduce vulnerable, malicious, unnecessary, or license-incompatible dependencies. The same supply-chain lens applies to model artifacts, training data, retrieved source collections, MCP servers, browser extensions, workflow plugins, and copied prompt or skill libraries. [HVE Core](../../../raw/processed/microsoft-hve-core.md) is useful as a source example because it exposes license, third-party notice, security, governance, and responsible-AI signals alongside reusable agent artifacts.

The [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) adds agent-configuration risk: coding-agent tool manifests, skills, MCP servers, tool descriptions, and editor or workspace connectors are supply-chain inputs. They need provenance, review, inventory, and change detection because prompt injection or malicious behavior can live in tool descriptions and reusable agent artifacts, not only in package code.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) add installation-source and runtime-security controls. Enterprise marketplace allowlists, MCP server review, plugin-source restrictions, prompt-injection screening for consumed dependencies, and credential brokering all treat agent tooling as part of the software supply chain. Product feature histories stay upstream; locally, no agent tool should become trusted merely because it is convenient to install.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) adds package-account and plugin-consent signals. Registry account safeguards, marketplace restrictions, project-settings plugin activation, and usage of recovery credentials all matter to agent-assisted package operations because a coding agent can trigger installs, dependency updates, or publication-adjacent workflows faster than a human reviewer can inspect them.

This page owns the local acceptance and routing rules. Broad provider security announcements, model catalogs, package ecosystem watchlists, and product-specific vulnerability tracking belong upstream unless a local approval rule depends on them.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) adds two supply-chain signals. Workflow actions from unverified sources and package-account compromise controls should feed local review gates for agent-generated CI, dependency, and install changes. Platform details stay upstream; locally, agents should not add actions or packages without provenance, lockfile, and risk review.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) reinforces data-control as a development-workflow gate. Source code, logs, code review material, internal docs, raw artifacts, and private context should be classified before they are sent to external models, hosted tools, browser agents, or third-party analysis surfaces. The local control is not product-specific; it is a rule that intelligence access cannot silently trade away data ownership, retention, or auditability.

The [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) and [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json) add dependency, extension, and sample-analysis signals. Agent-authored package installs, IDE extension use, MCP server metadata, malware samples, reverse-engineering artifacts, and tool-supplied sensitive records are all supply-chain or sensitive-data surfaces. The local acceptance rule is to review provenance, necessity, lockfiles, account security, data classification, and tool parameter leakage before an agent can install, publish, analyze, or exfiltrate through a connected tool.

The [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json) adds managed-setting, visual-context, and model-enablement signals. Enterprise plugin controls, bypass-permission modes, browser tools, model enablement policies, image and PDF attachments, and remote admin MCP servers are supply-chain or sensitive-data controls when they affect what an agent can see or do. The local rule is to review tool provenance, attachment sensitivity, retention terms, model approval, and action scope before enabling those surfaces for team workflows.

The [Deepsec clipping](../../../raw/processed/vercel-labsdeepsec Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents.md), [Just Bash clipping](../../../raw/processed/vercel-labsjust-bash Bash for Agents.md), and [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md) add supply-chain intake examples. Agent security scanners, virtual shell packages, chat adapters, state stores, and channel integrations should be reviewed for package provenance, sandbox claims, credential handling, network behavior, adapter permissions, and whether collaboration messages or repository content could leave the intended trust boundary.

The [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) and [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json) add sensitive-code and telemetry-capture controls. Before exporting agent traces or running a governed coding agent on sensitive repositories, teams should decide whether prompts, responses, tool content, session logs, screenshots, and debug logs can be retained, and should separate credentials from the sandbox that executes generated or delegated code.

The [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json) adds a slopsquatting dependency-control signal. Agent-generated package names, scaffolded install commands, and dependency updates should be treated as untrusted until the package exists in the intended registry, has expected provenance, matches project need, fits lockfile policy, and survives human or policy review.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) and [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json) add repository-source and runtime-separation signals. Public agent-onboarding snippets, unknown repository URLs, image or binary PR artifacts, and default-permission agent infrastructure should be treated as supply-chain inputs until source verification, install review, credential separation, logging, and blast-radius checks pass.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) adds dependency-cooldown, MCP trust, and PR-context signals. Routine AI-assisted dependency maintenance should preserve a waiting period or equivalent risk review for new package releases while still allowing urgent security updates through a faster path. MCP server trust prompts, configuration fingerprints, and PR context ingestion are supply-chain and data-boundary surfaces because they decide which code, metadata, and external services an agent can treat as trusted context.

The [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json) and [July 15 leaf update watch source](../../../raw/processed/2026-07-15/ai-dev-wiki-leaf-update-watch-2026-07-15T210218-0400.json) add instruction-file, repository-history, sandbox, and data-residency signals. Durable agent instruction files, cloned repository docs, symlink paths, git history, package installs, generated code execution, and coding-agent deployment location are supply-chain or sensitive-data surfaces. Security patch acceleration is useful only when validation, deployment, and disclosure gates keep pace with faster vulnerability discovery.

The [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json) adds secret-scanning and runner-egress signals. Secret alerts should preserve provider category, generic-versus-specific detector evidence, public exposure attribution, and webhook routing fields so agent-generated packages, generated scripts, and repository-history scans can be triaged without leaking the secret itself. CI jobs that run generated build scripts or dependency installs need runner-neutral egress review: hosted Linux, macOS, Windows, and third-party runners should all produce outbound-network evidence before jobs handle signing material, deployment credentials, or production-adjacent tokens.

The July 17 raw sources add portable-skill supply-chain evidence. The [topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) and [leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json) treat public skill registries, imported instruction bundles, generated skill files, tool-scope metadata, and poisoned registry paths as supply-chain inputs. Local adoption should pin source registries, record owner and version, review allowed tool scope, and preserve tamper-evident approval history before skills can alter agent authority.

The July 19-21 raw sources add generated-dependency, private-inference, and agentic-application risk signals. The [July 19 topic news collector source](../../../raw/processed/2026-07-19/ai-dev-wiki-topic-news-collector-2026-07-19T203449-0400.json) and [July 19 leaf update watch source](../../../raw/processed/2026-07-19/ai-dev-wiki-leaf-update-watch-2026-07-19T210231-0400.json) reinforce HalluSquatting and private-inference concerns: hallucinated package, repository, or skill names should be resolved against exact registries or URLs before clone or install actions, and proprietary code prompts need retention, training-use, jurisdiction, and approval review. The [July 21 leaf update watch source](../../../raw/processed/2026-07-21/ai-dev-wiki-leaf-update-watch-2026-07-21T210116-0400.json) maps OWASP agentic-application controls to goal constraints, untrusted retrieved content, per-agent identity, AIBOM provenance, sandboxed execution, behavioral monitoring, and kill switches across IDE, CLI, and PR workflows.

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) and [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json) add deterministic guardrail, sandbox-escape, SANDWORM_MODE, agentic incident, and AI-generated-code security evidence. Supply-chain controls should treat agent-authored commits like untrusted external contributions, enforce provenance and PR policy, model command side effects and repository-config writes, monitor package tokens and AI toolchains, and keep containment, egress, and package access outside model discretion.

The [July 25 topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json) adds agent-workstation and developer-toolchain evidence. AI-assisted development controls should cover developer machines, IDE extensions, package registries, CI/CD egress, pull requests, default branches, and fleet-wide incident checks because agents can accelerate both legitimate software changes and attacker movement across those surfaces.

The July 28 raw sources add malware-advisory and agent-configuration supply-chain evidence. The [topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json) treats malware-specific package alerts as distinct from CVE-style vulnerability alerts, while the [leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) reinforces that MCP registrations, dependency trees, CI workflows, and agent configuration files are persistent instruction and execution surfaces. Local dependency gates should review malware advisory type, registry provenance, lockfile impact, and generated install intent before accepting agent-authored package changes.

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
- Review managed plugin settings, bypass modes, browser tooling, visual attachments, model enablement, and remote MCP administration as supply-chain or data-control changes.
- Record retention and sensitivity decisions for screenshots, PDFs, architecture images, logs, and other multimodal context before they are sent to a hosted assistant.
- Review agent security scanners, virtual shell tools, chat adapters, state stores, and channel integrations before they enter a team agent workflow.
- Check whether security scans, chat-agent threads, and simulated shell examples expose repository content, credentials, collaboration messages, or sensitive findings outside the intended environment.
- Classify prompt, response, tool, screenshot, debug-log, and session-log content before exporting centralized agent telemetry.
- Keep credentials outside coding-agent sandboxes and use approval gates before generated code or delegated tools can touch sensitive files, networks, or dependencies.
- Prefer deny-by-default network access for sensitive-code agents until the needed endpoints and evidence requirements are explicit.
- Verify AI-proposed packages against registries, provenance, allowlists, lockfiles, and project need before accepting install commands or dependency edits.
- Escalate hallucinated or unknown package names as supply-chain risk rather than letting the agent search, install, or rename around the failure unaudited.
- Verify repository URLs, public setup snippets, and agent install instructions before allowing a coding agent to clone, install, configure, or execute them.
- Treat image and binary artifacts as possible instruction carriers when a downstream multimodal agent can read them; keep secrets and credentials outside that review path.
- Inventory agent frameworks, RAG stores, default permissions, logging, keys, runtime separation, and network reach before connecting them to codebases or enterprise data.
- Keep routine dependency-update automation subject to cooldown, provenance, lockfile, and release-health review while routing security fixes through explicit urgent-update gates.
- Treat MCP trust prompts, configuration fingerprints, PR context ingestion, and IDE extension updates as supply-chain or data-boundary decisions for agent workflows.
- Review repository instruction files, symlink targets, git history, package installs, and generated-code execution paths before autonomous agents treat them as trusted context or authority.
- Treat customer VPC, dedicated GPU, air-gapped, or hosted coding-agent deployment choices as data-residency and evidence-retention decisions.
- Keep validation, deployment, and disclosure gates explicit when AI-assisted security work accelerates vulnerability discovery or patch generation.
- Route secret-scanning alerts with detector category, attribution, verified-domain, and webhook evidence while keeping credential values out of prompts and raw artifacts.
- Require OS-neutral and provider-neutral runner egress evidence before generated scripts, dependency installs, or signing workflows can use sensitive credentials.
- Treat public skill registries, imported instruction bundles, generated skill files, and tool-scope metadata as supply-chain inputs until provenance, owner, version, trust status, approval history, and allowed authority are reviewed.
- Resolve AI-suggested package, repository, and skill names against exact registries, URLs, lockfiles, and approval evidence before clone, install, import, or scaffold actions.
- Review private-inference and hosted-agent paths for source retention, training-use terms, jurisdiction, reviewer access, approval, and auditability before proprietary code enters prompts.
- Pair agentic application controls with goal constraints, untrusted-content handling, AIBOM provenance, sandboxing, behavioral monitoring, and kill switches when agents can affect IDE, CLI, or pull-request workflows.
- Extend AI-assisted development supply-chain controls to agent workstations, IDE extensions, package registries, CI/CD egress, pull requests, default branches, and fleet-wide incident checks.
- Separate malware-specific dependency alerts from ordinary vulnerability alerts when reviewing agent-authored install, update, or lockfile changes.
- Treat MCP registrations, CI workflows, and agent configuration files as persistent supply-chain inputs that need provenance, integrity monitoring, scoped credentials, and review before agent use.

## Authoritative Sources

- [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json)
- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
- [July 25 topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json)
- [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
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
- [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json)
- [Deepsec clipping](../../../raw/processed/vercel-labsdeepsec Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents.md)
- [Just Bash clipping](../../../raw/processed/vercel-labsjust-bash Bash for Agents.md)
- [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)
- [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json)
- [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)
- [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json)
- [July 15 leaf update watch source](../../../raw/processed/2026-07-15/ai-dev-wiki-leaf-update-watch-2026-07-15T210218-0400.json)
- [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json)
- [July 19 topic news collector source](../../../raw/processed/2026-07-19/ai-dev-wiki-topic-news-collector-2026-07-19T203449-0400.json)
- [July 19 leaf update watch source](../../../raw/processed/2026-07-19/ai-dev-wiki-leaf-update-watch-2026-07-19T210231-0400.json)
- [July 21 leaf update watch source](../../../raw/processed/2026-07-21/ai-dev-wiki-leaf-update-watch-2026-07-21T210116-0400.json)
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

- Maintained on 2026-07-23 with deterministic guardrails, sandbox escapes, SANDWORM_MODE, untrusted AI-authored commit, package-token, egress, and containment guidance.
- Maintained on 2026-07-25 with agent-workstation, IDE extension, package registry, CI/CD egress, PR, default-branch, and fleet-incident supply-chain controls.
- Maintained on 2026-07-28 with malware-specific dependency alerts, MCP registration integrity, agent configuration, CI workflow, and lockfile review controls.
- Created on 2026-06-23 to separate sensitive-data, package-install, dependency, model-artifact, source, and licensing controls from the broader governance-controls page.
- Maintained on 2026-06-24 with agent skill, tool manifest, MCP server, and connector configuration supply-chain controls.
- Maintained on 2026-06-25 with marketplace allowlists, runtime agent-security checks, and credential-broker controls for agent tooling.
- Maintained on 2026-06-26 with package-account protection and plugin-consent controls for agent-enabled development environments.
- Maintained on 2026-06-27 with unverified workflow-action and package-account review gates for agent-generated changes.
- Maintained on 2026-06-28 with data-control gates for source, logs, reviews, and private development context.
- Maintained on 2026-07-01 with package, IDE extension, MCP metadata, malware-analysis, and tool-parameter controls for agent workflows.
- Maintained on 2026-07-01 with managed plugin settings, bypass modes, browser tools, visual attachments, model enablement, and remote admin MCP controls.
- Maintained on 2026-07-06 with scanner, virtual shell, chat adapter, state store, and collaboration-channel supply-chain checks.
- Maintained on 2026-07-08 with telemetry-content classification, credential-separated sensitive-code sandboxes, and deny-by-default network controls.
- Maintained on 2026-07-12 with slopsquatting dependency controls for AI-proposed package names, install commands, provenance, allowlists, and lockfiles.
- Maintained on 2026-07-13 with source verification, public setup-snippet review, binary artifact handling, and runtime-separation checks for agent infrastructure.
- Maintained on 2026-07-14 with dependency cooldown, MCP trust-validation, PR-context, and IDE extension update controls.
- Maintained on 2026-07-15 with instruction-file trust review, repository-history secret coverage, symlink/path checks, sandbox execution controls, patch validation, and data-residency review.
- Maintained on 2026-07-16 with secret-scanning routing fields and runner-neutral egress controls for generated build and deployment workflows.
- Maintained on 2026-07-17 with public skill registry, imported instruction bundle, generated skill, tool-scope, and poisoned registry supply-chain controls.
- Maintained on 2026-07-22 with HalluSquatting resolution, private-inference review, AIBOM provenance, untrusted-content, sandbox, monitoring, and kill-switch controls.
