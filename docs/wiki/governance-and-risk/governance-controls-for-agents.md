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

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) and [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) add production-agent and investment-governance signals. Production coding agents should use isolated workspaces, scoped identities, monitored behavior, human approval for consequential actions, model routing by policy, and full audit trails. AI investment governance should require usage and spend visibility, outcome ROI, governance before advanced workflows scale, centrally funded shared capabilities, and capacity matched to proven demand.

The July 17 raw sources add governed-agent infrastructure evidence. The [topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) records event-triggered automation, terminal-agent hardening, and remediation flows as product evidence for local controls. The durable owners are [event-triggered agent workflows](../agent-workflows/event-triggered-agent-workflows.md), [terminal agent workflows](../agent-workflows/terminal-agent-workflows.md), [destructive command controls](destructive-command-controls.md), [ai-assisted security repair gates](ai-assisted-security-repair-gates.md), [agent governance infrastructure](agent-governance-infrastructure.md), and [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md).

The July 18-21 raw sources add agent-control refinements. The [July 18 topic news collector source](../../../raw/processed/2026-07-18/ai-dev-wiki-topic-news-collector-2026-07-18T203453-0400.json) and [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json) add branch-tested review instructions, setup prompts, approval agents, prompt-injection defenses, API-safe skill evaluation, MCP connection inventory, and explainable command approvals. The [July 21 leaf update watch source](../../../raw/processed/2026-07-21/ai-dev-wiki-leaf-update-watch-2026-07-21T210116-0400.json) adds repository-hosted agent governance rules and agent readiness checklists. Locally, these are control-plane requirements: instructions, setup prompts, approvals, tool connections, and agent-mediated contributions need policy evidence before they change code or external state.

The detailed control leaves are:

- [prompt-injection-and-untrusted-content.md](prompt-injection-and-untrusted-content.md) owns direct and indirect prompt-injection handling, source labels, and untrusted-content boundaries.
- [agent-governance-infrastructure.md](agent-governance-infrastructure.md) owns identity, authorization, allowed actions, monitoring, audit, policy enforcement, and human accountability chains.
- [sensitive-data-and-supply-chain-controls.md](sensitive-data-and-supply-chain-controls.md) owns secrets, PII, package installs, dependencies, model or source artifacts, licensing, and third-party notices.
- [destructive-command-controls.md](destructive-command-controls.md) owns destructive shell command detection, denial reasons, path containment, explicit approval, and recovery evidence.

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) adds agent automation controls and enterprise connector governance evidence. Governance controls should classify first-party and third-party agents, record rationale and confidence for automated suggestions, preserve proposed-state-change approval panels, monitor agent activity, and detect prompt-injection attempts before content retrieval or action.

The [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json) and [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json) add two governance refinements. Approval panels and rationale-bearing suggestions improve reviewability but do not enforce security by themselves. Coding-agent sandbox escapes, generated files, mid-conversation tool changes, and fallback routing need policy, audit, and post-action validation outside the prompt.

The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) and [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) add scoped discovery and enterprise content-control signals. Progressive tool discovery, field-level scopes, managed OAuth, content labels, action vetting, prompt-injection detection, audit trails, alerts, and high-impact approval holds should be enforced by the runtime around the agent.

The [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json) and [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) add managed-policy, dependency, and CI gate evidence. Cross-client model, plugin, marketplace, approval-bypass, token-limit, telemetry, and remote-skill policy routes through [agent governance infrastructure](agent-governance-infrastructure.md) and [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md). Malware-specific package alerts route through [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md), while CI execution holds route through [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md).

The August 3 raw sources add agent identity and security-checklist evidence. The [midday leaf update watch source](../../../raw/processed/2026-08-03/ai-dev-wiki-leaf-update-watch-2026-08-03T121800-0400.json) and [evening leaf update watch source](../../../raw/processed/2026-08-03/ai-dev-wiki-leaf-update-watch-2026-08-03T210231-0400.json) reinforce named owners, purposes, permissions, lifecycle review, discovery, audit trails, and first-class agent records as control-plane requirements. The same evening source adds pre-deployment checklist signals: bound the job before access, reduce tools, keep authorization and high-impact approvals outside the model, rerun adversarial tests after prompt, tool, retrieval, memory, policy, or model changes, and attach evidence to release controls.

