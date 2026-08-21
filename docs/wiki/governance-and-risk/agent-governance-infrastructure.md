---
type: "Governance And Risk"
title: "Agent Governance Infrastructure"
description: "Agent governance works best as infrastructure around the model loop."
tags: ["governance-and-risk"]
---

# Agent Governance Infrastructure

## Current Understanding

Agent governance works best as infrastructure around the model loop. Policies for identity, authorization, allowed actions, monitoring, audit, rate limits, and accountability need to be enforced by the harness, gateway, platform, or tool server so the boundary still holds when a prompt, retrieved document, or generated action is hostile or mistaken.

The local governance questions before an agent acts are: which agent or tool actor is acting, who authorized it, what it is allowed to do, whether it is behaving as expected, and whether the action can be audited. Human accountability remains named even when the agent performs implementation work. Security and platform owners define policy boundaries; engineering teams build agents within those boundaries.

This page owns the local infrastructure pattern. Named platforms, cloud products, provider governance features, and broad agent-framework comparisons belong upstream unless they are needed to explain a local control boundary.

The [workspace agents source](../../../raw/processed/OpenAI Just Gave Every Team A Free Employee. Here's The Catch..md) is relevant locally because it describes governance as the adoption gate for agents that cross enterprise tools. The local pattern is least privilege by default: control who can build, publish, run, connect tools, approve actions, use personal connections, inspect history, analyze usage, and suspend an agent.

The [topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) adds public signals that agentic development governance is moving toward runtime inventory, policy enforcement, MCP and tool visibility, generated-output validation, verifiable identity, policy versioning, execution-environment evidence, and tool-call transcripts. Vendor-specific product coverage belongs upstream; locally, these signals support treating agent governance as run-level evidence infrastructure.

The [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) reinforces governance as operational infrastructure: agent actions need trace-level monitoring, delegated identity, credential revocation paths, MCP policy controls, tool-output trust boundaries, and model-routing evidence. The local pattern is to make these controls inspectable at run time rather than relying on prompt instructions after a tool chain is already connected.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) add governance signals for marketplace allowlists, shadow-agent inventory, agent-level identity, tool access control, real-time filtering, audit trails, continuous adversarial testing, and governance controls embedded inside developer tool surfaces. Vendor surveys and product catalogs remain upstream-owned; locally, these signals make agent inventory, plugin source control, and runtime policy evidence first-class infrastructure requirements.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) and [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) add infrastructure controls for model-policy settings, plugin install consent, strict marketplace sources, runner groups, parallel workflow steps, permission-denial logging, and deterministic configuration artifacts. These are infrastructure boundaries because they decide what an agent can run, where it can run, and how the resulting evidence can be audited.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) adds deterministic governance and data-control signals. Coding-agent permissions, approvals, package-install rules, source access, and audit logs should be policy-owned infrastructure with predictable execution boundaries. Forward-deployed or externally hosted AI capability does not remove the need for explicit data classification, reviewability, and operational control over what source, logs, review material, and internal context can leave the environment.

The [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json) adds identity-governance and guardrail evidence for autonomous agents. Local governance infrastructure should support continuous inventory, inherited-permission checks, behavioral baselines, runtime policy enforcement, stale-credential detection, deterministic guardrails, observability, audit trails, escalation rules, and human oversight. A UI-first operating pattern can preserve existing approval paths and audit artifacts when backend integration would bypass controls.

The [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) adds a production-adjacent approved-action pattern. Read-only default access, separate agent identity, requester-bounded permissions, scoped remediation plans, sandbox validation, and attribution to agent, requester, and approver should be inspectable control-plane evidence before an agent changes deployment, runtime, cost, or infrastructure state.

The [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json) adds enterprise configuration and budget-policy signals. Managed assistant settings, model defaults, plugin marketplace controls, bypass-permission modes, browser-tool availability, session credit limits, cost-center budgets, and model enablement should be treated as governed control-plane artifacts. They need ownership, review cadence, override visibility, and audit evidence because they determine which agent surfaces can act, which model runs, and how much work a session can consume.

