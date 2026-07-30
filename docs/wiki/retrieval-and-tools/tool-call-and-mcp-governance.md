---
type: "Retrieval And Tools"
title: "Tool Call And MCP Governance"
description: "Tool calls turn model intent into software-mediated action."
tags: ["retrieval-and-tools"]
---

# Tool Call And MCP Governance

## Current Understanding

Tool calls turn model intent into software-mediated action. The model requests an action with arguments, the harness validates schema and permissions, software executes outside the model, and the result becomes context for a continuation or final answer.

Dynamic context tools sit between retrieval and action. They let a model request targeted additional information when the application cannot know all needed context upfront. Action tools perform governed operations such as reading, writing, scheduling, querying, transforming, or updating external systems.

MCP is the local practice boundary for standardized tool access. It exposes typed tools through a server and client arrangement while credentials remain in the connector or server. Broad MCP ecosystem coverage belongs to the upstream [AI wiki MCP server index](../../../upstream-ai-wiki/mcp-servers/index.md); this page owns how local AI-assisted workflows should treat MCP as a governed access layer.

The [topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) adds a governed-execution lens for MCP and agent tools: tool governance should account for the acting identity, policy version, execution environment, runtime inventory, tool-call transcript, and generated-output validation. Vendor-specific governed MCP products remain upstream-owned; the local rule is that tool access should produce reviewable evidence when it can change code, data, infrastructure, or external systems.

The [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) adds three tool-governance requirements. MCP gateway practice should include per-tool policy, per-user or per-group scope, hosted tool catalog change detection, centralized audit logs, and data protection before tool responses reach the model. Tool output from externally controlled systems should be treated as untrusted content that cannot authorize shell commands, dependency changes, credential use, or cloud actions by itself. Model or provider routing should be recorded when available because hidden routing can affect reproducibility and evaluation evidence.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) add two operating controls. First, tool installation sources and marketplaces should be governed before a tool appears in an agent environment. Second, MCP-connected external data must be treated as untrusted evidence even when the MCP server itself is approved, because the content flowing through the server can still steer a coding agent toward unsafe actions.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) and [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) add consent, denial, and deterministic-control-plane signals. Tool catalogs, plugins, compiled agent artifacts, content hashes, MCP exposure, permission-denial reasons, authentication notices, and tamper-evident logs should be inspectable control-plane evidence rather than invisible agent behavior.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) adds another MCP security-practice signal: least privilege, allowlists, audit trails, data boundaries, and explicit approval gates should be present before MCP tools can affect code, repositories, infrastructure, or external systems.

The [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json) and [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) add tool-metadata and catalog-governance signals. Tool descriptions, Team MCP catalogs, organization groups, agent pickers, CLI surfaces, and approved integration marketplaces are instruction-bearing supply-chain inputs. A critical agent should not consume changed tool metadata, new server entries, or newly available command surfaces without provenance review, group scope, and re-approval when the action surface changes.

The [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json) and [FastMCP research source](../../../raw/processed/project-wiki-research-2026-07-01-fastmcp.md) add two governed-MCP boundaries. Browser-driving tools and remote MCP servers that can administer accounts, audit-log streams, or production-adjacent systems should be classified as privileged action surfaces with explicit scope, approval, and evidence requirements. FastMCP-style OpenAPI or FastAPI conversion is useful implementation context, but the local practice is to review the resulting tool surface as a designed least-privilege interface rather than exposing every route because a framework can generate it.

The [July 2 topic news collector source](../../../raw/processed/2026-07-02/ai-dev-wiki-topic-news-collector-2026-07-02T203134-0400.json) adds browser-observation and build-aware context signals. Browser tools can turn live UI state into agent evidence, but permission, domain, and reproducibility controls still decide whether the observation is sufficient or needs logs and tests. Language-server setup skills and compile-command generation are retrieval preparation steps: they should be reviewed as context-building tools, not as permission to edit without build or import verification.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) and [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json) add trusted-catalog, tool-description, and semantic-MCP signals. Tool descriptions, schema text, catalog entries, routing decisions, and returned business context are part of the trusted execution surface. They need provenance review, re-approval when action surfaces change, invocation evidence, deterministic verification checks, and governed semantic definitions when agents retrieve enterprise metrics.

The [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json) adds operating telemetry for tools and skills. Tool-call inventory, MCP server usage, Bash command families, skill adoption, and error counts are governance evidence because they reveal which integrations are actually used, which fail often, and which surfaces deserve retirement or stricter policy. The [Just Bash clipping](../../../raw/processed/vercel-labsjust-bash Bash for Agents.md) also adds a virtual-shell lens: simulated shell environments can support agent experimentation, comparison tests, and safer examples, but they still need clear boundaries so a simulated command transcript is not mistaken for proof from the real repository or host.