The [August 6 topic news collector source](../../../raw/processed/2026-08-06/ai-dev-wiki-topic-news-collector-2026-08-06T203203-0400.json) adds containment and social-engineering evidence from a public analysis of an AI Security Institute cyber-evaluation incident. The local guidance is source-specific until primary incident material is available: coding-agent and evaluation harnesses should treat internet access, maintainer contact, public pull requests, package publishing, external messaging, and repository contribution attempts as separate high-impact action classes with explicit purpose binding, egress controls, monitoring, kill switches, and audit evidence.

The [August 9 topic news collector source](../../../raw/processed/2026-08-09/ai-dev-wiki-topic-news-collector-2026-08-09T203245-0400.json) and [August 9 leaf update watch source](../../../raw/processed/2026-08-09/ai-dev-wiki-leaf-update-watch-2026-08-09T210438-0400.json) reinforce high-capability and browser-agent containment. Higher-capability coding or cybersecurity agents should have isolated test environments, restricted network and tool access, model or artifact protection, monitoring, detection, and pause criteria before work continues. Browser-agent runtimes add authenticated browser sessions, proxies, captcha handling, and page-driven tool output to the control surface; route their runtime specifics through [browser-agent runtime boundaries](../application-patterns/browser-agent-runtime-boundaries.md).

The August 15 raw sources reinforce controls as enforceable runtime architecture. The [topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json) adds model enablement, self-hosted factory, file-backed planning, CI milestone-gate, and runtime gateway evidence. The [leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) adds durable execution, scoped MCP access, behavior baselines, company-harness drills, containment failures, persistent memory poisoning, and repository/skill baiting evidence. Locally, agent governance should require admin enablement, cost ownership, egress controls, scoped credentials, auditable session records, memory quarantine, repository-package provenance, and semantic acceptance gates before long-running agents operate across shared systems.

The August 17 topic news collector adds defensive-security and local-sandbox evidence. Security agents should receive approved access to codebases, infrastructure configuration, documentation, CI checks, security playbooks, and prioritized backlog targets rather than broad unconstrained autonomy. Local coding-agent sandboxes should deny host credentials, commits, pushes, installs, and sensitive remote capabilities by environment policy when those actions are outside the approved workflow.

The August 22 raw sources reinforce governance as runtime architecture rather than policy prose:

- [Shared-channel agent sessions](../agent-workflows/shared-channel-agent-sessions.md) own chat-visible steering, repository permission checks, integration identity, sandbox billing, and extra pull-request approvals.
- [Governed database agent access](../retrieval-and-tools/governed-database-agent-access.md) owns database-agent insider risk, governed semantic layers, saved connections, audit trails, and isolated writes.
- [Execution edge authorization](execution-edge-authorization.md) owns graph-edge authorization, paid agent actions, connected-app action gates, memory-write authority, sandbox pause criteria, and trust receipts.
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md) own layered release, CI, sampled-production, deterministic, LLM-judge, and human-review evaluation placement.
- [Prompt injection and untrusted content](prompt-injection-and-untrusted-content.md) owns hidden document carriers, persistent memory poisoning, malicious links, connected-app injection, and paid-action screening.

The local synthesis from the [topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json) and [leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json) is that controls are credible when authorization, spend limits, memory writes, connected-app actions, runtime traces, and pause or approval decisions are enforced outside the model and joined to the delegated human or workflow.

The August 28 and 29 raw sources add live-agent governance, policy-default, and workflow-redesign evidence. The [leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json) records running-agent discovery, granular guardrails, action-order review, lifecycle governance, contextual action controls, structured-output credential boundaries, and AI-generated-code production risk. The [topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) records managed coding-agent policy, billing, retention, sandbox, review-effort, AI-native workflow orchestration, and cross-surface agent boundaries. Locally, governance should treat these as rollout controls rather than broad product facts.