The [July 2 topic news collector source](../../../raw/processed/2026-07-02/ai-dev-wiki-topic-news-collector-2026-07-02T203134-0400.json) adds workflow identity, session-audit, and trace-log hygiene signals. Coding-agent CI runs should prefer scoped workflow identity and explicit permissions over long-lived personal tokens. Agent-session records, tool calls, prompts, responses, and trace logs are audit evidence, but raw payload retention can expose sensitive development context, so governance infrastructure needs retention, redaction, SIEM routing, and investigation access rules.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) and [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json) reinforce governance as platform infrastructure. Control-plane responsibilities include identity, tool policy, model routing, sandbox boundaries, trace evidence, compliance checks, and human escalation paths, while data-plane tools and retrieved business context need semantic governance and source-truth enforcement.

The [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json) and [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json) add enterprise acceptance gates for agent deployment. Agent governance should cover tool-risk classification, vendor terms, telemetry behavior, jurisdictional policy, on-premise or air-gapped review requirements, per-agent identity, gateway enforcement, role accountability, risk registers, oversight evidence, logging, and monitoring before broad team rollout.

The [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json) and [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json) add declarative and procurement controls. Agent configuration-as-code, permission allow lists, spend caps, traces, audit logs, compliance-as-code, SSO, SCIM, data residency, retention policy, and support commitments are governance infrastructure when agents become team tools. Broad vendor comparison and product ranking remain upstream-owned; locally, these signals define the evidence needed before procurement or rollout.

The [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) and [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json) add managed endpoint policy, OTLP export, identity-bound authorization, data-injection, multi-tool policy, and governed sensitive-code harness signals. Governance infrastructure should keep policy distribution, trace export, authorization, sandboxing, egress limits, credential separation, and session audit evidence outside ordinary prompt wording.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) and [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json) add enterprise session-forensics and shared-runtime signals. Governance infrastructure should preserve prompts, tool usage, MCP activity, command execution, agent actions, skills, rules, model enablement, runtime policy decisions, and shadow-AI inventory as reviewable evidence, while separating product-specific catalogs into the upstream wiki.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) adds upfront fleet-governance and shadow-AI signals. Agent governance should start before pilots spread: maintain an inventory of sanctioned and unsanctioned agent surfaces, assign owners, enforce policy through gateways or managed settings, monitor usage and cost, and define risk-based response paths for developer use of unapproved AI coding or review tools.

The [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json) reinforces identity, visibility, and control-plane requirements for production agents. Governance infrastructure should detect inherited permissions, explain privileged actions, issue short-lived task scopes, monitor shadow AI, and maintain emergency pause or revocation paths across agent platforms.

The [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json) and [July 15 leaf update watch source](../../../raw/processed/2026-07-15/ai-dev-wiki-leaf-update-watch-2026-07-15T210218-0400.json) add production-coding-agent and MCP-policy signals. Governance infrastructure should provide isolated environments, scoped permissions, real-time monitoring, approval gates, policy-based model routing, identity mapping, exportable audit trails, and cross-server MCP policy enforcement before teams expand autonomous development workflows.

The [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json) and [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json) add delegated-identity, governance-certification, and private-agent deployment signals. Agent control planes should record delegation chains, off-host authorization decisions, agent identity, compliance evidence, procurement trust signals, and data-locality boundaries before enterprise agent surfaces become recurring development infrastructure. Broad vendor, product, and certification background remains upstream-owned.

The [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json) adds production governance infrastructure signals. Control planes should maintain current permission inventories, revocation paths, centralized discovery for running agents and connected services, tamper-evident audit logs, policy standards, dependency visibility, and agent-to-agent traffic monitoring so governance remains enforceable as teams add skills, MCP servers, tools, and connected services.

