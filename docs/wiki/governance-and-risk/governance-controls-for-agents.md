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

The [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json) adds shadow-agent and destructive-command controls. Local governance should inventory developer-side agents and MCP connections, capture audit evidence for tool invocation and data access, and treat recursive deletion, cleanup, quoting-sensitive shell operations, and path-crossing commands as a higher-risk action class. User-generated incident reports should be used only for the control lesson, without copying personal details.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) and [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json) add executable-compliance and governed-semantics signals. Agent governance should turn recurring compliance rules into automated pull-request checks where possible, and data-agent workflows should rely on governed semantic definitions, source truth, and execution monitoring rather than policy prose alone.

The [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json) reinforces compliance and data-boundary controls for AI review. Source-code location, data residency, intellectual-property exposure, audit controls, air-gapped operation, and private-cloud deployment can decide whether a review agent is usable before quality is evaluated. Compliance-as-code belongs in pull-request checks when rules are stable enough to test.

The [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) adds desktop-agent enablement and spend-surface controls. Broad product details remain upstream-owned, but locally a rollout must capture who can use the desktop agent, which BYOK or organization policy applies, which budgets follow team membership, and which billing or usage API produces audit evidence after preview surfaces retire.

The [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) adds managed policy, telemetry, review-dismissal, and sensitive-code harness signals. Locally, coding-agent controls should distinguish prompt or tool-content capture from metadata telemetry, push editor and CLI policy through managed device or server settings where available, and treat review-dismissal authority as separate from the ability to request an agent repair.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) and [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json) add runtime-enforcement, shared-agent-runtime, and untrusted-repository signals. Locally, coding-agent governance should treat admin-enabled model access, code-enabled managed runtimes, IDE session forensics, shadow-AI inventory, and untrusted dependency review as control-plane decisions with disposable execution boundaries and auditable policy evidence.

The [GitLost clipping](../../../raw/processed/GitLost is a dream come true for anyone who likes to jailbreak LLMs.md) adds a source-to-output control lesson for GitHub-style agentic workflows. A workflow that reads attacker-writable issue content, holds private repository access, and can post public comments needs minimum viable permissions, public-output restrictions, and disclosure checks before model behavior is considered. Guardrails that ask the model not to reveal private data are not enough when the tool graph permits retrieval and publication in one run.

The July 12 raw sources add three control refinements. The [topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json) reinforces prompt-injection, slopsquatting, LLM gateway, and leader-governance controls. The [leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json) reinforces task-scoped access, privileged-action visibility, centralized policy, emergency pause, and per-tool audit controls.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) and [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json) add AI-authored-code traceability, regulated lifecycle controls, and cross-boundary visibility. Local governance should record where AI-generated code enters, which policies and tests applied, what issues were found, how remediation was verified, and who owns agents that cross vendor, contractor, or internal-system boundaries.

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
- Inventory shadow agents, local MCP servers, connector grants, and developer-side tool paths that can bypass centrally managed visibility.
- Require command previews, normalized working directories, path-containment checks, backups or restore points, and explicit approval before destructive file operations.
- Capture who invoked which agent tool, what data or repository scope it touched, and which policy allowed or blocked the action.
- Encode recurring compliance requirements as automated checks when they can be tested at pull-request time.
- Require governed semantic definitions, source-truth labels, and execution monitoring before agents retrieve or act on business metrics.
- Treat source-code location, data residency, auditability, and air-gapped operation as acceptance gates for AI code review in regulated environments.
- Prefer executable pull-request policy checks for stable compliance requirements instead of relying on manual audit notes after merge.
- Treat desktop-agent plan access, BYOK policy, cost-center membership, and usage-reporting API coverage as governed rollout controls.
- Manage editor, CLI, plugin, marketplace, permission-mode, telemetry, and model settings centrally when the agent can affect shared code or policy evidence.
- Separate who may delegate a repair to an agent from who may dismiss human or automated review gates.
- Decide whether prompt, response, and tool content can enter telemetry streams before enabling centralized traces.
- Treat governed sensitive-code execution as a control bundle: deny-by-default networking, credential separation, sandboxing, human approvals, and per-session audit logs.
- Treat model enablement, session forensics, code-enabled managed runtimes, and shadow-AI discovery as governed rollout controls when agents can change code or execute code.
- Require disposable workspaces, constrained commands, and deterministic scanner evidence before autonomous agents inspect untrusted repositories or third-party dependencies.
- For issue-triggered agents, minimize repository scope, separate private-data reads from public posting, and require policy evidence before any agent-authored response can disclose retrieved content.
- Gate package installs, dependency edits, public replies, gateway routing, and privileged tool calls through deterministic policy evidence rather than model assurances.
- Review leader-facing governance literacy, evaluation evidence, and reliability assumptions before expanding agentic SDLC workflows beyond pilots.
- Treat AI-authored code as an auditable source class with generation, review, test, remediation, and policy-decision records.
- Require lifecycle controls for regulated teams: standards guide the agent before work begins, and independent verification gates run before code enters the main codebase.
- Map agent visibility across vendors, contractors, SaaS tools, repositories, and internal systems before expanding what an agent can see, do, or escalate.

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
- [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json)
- [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json)
- [GitLost clipping](../../../raw/processed/GitLost is a dream come true for anyone who likes to jailbreak LLMs.md)
- [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json)
- [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)
- [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json)

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
- Maintained on 2026-07-03 with shadow-agent inventory, MCP audit evidence, and destructive shell-command containment controls.
- Maintained on 2026-07-04 with executable compliance checks, governed semantics, source truth, and execution monitoring.
- Maintained on 2026-07-05 with data-residency, source-code exposure, auditability, air-gapped review, and compliance-as-code pull-request gates.
- Maintained on 2026-07-07 with desktop-agent access, BYOK policy, cost-center membership, and durable usage-reporting controls.
- Maintained on 2026-07-08 with managed editor and CLI policy, centralized telemetry capture boundaries, review-dismissal authority separation, and sensitive-code execution controls.
- Maintained on 2026-07-09 with admin-enabled model access, runtime enforcement, shadow-AI inventory, shared managed runtime, and untrusted repository review controls.
- Maintained on 2026-07-10 with issue-triggered workflow controls for minimum repository scope, private-read separation, and public-output disclosure gates.
- Maintained on 2026-07-12 with slopsquatting, prompt-injection, LLM gateway, task-scoped access, privileged-action visibility, and leader-governance controls.
- Maintained on 2026-07-13 with AI-authored-code traceability, regulated lifecycle controls, and cross-boundary agent visibility requirements.