The [August 31 topic news collector source](../../../raw/processed/2026-08-31/ai-dev-wiki-topic-news-collector-2026-09-01T003223Z.json) adds open-source contribution, runtime semantic-policy, eval-containment, and MCP prompt-injection evidence. AI-assisted contributions should keep contributor accountability for quality, correctness, maintainability, legal compliance, review, testing, and modification even when disclosure is optional. High-risk agent evaluations should probe sandbox configuration, restrict or remove internet access where possible, state target and network boundaries, monitor reasoning/actions/network activity, and preserve human stop authority. Runtime guardrails should inspect tool intent, data movement, package or MCP server installs, scope drift, and follow-up instructions before action.

The September 3 raw sources add control-stack and spend-boundary evidence:

- The [leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json) reinforces owner registers, scoped identities, kill switches, business-rule validation, SIEM export, and runtime mediation as recurring controls.
- The [topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json) connects identity, access, memory, monitoring, audit, governed execution, and cost attribution as one control stack.

Locally, governance controls should join those records by agent or session so a risky run can be attributed and stopped outside model self-limiting.

The September 4 raw sources add policy-default, pause-monitor, and supply-chain-control evidence:

- The [September 4 leaf update watch source](../../../raw/processed/2026-09-04/ai-dev-wiki-leaf-update-watch-2026-09-04T210211-0400.json) records budget expiry, AI review approvals, managed defaults, data-retaining model enablement, and cybersecurity monitors that can slow, pause, or stop work.
- The [September 4 topic news collector source](../../../raw/processed/2026-09-04/ai-dev-wiki-topic-news-collector-2026-09-05T003214Z.json) records content exclusions, model policy, model deprecation, trusted publishing, reusable workflow identity, and human checkpoints.
- Locally, administrator policy should bind those controls to the agent, repository, workflow, model route, budget, data boundary, and release or registry path before autonomous work scales.

## Practice Boundaries