The July 18-21 raw sources add runtime-governance and agent-readiness controls. The [July 18 leaf update watch source](../../../raw/processed/2026-07-18/ai-dev-wiki-leaf-update-watch-2026-07-18T210124-0400.json), [July 19 leaf update watch source](../../../raw/processed/2026-07-19/ai-dev-wiki-leaf-update-watch-2026-07-19T210231-0400.json), and [July 21 leaf update watch source](../../../raw/processed/2026-07-21/ai-dev-wiki-leaf-update-watch-2026-07-21T210116-0400.json) reinforce isolate-scope-approve controls, policy-as-code enforcement, zero-trust identity, sandboxing, monitoring, ownership, incident readiness, and kill-switch paths. The [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json) adds governed-agent gateways and trace issue detection: runtime control planes should observe model calls, tool calls, MCP calls, agent-to-agent hops, budgets, permissions, traces, and recurring failure categories.

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) and [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json) add platform-governance and compromised-agent evidence. Agent infrastructure should make privileges task-scoped and identity-bound, keep human owners discoverable, provide policy and audit trails, support just-in-time access, and monitor enterprise-layer behavior when agents can reach identity, application, network, content, package, or CI systems.

The [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json) and [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json) add workflow-security and supervision-channel evidence. Governance infrastructure should keep autonomous coding work visible across its security and supervision path.

The July 28 raw sources add cross-client managed-policy and suspicious-workflow control evidence. The [topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json) records enterprise policy surfaces for model enablement, agent-client access, managed settings, plugin marketplaces, approval-bypass controls, and CI workflow approval holds. The [leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) reinforces governed remote skills and IDE telemetry controls. Local governance infrastructure should distribute policy across cloud agents, apps, IDEs, CLIs, and MCP skill loaders so one surface cannot bypass another.

The July 31 raw sources add registry, audit, identity, and formal-correctness evidence. The [topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json) records centralized MCP-server registration, admin approval, runtime blocking, AI trust policy, AI-processing audit records, and OAuth authorization controls. The [leaf update watch source](../../../raw/processed/2026-07-31/ai-dev-wiki-leaf-update-watch-2026-07-31T210319-0400.json) reinforces first-class agent identity, owner, purpose, permissions, lifecycle, audit trail, inventory, revocable credentials, and formal-verification layering. Broad company, product, standard, and formal-method background stays upstream-owned; locally, these sources strengthen the infrastructure rule that governance must be enforceable before and during agent execution.

The [August 6 topic news collector source](../../../raw/processed/2026-08-06/ai-dev-wiki-topic-news-collector-2026-08-06T203203-0400.json) adds a containment-first evaluation signal. When a coding agent or cyber-evaluation harness has public internet access, governance infrastructure should enforce network destinations, account identities, permitted communication types, public-output review, emergency stop behavior, and immutable run evidence before the model can contact maintainers, open public contributions, publish packages, or transfer files outside the sandbox.

The August 13 raw sources add audit-harness, usage-metric, ROI, and agent-security lifecycle evidence. The [topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json) records schema-validated session, prompt, tool, and turn events; prompt-hash privacy; SIEM-ready export; MCP-queryable logs; agent autonomy controls; and review-capacity pressure. The [leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json) records third-party agent usage metrics, ROI dashboards, Compliance API local-session evidence, managed-agent budgets, and status incidents. Locally, governance infrastructure should join audit records, usage metrics, budget and ROI assumptions, workspace identity, and incident response evidence without copying sensitive prompt content into central logs.

The August 18 raw sources add inventory-first rollout, managed-settings, and bypass-telemetry evidence. The [topic news collector source](../../../raw/processed/2026-08-18/ai-dev-wiki-topic-news-collector-2026-08-18T203320-0400.json) records a practical enterprise-risk pattern: inventory deployed agents, rank the highest-risk ones, pilot runtime controls and audit logging on one agent, then scale from measured results. The [leaf update watch source](../../../raw/processed/2026-08-18/ai-dev-wiki-leaf-update-watch-2026-08-18T210146-0400.json) adds managed plugin settings, MCP allowlists, approval-bypass controls, organization rule-insight reports, adoption telemetry, and AI access controls as public signals for making rollout state and exception behavior auditable. Locally, governance should start with a current agent inventory, assigned owners, risk tiers, managed policy surfaces, and exportable evidence for bypasses or rollout exceptions.