The [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) adds governed workspace configuration signals for agent tools. Managed editor and CLI settings, workspace-level MCP server configuration, strict marketplace controls, permission modes, hooks, generated customization files, and debug logs should be reviewed as one tool-control surface rather than scattered personal preferences.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) and [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json) add shared-operation and session-forensics signals. Tools exposed through GUI commands and MCP should share the same tested operation path where possible, and coding-agent governance should record prompts, commands, MCP server activity, tool usage, skills, rules, and approval settings when those surfaces can affect code or external systems.

The [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json) adds MCP identity-interoperability and task-based access-control signals. MCP gateways should treat identity and authorization as runtime architecture: a tool call should carry user or trigger identity, agent identity, task scope, short-lived credential scope, quota or budget limit, and approval state. Broad standards and product background stays upstream; locally, MCP governance should reject broad standing credentials when the action should be scoped to one task.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) reinforces gateway-mediated MCP and agent-authentication practice. Centralized MCP registration, user-agent-task authorization, SSO or directory integration, audit logs, token custody, and per-tool deployment control are local governance criteria when teams expose developer tools through agents. Product comparisons stay upstream; locally, the rule is that a convenient local MCP configuration is not enough when tool calls need enforceable policy and reviewable identity evidence.

The [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json) adds an LLM gateway operating-control signal. Gateways are not only provider abstraction; in local practice they are policy and observability control planes for authentication, routing, rate limits, cost tracking, failover, and governance evidence across model and tool traffic.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) and [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json) add runtime-infrastructure and public-onboarding controls. Agent frameworks, RAG pipelines, vector stores, CLI installers, MCP entrypoints, and public setup instructions should be inventoried as tool surfaces with permissions, credential handling, logging, runtime separation, source provenance, and approval state before an agent uses them against code or enterprise data.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) and [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) add program-controlled tool, MCP trust, and public-sector service-tool signals. Programmatic tool calling should be treated as harness-mediated processing with its own schema, logging, policy, and intermediate-data controls rather than as ordinary model-only tool choice. MCP trust validation, interactive MCP authentication, app-server authentication, and public-sector read/write API examples reinforce that tool access needs configuration fingerprints, identity prompts, local testing, transport expectations, and domain-owner approval before an agent can use a server as a source of action.

The [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json) adds MCP least-privilege and interceptor signals. Tool governance should include capability scoping, argument validation, sandboxing, approval gates, runtime monitoring, and a common policy interception layer when several MCP servers or agent tools expose heterogeneous action surfaces. Broad MCP protocol and vendor background remains upstream-owned; locally, interception is useful only when it produces enforceable policy decisions and audit evidence before a tool call reaches code, data, or external systems.

The July 18-20 raw sources add approval visibility, API-safe evaluation, and connection-inventory controls. The [July 18 topic news collector source](../../../raw/processed/2026-07-18/ai-dev-wiki-topic-news-collector-2026-07-18T203453-0400.json) records API emulation for agent-skill evals and MCP connection inventory as local governance signals. The [July 19 topic news collector source](../../../raw/processed/2026-07-19/ai-dev-wiki-topic-news-collector-2026-07-19T203449-0400.json) reports tool-call approval prompts that hide SQL or command arguments as a control failure shape. The [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json) adds setup prompts, MCP installation, protocol-layer boundaries, subagent hooks, and explainable command review. Locally, tool approvals should expose material arguments, emulate costly or mutating APIs during evals, and inventory connections before trust is granted.

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) adds MCP specification and enterprise gateway evidence. MCP governance should account for stateless compatibility windows, logging placement, secret-scanning surfaces, filtered tool discovery, per-tool authorization, rate limits, OAuth or PRM support, deployment model, and audit evidence before connecting agents to enterprise tools.

The [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json) and [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json) add runtime tool-surface controls. MCP upgrades should be treated as compatibility and conformance gates, not just version bumps. Mid-conversation tool-list changes and fallback routing should be logged because they can alter cache assumptions, available actions, and which provider or safety path handled a request.

The [July 25 topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json) adds regulated-gateway, context-limit, and fallback-governance signals. MCP gateways for regulated workflows should be evaluated as centralized control planes for authentication, authorization, policy, audit logging, network boundaries, device posture, model routing, and private deployment evidence. Tool-specific MCP guidance also reinforces that bounded context is not complete dataset visibility: agents should route large-scale or complete operations through direct APIs or workflow tools with explicit data coverage checks. Runtime tool-surface mutation and automatic fallback routing should be logged because they change available actions, cache assumptions, and reproducibility.