- Keep secrets, credentials, PII, and company-internal content outside prompts and raw source artifacts unless the human explicitly approves that use.
- Treat policy defaults, billing behavior, retention settings, sandbox availability, review-depth defaults, and agent action ordering as governance inputs before a managed coding-agent surface becomes team policy.
- Require running-agent discovery, agent registration, owner mapping, telemetry, granular guardrails, and context-aware action checks for recurring or cross-system agents.
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
- Join identity, access, memory, monitoring, audit, cost, and revocation evidence by agent or session when the workflow can keep running after a single prompt.
- Treat daily token or request envelopes, outbound API meters, and spend-triggered session restrictions as blast-radius controls for long-running agents.
- Validate business-rule, system-of-record, and SIEM-export controls before agents move from advisory reasoning to operational side effects.
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
- Require isolate-scope-approve controls, runtime monitoring, policy-routed models, and audit trails before production coding agents can operate beyond pilot tasks.
- Tie adoption expansion to visible usage, spend, outcome ROI, shared-capability readiness, and governance evidence rather than raw assistant availability.
- Route event-triggered and terminal agents through the governed workflow contract before they inspect, patch, execute commands, or create public output.
- Route destructive shell commands through command-risk detection, path containment, denial evidence, and explicit approval before execution.
- Route permission inventories, revocation paths, centralized discovery, audit integrity, and agent-traffic monitoring through governance infrastructure leaves instead of relying on local prompt rules.
- Use scenario-level security guardrails and structural-integrity checks before treating AI acceleration in vulnerability or dependency workflows as reduced risk.
- Treat branch-readable instructions, setup prompts, approval agents, MCP connection inventories, command explanations, and repository-hosted agent-governance manifests as enforceable workflow controls when they affect code or tool authority.
- Maintain discoverable inventories of agents, tools, connected services, permissions, owners, revocation paths, and permitted-use policies before agents operate across systems.
- Prefer first-class agent identities, just-in-time access, lifecycle visibility, and audit trails over long-lived shared secrets for autonomous workflows.
- Treat coding-agent sandbox escapes and untrusted repository content as governance failures that require sandbox-boundary review, egress controls, and post-patch validation.
- Route upstream product, protocol, company, and CVE background to the upstream AI or security wiki; keep this page focused on local approval, ownership, and audit controls.
- Require policy-backed enforcement for approval panels, confidence scores, and rationale displays before treating them as security-relevant controls.
- Audit fallback routing and mid-conversation tool-list changes when they can alter model choice, allowed actions, cache behavior, or execution path.
- Enforce field-level scopes, action vetting, prompt-injection screening, audit trails, and approval holds in the runtime when agents act on enterprise content or discovered tools.
- Enforce managed model, plugin, marketplace, approval-bypass, telemetry, token-limit, remote-skill, CI execution, and malware-alert policies consistently across agent clients and IDE surfaces.
- Give defensive agents approved code, infrastructure, documentation, CI, playbook, and backlog access while denying host credentials, commits, pushes, installs, and unapproved remote actions through sandbox policy.
- Require first-class agent records with owner, purpose, permissions, lifecycle review, inventory, cost attribution, and deprovisioning before agents operate across SaaS, repositories, or internal automation.
- Attach adversarial-test, approval, retest-trigger, and release-control evidence to agent deployment decisions instead of treating a checklist answer as enforcement.
- Gate public maintainer contact, public-repository contribution, package publication, external messaging, and unsandboxed internet use separately from ordinary code edits, even when they occur inside an evaluation or security-testing workflow.
- Require real-time monitoring, egress limits, kill-switch paths, and post-run audit review for coding agents that can reach public systems or people.
- Pause or hold high-capability agent work when containment evidence, network/tool restrictions, monitoring, or detection coverage is not strong enough for the task risk.
- Treat browser-agent identity, proxy, captcha, and authenticated-session features as governed controls before agents can operate against external websites.
- Require model-enable evidence, runtime cost attribution, scoped credentials, egress policy, retained session records, memory inspection, repository-package provenance, and semantic CI or deployment gates when agents can run long-lived or cross-system work.
- Treat team chat, connected apps, semantic layers, database tools, agent wallets, and cloud sandboxes as execution edges that need independent authorization and trace evidence.
- Route mandate evidence, spend caps, memory writes, connected-app actions, graph evidence, and sandbox pause criteria through [execution edge authorization](execution-edge-authorization.md).
- Keep AI-assisted contributor accountability, review, testing, maintainability, and legal-compliance obligations explicit even when a policy does not require AI-use disclosure.
- Probe containment, network reachability, tool restrictions, monitoring, and human stop paths before high-risk agent evaluations or security-testing workflows proceed.
- Enforce runtime policy over tool intent, data movement, package and MCP server installation, scope drift, and follow-up instructions when agents can cross systems.
- Bind budget expiry, AI approvals, managed model defaults, data-retaining routes, pause monitors, content exclusions, trusted publishing, and reusable-workflow identity to explicit administrator policy before recurring agents can affect repositories, packages, or external systems.

## Authoritative Sources