The August 20 raw sources add continuous-control and evidence-pack signals. The [leaf update watch source](../../../raw/processed/2026-08-20/ai-dev-wiki-leaf-update-watch-2026-08-20T210330-0400.json) records managed IDE settings, token-type revocation, audit-log capture, and governed sovereign-agent substrates. The [topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json) records governance commentary about shadow AI, inherited permissions, continuous capability discovery, permission review, business-impact assessment, adjustable isolation, task-scoped credentials, dual-use gates, and vendor transparency. Locally, governance infrastructure should continuously discover agent surfaces, review inherited access, bind credentials to trust boundaries, require isolation or pause paths, and demand evidence packs or reporting methodology before adoption metrics are trusted.

## Practice Boundaries

- Give each agent, workflow, and tool surface a clear identity and allowed-action set.
- Require human approval or policy approval for high-risk file, network, dependency, credential, external-system, or production-like actions.
- Validate tool requests through deterministic code before execution.
- Keep audit evidence for tool calls and materially important model-assisted actions when the work needs reviewability.
- Enforce budget, rate-limit, and consumption controls outside prompt wording.
- Keep user-visible transparency when an application experience lets an agent act on a user's behalf.
- Keep policy ownership separate from agent implementation so security rules are not rewritten by ordinary agent behavior.
- Prefer service accounts and scoped connectors for shared team agents when personal connections would create unclear delegation.
- Audit published agents regularly for audience, connector scope, approval requirements, and run history.
- Inventory installed agents, tool servers, MCP servers, plugins, and connectors that can affect development workflows.
- Capture run-level evidence for identity, policy version, execution environment, approvals, tool calls, and generated outputs when auditability matters.
- Preserve enough trace, identity, credential, and routing evidence to investigate an agent run after a failure or security concern.
- Keep revocation paths ready for credentials and connectors that an agent can use through a developer environment.
- Govern plugin marketplaces, MCP catalogs, extension sources, and installed agent tooling before tools are available to a developer or agent workflow.
- Pair agent inventory with continuous monitoring, adversarial testing, and audit evidence when agents can touch sensitive systems or software delivery paths.
- Bind runner access, model enablement, parallel execution, plugin installation, and permission-denial records to policy-owned infrastructure rather than per-prompt convention.
- Specify deterministic policy boundaries for permissions, approvals, package installation, data access, and audit logs before agent workflows run.
- Treat data-control and classification gates as infrastructure requirements when development context can reach external models or tools.
- Maintain continuous inventory and behavioral monitoring for agent identities, credentials, connectors, and tool surfaces.
- Prefer execution paths that preserve established approval, escalation, and audit artifacts when agents operate in enterprise workflows.
- Default production-adjacent agents to read-only investigation until a scoped plan, sandbox validation result, requester authority, and approver attribution are recorded.
- Treat managed settings, model policies, plugin marketplace controls, browser-tool enablement, and budget caps as policy-owned infrastructure rather than personal editor preferences.
- Record override, bypass, and model-default decisions when they affect authority, cost, repeatability, or review evidence.
- Prefer scoped workflow identity and explicit automation permissions over stored personal tokens for unattended coding-agent jobs.
- Define retention, redaction, and access rules for agent-session streams, tool-call transcripts, prompts, responses, and trace logs before routing them to audit systems.
- Separate control-plane policy, identity, routing, and audit responsibilities from data-plane tool execution and retrieval.
- Keep human escalation paths and validation capacity visible when regulated or audit-heavy work adopts agentic workflows.
- Treat semantic layers and compliance checks as governance infrastructure when agents can act on enterprise data or pull requests.
- Review vendor terms, telemetry behavior, jurisdictional rules, deployment location, and approved alternatives before classifying a coding or review agent for enterprise use.
- Require per-agent identity, gateway enforcement, risk registers, oversight evidence, logging, and monitoring when agents become recurring team infrastructure.
- Version agent definitions, prompts, model routes, triggers, tools, permissions, and spend caps when those settings determine recurring team behavior.
- Require identity, audit-log, retention, residency, support, and compliance evidence before enterprise coding-agent pilots expand.
- Distribute editor and CLI agent policy through managed endpoint or server settings when personal configuration would make control evidence inconsistent.
- Treat trace export, prompt-content retention, and tool-content retention as policy decisions with security review and audit ownership.
- Pair governed sensitive-code harnesses with sandbox evidence, deny-by-default networking, credential separation, and human approval records.
- Capture session forensics across prompts, tools, MCP activity, commands, generated rules, skills, and agent actions when those records support runtime enforcement or incident review.
- Inventory unmanaged coding-agent surfaces and code-enabled managed runtimes before treating IDE or platform policy as complete.
- Start agent-fleet governance with ownership, inventory, policy enforcement, monitoring, and cost controls instead of treating those controls as post-pilot cleanup.
- Track unauthorized AI development tools through sanctioned-tool inventories, acceptable-use policy, training, monitoring, and risk-based response paths.
- Detect inherited permissions, standing access, shadow agents, and unexplained privileged actions before expanding agent autonomy.
- Maintain short-lived task scopes, emergency pause, and revocation paths as control-plane features, not after-the-fact incident notes.
- Require isolated execution, scoped permissions, live monitoring, approval gates, model-route policy, identity mapping, and exportable audit evidence before production coding-agent rollout.
- Centralize MCP or tool policy enforcement when server-by-server configuration would create inconsistent permissions, redaction, rate-limit, or audit behavior.
- Record delegation-chain evidence, agent identity, authorization decisions, procurement governance proof, and data-locality commitments before recurring private-agent deployment.
- Maintain current permission inventories, revocation paths, connected-service discovery, dependency visibility, tamper-evident audit logs, policy standards, and agent-traffic monitoring as control-plane infrastructure.
- Require agent readiness evidence for isolation, authorization boundaries, command safety, network egress, workflow visibility, provenance, rollback, incident response, explainability, and kill-switch behavior before production-like autonomy.
- Treat governed-agent gateways and trace issue monitors as runtime control planes when they enforce cost, permission, data-boundary, policy, and failure-category evidence across model, tool, MCP, and agent-to-agent hops.
- Preserve centralized visibility across generation, test, review, merge, and deployment before scaling autonomous coding volume.
- Record voice steering, usage monitors, model-router decisions, refusal paths, and subagent handoffs when they affect supervision or audit evidence.
- Distribute model policy, plugin marketplace rules, approval-bypass settings, client access, token limits, and telemetry export rules consistently across cloud, app, IDE, CLI, and MCP skill-loading surfaces.
- Hold suspicious or high-impact agent-authored workflow execution until policy and owner approval evidence are recorded.
- Require agent identities to carry owner, purpose, permission set, lifecycle date, inventory record, audit trail, and task-specific revocation path before granting durable workflow access.
- Treat formal correctness tools as governance evidence that can strengthen policy-boundary checks but cannot replace runtime identity, authorization, monitoring, and human escalation controls.
- Capture AI-processing audit records, trust-layer policy decisions, and remote-tool authorization events where they can be joined to agent identity and workflow outcome.
- Enforce allowlisted network destinations, external-communication classes, public-output review, and emergency stop behavior for evaluation agents before granting public internet access.
- Preserve immutable evidence for attempted external contact, repository contribution, package publication, file transfer, and identity use during agent runs.
- Capture session, prompt, tool, turn, workspace, budget, and incident evidence through schema-validated audit events, using hashes or redacted previews when full prompt retention would expose sensitive context.
- Pair agent adoption metrics and ROI dashboards with governance evidence for reviewer capacity, cost ownership, identity, approved tool scope, and incident response instead of treating activity counts as approval.
- Start governance rollout with an agent inventory, risk tiering, one controlled pilot, runtime logs, and measured results before expanding controls across all agents.
- Treat managed settings, MCP allowlists, approval-bypass controls, rule-insight reports, and rollout telemetry as governance evidence that must be exportable and owner-reviewed.
- Continuously discover agent capabilities, shadow-agent surfaces, inherited permissions, and connected tools instead of relying on periodic policy review alone.
- Bind credentials to task scopes and trust boundaries, and preserve token-type revocation plus audit evidence for containment after agent or tool incidents.
- Require adjustable isolation, emergency pause, signed evidence packs, and vendor-reporting methodology when agents operate in regulated, sensitive, or high-impact workflows.
- Treat vendor adoption, safety, and usage metrics as governance inputs only when their collection method, scope, exclusions, and auditability are visible.