The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) adds [progressive MCP tool discovery](progressive-mcp-tool-discovery.md) as a concrete context-budget and least-privilege pattern. This page keeps the governance boundary: discovered tools need policy evidence before invocation.

The [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) reinforces runtime governance for content agents. Permission blocking, label-based access, prompt-injection screening, audit trails, threshold alerts, and approval holds for high-impact actions belong in the tool-control layer, not only in prompt guidance.

The July 28 raw sources add cross-client and remote-skill tool governance evidence. The [topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json) records managed settings for plugins, marketplaces, approval bypasses, and model routing across agent clients, while the [leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) records MCP-discovered skills, token-limit controls, MCP diagnostics, and custom-agent routing as governed tool surfaces.

The July 29 raw sources add MCP migration and state-handle evidence. The [topic news collector source](../../../raw/processed/2026-07-29/ai-dev-wiki-topic-news-collector-2026-07-29T203119-0400.json) records stateless-core, OAuth-hardening, extension, migration-plan, elicitation, and explicit-state-handle implications for remote MCP practice, while the [leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json) reinforces remote skill package governance through MCP servers. Broad protocol details stay upstream; locally, protocol revisions should trigger conformance tests, session-dependence audits, explicit state externalization, approval review, and traceability updates before agents rely on changed servers.

## Practice Boundaries