- [September 4 leaf update watch source](../../../raw/processed/2026-09-04/ai-dev-wiki-leaf-update-watch-2026-09-04T210211-0400.json)
- [September 4 topic news collector source](../../../raw/processed/2026-09-04/ai-dev-wiki-topic-news-collector-2026-09-05T003214Z.json)
- [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json)
- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [September 3 leaf update watch source](../../../raw/processed/2026-09-03/ai-dev-wiki-leaf-update-watch-2026-09-03T210157-0400.json)
- [September 3 topic news collector source](../../../raw/processed/2026-09-03/ai-dev-wiki-topic-news-collector-2026-09-04T003115Z.json)
- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
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
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json)
- [July 18 topic news collector source](../../../raw/processed/2026-07-18/ai-dev-wiki-topic-news-collector-2026-07-18T203453-0400.json)
- [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json)
- [July 21 leaf update watch source](../../../raw/processed/2026-07-21/ai-dev-wiki-leaf-update-watch-2026-07-21T210116-0400.json)
- [July 22 topic news collector source](../../../raw/processed/2026-07-22/ai-dev-wiki-topic-news-collector-2026-07-22T203140-0400.json)
- [July 22 leaf update watch source](../../../raw/processed/2026-07-22/ai-dev-wiki-leaf-update-watch-2026-07-22T210121-0400.json)
- [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json)
- [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json)
- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [August 3 midday leaf update watch source](../../../raw/processed/2026-08-03/ai-dev-wiki-leaf-update-watch-2026-08-03T121800-0400.json)
- [August 3 evening leaf update watch source](../../../raw/processed/2026-08-03/ai-dev-wiki-leaf-update-watch-2026-08-03T210231-0400.json)
- [August 6 topic news collector source](../../../raw/processed/2026-08-06/ai-dev-wiki-topic-news-collector-2026-08-06T203203-0400.json)
- [August 9 topic news collector source](../../../raw/processed/2026-08-09/ai-dev-wiki-topic-news-collector-2026-08-09T203245-0400.json)
- [August 9 leaf update watch source](../../../raw/processed/2026-08-09/ai-dev-wiki-leaf-update-watch-2026-08-09T210438-0400.json)
- [Browserbase use-cases clipping](../../../raw/processed/Browserbase Use Cases Web Scraping & AI Agent Examples.md)
- [August 15 topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [August 17 topic news collector source](../../../raw/processed/2026-08-17/ai-dev-wiki-topic-news-collector-2026-08-17T203101-0400.json)
- [August 22 topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json)
- [August 22 leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json)
- [August 31 topic news collector source](../../../raw/processed/2026-08-31/ai-dev-wiki-topic-news-collector-2026-09-01T003223Z.json)

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
- [destructive command controls](destructive-command-controls.md)
- [event-triggered agent workflows](../agent-workflows/event-triggered-agent-workflows.md)
- [terminal agent workflows](../agent-workflows/terminal-agent-workflows.md)
- [browser-agent runtime boundaries](../application-patterns/browser-agent-runtime-boundaries.md)
- [execution edge authorization](execution-edge-authorization.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-09-04 with budget-expiry, AI-approval, managed-default, data-retention, pause-monitor, content-exclusion, trusted-publishing, and workflow-identity controls.
- Maintained on 2026-08-31 with AI-assisted contributor accountability, runtime semantic-policy, eval containment, tool-intent, data-movement, package/MCP-install, and high-risk network-boundary evidence.
- Maintained on 2026-09-03 with identity-access-memory-monitoring-audit stack, business-rule validation, SIEM export, cost envelopes, kill-switch, and revocation evidence.
- Maintained on 2026-07-23 with agent classification, rationale, confidence, proposed-change approval, activity oversight, and prompt-injection detection guidance.
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
- Maintained on 2026-07-14 with isolate-scope-approve production controls and investment-governance evidence for scaled agent adoption.
- Maintained on 2026-07-17 with routing to focused leaves for event-triggered workflow governance, destructive-command controls, governance infrastructure, approval boundaries, and security repair gates.
- Maintained on 2026-07-22 with branch-tested instruction controls, setup-prompt governance, command explanation, MCP inventories, and repository-hosted agent-governance evidence.
- Maintained on 2026-07-22 with inventory, revocation, agent identity, just-in-time access, and sandbox-boundary control evidence.
- Maintained on 2026-07-24 with approval-panel enforcement limits, sandbox-escape validation, tool-list mutation, and fallback-routing governance.
- Maintained on 2026-07-27 with progressive-discovery and enterprise-content runtime control guidance.
- Maintained on 2026-07-28 with cross-client managed policy, CI execution approval, telemetry, token-limit, remote-skill, and malware-alert policy guidance.
- Maintained on 2026-08-03 with first-class agent records, lifecycle review, inventory, pre-deployment adversarial retest, and evidence-attached release controls.
- Maintained on 2026-08-06 with source-specific containment guidance for internet access, public contribution attempts, maintainer contact, external messaging, monitoring, and kill-switch controls.
- Maintained on 2026-08-09 with high-capability pause criteria and browser-agent identity, proxy, captcha, and authenticated-session controls.
- Maintained on 2026-08-15 with admin model enablement, self-hosted factory controls, scoped access, memory quarantine, repository-package provenance, containment, and semantic acceptance-gate evidence.
- Maintained on 2026-08-17 with defensive-security agent access and local coding-agent sandbox-denial evidence.
- Maintained on 2026-08-22 with execution-edge authorization, spend-cap, memory-write, connected-app, sandbox-pause, and graph-evidence controls.
- Maintained on 2026-08-29 with running-agent discovery, action sequencing, policy-default, billing, retention, sandbox, review-effort, structured-output, and production-risk governance evidence.