## Authoritative Sources

- [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json)
- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [retrieval and tools practice](../retrieval-and-tools/rag-tools-and-mcp-practice.md)
- [Workspace agents source](../../../raw/processed/OpenAI Just Gave Every Team A Free Employee. Here's The Catch..md)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json)
- [June 29 leaf update watch source](../../../raw/processed/2026-06-29/ai-dev-wiki-leaf-update-watch-2026-06-29T210316-0400.json)
- [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json)
- [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json)
- [July 2 topic news collector source](../../../raw/processed/2026-07-02/ai-dev-wiki-topic-news-collector-2026-07-02T203134-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json)
- [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json)
- [July 5 leaf update watch source](../../../raw/processed/2026-07-05/ai-dev-wiki-leaf-update-watch-2026-07-05T210225-0400.json)
- [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json)
- [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)
- [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json)
- [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json)
- [July 15 leaf update watch source](../../../raw/processed/2026-07-15/ai-dev-wiki-leaf-update-watch-2026-07-15T210218-0400.json)
- [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json)
- [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json)
- [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json)
- [July 18 leaf update watch source](../../../raw/processed/2026-07-18/ai-dev-wiki-leaf-update-watch-2026-07-18T210124-0400.json)
- [July 19 leaf update watch source](../../../raw/processed/2026-07-19/ai-dev-wiki-leaf-update-watch-2026-07-19T210231-0400.json)
- [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json)
- [July 21 leaf update watch source](../../../raw/processed/2026-07-21/ai-dev-wiki-leaf-update-watch-2026-07-21T210116-0400.json)
- [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json)
- [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json)
- [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 31 topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json)
- [July 31 leaf update watch source](../../../raw/processed/2026-07-31/ai-dev-wiki-leaf-update-watch-2026-07-31T210319-0400.json)
- [August 6 topic news collector source](../../../raw/processed/2026-08-06/ai-dev-wiki-topic-news-collector-2026-08-06T203203-0400.json)
- [August 13 topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json)
- [August 13 leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json)
- [August 18 topic news collector source](../../../raw/processed/2026-08-18/ai-dev-wiki-topic-news-collector-2026-08-18T203320-0400.json)
- [August 18 leaf update watch source](../../../raw/processed/2026-08-18/ai-dev-wiki-leaf-update-watch-2026-08-18T210146-0400.json)
- [August 20 leaf update watch source](../../../raw/processed/2026-08-20/ai-dev-wiki-leaf-update-watch-2026-08-20T210330-0400.json)
- [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance controls for agents](governance-controls-for-agents.md)
- [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [application-patterns](../application-patterns/index.md)
- [adoption-and-operating-model](../adoption-and-operating-model/index.md)
- [agent ownership rosters](../adoption-and-operating-model/agent-ownership-rosters.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)
- [agent identity and delegated authority](agent-identity-and-delegated-authority.md)
- [trajectory-level agent evaluation](../verification-and-evals/trajectory-level-agent-evaluation.md)
- [destructive command controls](destructive-command-controls.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-07-23 with task-scoped identity, human owners, just-in-time access, audit trails, and enterprise-layer monitoring signals.
- Maintained on 2026-08-18 with inventory-first agent risk rollout, managed-settings governance, approval-bypass reporting, and rollout-telemetry signals.
- Created on 2026-06-23 to separate infrastructure enforcement, identity, authorization, audit, and accountability from the broader governance-controls page.
- Maintained on 2026-06-23 with public runtime governance signals for agent inventory, policy enforcement, governed MCP, and run-level evidence.
- Maintained on 2026-06-24 with trace monitoring, delegated identity, credential revocation, and MCP policy controls.
- Maintained on 2026-06-25 with marketplace allowlists, shadow-agent inventory, real-time filtering, adversarial testing, and tool-surface governance.
- Maintained on 2026-06-26 with policy-owned model settings, runner controls, plugin consent, permission-denial evidence, and deterministic configuration artifacts.
- Maintained on 2026-06-28 with deterministic governance boundaries and data-control gates for external AI capability.
- Maintained on 2026-06-29 with guardian-agent identity controls, deterministic guardrails, observability, escalation, and UI-first audit preservation.
- Maintained on 2026-07-01 with read-only default investigation, scoped approved actions, sandbox validation, and agent-requester-approver attribution.
- Maintained on 2026-07-01 with enterprise managed settings, model defaults, plugin controls, browser-tool enablement, and budget caps as control-plane evidence.
- Maintained on 2026-07-02 with scoped workflow identity, agent-session audit streams, and trace-log hygiene requirements.
- Maintained on 2026-07-04 with platform control-plane boundaries, governed semantics, compliance checks, and human escalation capacity.
- Maintained on 2026-07-05 with tool-risk classification, deployment-location gates, per-agent identity, gateway enforcement, and oversight evidence.
- Maintained on 2026-07-06 with configuration-as-code, compliance-as-code, procurement, identity, retention, and spend-control evidence.
- Maintained on 2026-07-08 with managed endpoint policy, trace export controls, identity-bound authorization, and governed sensitive-code harness evidence.
- Maintained on 2026-07-09 with runtime session forensics, shadow-AI inventory, model-enable policy, and shared managed-runtime governance evidence.
- Maintained on 2026-07-11 with upfront fleet governance, sanctioned-tool inventory, shadow-AI monitoring, and cost-control requirements.
- Maintained on 2026-07-12 with inherited-permission detection, privileged-action visibility, task-scoped authority, shadow-AI monitoring, and emergency revocation controls.
- Maintained on 2026-07-15 with isolated coding-agent environments, scoped permissions, live monitoring, policy-based routing, audit trails, and cross-server MCP policy enforcement.
- Maintained on 2026-07-16 with delegation-chain evidence, off-host authorization, agent identity, governance proof, and private-agent data-locality boundaries.
- Maintained on 2026-07-17 with current permission inventories, revocation paths, centralized discovery, audit integrity, dependency visibility, and agent-traffic monitoring.
- Maintained on 2026-07-22 with readiness checklists, policy-as-code, gateway-level runtime controls, trace issue detection, incident readiness, and kill-switch evidence.
- Maintained on 2026-07-26 with workflow-security visibility, supervision-channel records, usage monitors, model-router decisions, refusal paths, and subagent handoff audit evidence.
- Maintained on 2026-07-31 with MCP registration governance, AI trust-layer audit, first-class agent identity, lifecycle, revocable credentials, and formal-correctness layering.
- Maintained on 2026-07-28 with cross-client managed policy, model enablement, plugin marketplace, approval bypass, CI approval hold, token-limit, telemetry-export, and remote-skill governance evidence.
- Maintained on 2026-08-06 with containment-first infrastructure controls for public internet access, external communication, repository contribution, package publication, emergency stops, and immutable run evidence.
- Maintained on 2026-08-13 with audit-harness events, prompt-hash privacy, SIEM export, usage metrics, ROI assumptions, workspace identity, budgets, and incident-response evidence.
- Maintained on 2026-08-20 with continuous discovery, inherited-permission review, task-scoped credentials, token-type revocation, isolation paths, evidence packs, and vendor-reporting methodology guidance.