- Describe tools with names, argument schemas, output contracts, and permission expectations.
- Validate tool arguments, user authority, workflow limits, and approval requirements before execution.
- Keep credentials in the harness, connector, or MCP server rather than exposing them in prompts.
- Log material tool requests, approvals, results, and failures when the workflow needs auditability.
- Prefer upfront retrieval when context is predictable and tool loops would add unnecessary cost.
- Use dynamic context tools when missing information is targeted and too large or uncertain for upfront context.
- Treat MCP servers as governed connectors, not as permission to bypass local approval rules.
- Record identity, policy, environment, approval, tool-call, and result evidence for high-impact agent tool use.
- Validate generated code or configuration outputs before they are accepted as tool results or committed artifacts.
- Default-deny high-impact MCP tools until policy, user scope, catalog change review, and audit logging are in place.
- Treat tool output and retrieved operational data as evidence, not as instructions that can expand agent authority.
- Record model routing or tool-provider routing metadata when it affects reproducibility, cost, or review evidence.
- Govern MCP server, plugin, and marketplace onboarding before they become available to agents.
- Apply untrusted-content handling to MCP-returned issue text, error reports, dependency metadata, and operational records, not only to open-web retrieval.
- Record plugin consent, permission denials, authentication notices, artifact hashes, and tool-log provenance when they affect trust or reproducibility.
- Require least privilege, explicit allowlists, data-boundary checks, audit trails, and approval gates for MCP tools that can change code, dependencies, infrastructure, or external records.
- Treat tool descriptions and MCP catalog metadata as live instructions that need review, provenance, and change detection before they reach acting agents.
- Govern IDE, CLI, cloud-agent, and marketplace tool availability with the same policy when they expose the same approved integration.
- Treat browser control, admin-capable remote MCP tools, and generated API-to-MCP surfaces as privileged tool categories that need allowlists, explicit approval, and auditable outcomes.
- Curate generated MCP tools for task fit, least privilege, schema clarity, and data exposure before allowing agents to use them.
- Treat browser observations as evidence that still needs permission bounds, allowed domains, and reproducible verification when decisions depend on live UI behavior.
- Govern build-aware context generation, language-server setup, and compile-command refreshes as retrieval tools whose outputs affect coding-agent confidence.
- Treat MCP server approval, tool descriptions, schema text, catalog entries, and routing records as auditable supply-chain inputs.
- Re-approve MCP tools when metadata, action scope, authentication, or returned-data authority changes.
- Pair governed data-access MCP tools with semantic definitions, source truth, and execution monitoring.
- Review tool-call, MCP, Bash-family, skill-adoption, and error-rate telemetry when maintaining the approved tool surface.
- Label simulated shell environments clearly and require real host verification before treating shell-like evidence as repository proof.
- Govern workspace MCP configuration, approved marketplaces, hooks, permission modes, generated customization files, and debug logs as auditable tool-surface changes.
- Require re-approval when an IDE or CLI exposes the same integration through a new managed setting, workspace file, or marketplace channel.
- Prefer one tested operation path for human UI commands and agent tool calls when both control the same system.
- Record prompts, commands, MCP activity, tool usage, skills, rules, and approval-setting changes as tool-surface evidence for high-impact coding-agent sessions.
- Require MCP gateways to preserve task, principal, agent, credential, quota, approval, and policy-decision evidence for delegated tool calls.
- Use task-scoped authorization for agent tool access when stable user, team, or service-account entitlements would grant more authority than the current task needs.
- Distinguish local MCP setup convenience from gateway-enforced access policy, identity, token custody, audit logs, and deployment control.
- Specify where user-agent-task authorization is enforced before a tool call reaches an external system.
- Treat LLM or AI gateways as governance control planes when they enforce authentication, routing policy, rate limits, cost telemetry, failover, and audit evidence.
- Avoid using provider abstraction as a substitute for explicit tool authority, data-boundary, and policy-decision records.
- Inventory agent frameworks, RAG stores, vector databases, CLI tools, and MCP entrypoints as active tool surfaces when they can affect code, credentials, or enterprise data.
- Require source provenance, install review, credential handling, logging, runtime separation, and approval state before public onboarding text can configure a tool for agent use.
- Treat programmatic tool orchestration as a governed harness path with schema, cache, intermediate-result, and logging controls separate from final model output.
- Validate MCP server trust through configuration fingerprints, authentication prompts, transport expectations, local test evidence, and domain-owner approval before enabling read/write service tools.
- Use capability scoping, argument validation, sandboxing, approval gates, runtime monitoring, and interception points for MCP or tool surfaces that can act across multiple systems.
- Keep common MCP policy enforcement close enough to execution that prompt injection, over-privileged tools, and untrusted tool output cannot bypass server-by-server review.
- Show material tool-call arguments, SQL, shell commands, target systems, and side effects before allow or deny decisions.
- Run conformance tests or equivalent compatibility checks before accepting MCP transport, session, elicitation, or logging-behavior changes.
- Log mid-conversation tool-list changes, fallback routing decisions, and cache-impact assumptions when they affect action availability or reproducibility.
- Use proxy or emulator-backed API evals for agent skills that would otherwise call live, costly, mutating, or nondeterministic services.
- Inventory MCP connections, setup prompts, subagent hooks, and protocol-layer boundaries before treating tool access as approved.
- Provide an explainable command-review path when side effects depend on shell or service-call semantics that are not obvious from the command text alone.
- Govern MCP servers as tools, resources, and prompts with separate controls for each primitive.
- Distinguish local developer convenience from enterprise MCP control planes that need role bundles, gateway logging, SCIM alignment, agent attribution, approval workflows, and agent-specific credentials.
- Expect stateless MCP calls, request metadata, cache hints, trace context, audited UI actions, and long-running task handles to require explicit state externalization and audit joins in the surrounding harness.
- Keep broad Model Context Protocol, MCP server, and vendor coverage upstream; maintain local MCP notes only when they change tool access, identity, approval, observability, or workflow design.
- Evaluate regulated MCP gateways as access infrastructure with identity, authorization, device posture, network, audit, routing, and deployment evidence rather than as connector catalogs.
- Require explicit data-coverage checks when an MCP-connected agent has bounded context and the task needs complete dataset operations.
- Route on-demand tool-schema selection through [progressive MCP tool discovery](progressive-mcp-tool-discovery.md) when large tool catalogs would waste context or expand action scope.
- Treat content-agent guardrails as runtime controls that can block actions, screen untrusted content, and hold high-impact operations for approval.
- Apply managed plugin, marketplace, approval-bypass, model-routing, token-limit, MCP diagnostic, and custom-agent policies consistently across IDE, CLI, app, cloud-agent, and remote-skill surfaces.
- Treat remote MCP skills as governed tool packages whose publisher, archive bounds, allowed tool scope, approval defaults, and diagnostics need review before use.
- Treat MCP protocol revisions as deployment lifecycle events that require conformance evidence, state-handle review, migration plans, approval checks, and updated audit joins.

## Authoritative Sources

- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [federation.md](../federation.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [RAG provenance ranking and chunking](rag-provenance-ranking-and-chunking.md)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json)
- [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json)
- [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json)
- [FastMCP research source](../../../raw/processed/project-wiki-research-2026-07-01-fastmcp.md)
- [July 2 topic news collector source](../../../raw/processed/2026-07-02/ai-dev-wiki-topic-news-collector-2026-07-02T203134-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json)
- [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json)
- [Just Bash clipping](../../../raw/processed/vercel-labsjust-bash Bash for Agents.md)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json)
- [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)
- [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)
- [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json)
- [July 18 topic news collector source](../../../raw/processed/2026-07-18/ai-dev-wiki-topic-news-collector-2026-07-18T203453-0400.json)
- [July 19 topic news collector source](../../../raw/processed/2026-07-19/ai-dev-wiki-topic-news-collector-2026-07-19T203449-0400.json)
- [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json)
- [July 22 topic news collector source](../../../raw/processed/2026-07-22/ai-dev-wiki-topic-news-collector-2026-07-22T203140-0400.json)
- [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json)
- [July 24 leaf update watch source](../../../raw/processed/2026-07-24/ai-dev-wiki-leaf-update-watch-2026-07-24T210141-0400.json)
- [July 25 topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json)
- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 29 topic news collector source](../../../raw/processed/2026-07-29/ai-dev-wiki-topic-news-collector-2026-07-29T203119-0400.json)
- [July 29 leaf update watch source](../../../raw/processed/2026-07-29/ai-dev-wiki-leaf-update-watch-2026-07-29T210208-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [retrieval-and-tools](index.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [agent identity and delegated authority](../governance-and-risk/agent-identity-and-delegated-authority.md)
- [trajectory-level agent evaluation](../verification-and-evals/trajectory-level-agent-evaluation.md)
- [progressive MCP tool discovery](progressive-mcp-tool-discovery.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-07-23 with stateless MCP, gateway-selection, filtered discovery, per-tool authorization, logging, and secret-scanning guidance.
- Created on 2026-06-23 to hold dynamic context, action-tool, and MCP governance practice.
- Maintained on 2026-06-23 with public governed-MCP and runtime agent governance signals.
- Maintained on 2026-06-24 with MCP gateway policy, untrusted tool-output, and routing-aware evidence requirements.
- Maintained on 2026-06-25 with marketplace onboarding and MCP-returned content as explicit tool-governance boundaries.
- Maintained on 2026-06-26 with plugin consent, permission-denial evidence, deterministic control-plane artifacts, and tamper-evident tool logs.
- Maintained on 2026-06-27 with MCP least-privilege, allowlist, audit, data-boundary, and approval-gate practice.
- Maintained on 2026-07-01 with tool-description poisoning, Team MCP catalog, organization-scope, and native agent command-surface governance.
- Maintained on 2026-07-01 with browser-tool, admin-capable remote MCP, and generated API-to-MCP curation boundaries.
- Maintained on 2026-07-02 with browser-observation evidence controls and build-aware context-generation governance.
- Maintained on 2026-07-04 with trusted MCP catalogs, tool-description change control, routing evidence, and governed semantic data access.
- Maintained on 2026-07-06 with tool and skill telemetry plus simulated shell evidence boundaries.
- Maintained on 2026-07-08 with managed workspace MCP configuration, marketplace, hook, permission-mode, and debug-log governance.
- Maintained on 2026-07-09 with shared GUI-and-agent operation paths, session forensics, and generated customization evidence.
- Maintained on 2026-07-10 with MCP identity interoperability and task-scoped access-control evidence.
- Maintained on 2026-07-11 with gateway-mediated MCP access, agent-authentication enforcement, token custody, and audit-log criteria.
- Maintained on 2026-07-12 with LLM gateway governance controls for authentication, routing, rate limits, cost, failover, and audit evidence.
- Maintained on 2026-07-13 with RAG infrastructure, CLI/MCP onboarding, runtime separation, credential handling, and public setup approval controls.
- Maintained on 2026-07-14 with programmatic tool orchestration, MCP trust validation, authentication, and governed service-tool controls.
- Maintained on 2026-07-22 with MCP primitive controls, gateway auditability, agent attribution, trace context, and task-handle governance.
- Maintained on 2026-07-15 with MCP least privilege, argument validation, runtime monitoring, approval gates, and common policy interception controls.
- Maintained on 2026-07-22 with visible tool-call arguments, API-safe skill evals, MCP inventories, setup-prompt review, subagent-hook checks, and explainable command approval.
- Maintained on 2026-07-24 with MCP conformance, mid-conversation tool-surface, fallback-routing, and cache-assumption guidance.
- Maintained on 2026-07-25 with regulated MCP gateway criteria, bounded-context data-coverage checks, and fallback/tool-surface audit guidance.
- Maintained on 2026-07-27 with progressive MCP discovery, field-scope, managed-OAuth, API-log, and content-agent guardrail guidance.
- Maintained on 2026-07-28 with cross-client managed plugin, marketplace, approval-bypass, model-routing, token-limit, MCP diagnostic, custom-agent, and remote-skill controls.
- Maintained on 2026-07-29 with MCP protocol migration, explicit state-handle, conformance, approval, and audit-join guidance.
