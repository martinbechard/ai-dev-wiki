---
type: "Adoption And Operating Model"
title: "Workflow Before Model Selection"
description: "Workflow before model selection means the team chooses the work shape before standardizing on a model, coding assistant, or harness."
tags: ["adoption-and-operating-model"]
---

# Workflow Before Model Selection

## Current Understanding

Workflow before model selection means the team chooses the work shape before standardizing on a model, coding assistant, or harness. The useful first questions are autonomy level, context sources, allowed tools, approval points, verification expectations, and evidence required for completion.

The [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md) and [gen AI application deck](../../../raw/processed/gen-ai-app-complete.md) separate models, harnesses, and workflows. A model supplies capability, a harness decides how that capability reaches files and tools, and a workflow decides how the work is oriented, planned, edited, tested, reviewed, and handed back.

This operating rule keeps model choice from becoming a shortcut around process design. Model routing, product selection, and build-versus-buy decisions remain downstream of the workflow requirement.

The [leaf update watch source](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json) reinforces this rule from public coding-agent comparisons and loop-design sources: there is no single best agent outside the work shape, governance requirement, review burden, cost profile, and delivery goal. Leaderboards and product lists are upstream ecosystem material; the local decision is whether a workflow needs automation loops, worktrees, subagents, connectors, review gates, or a smaller human-led assist pattern.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) add delegated-work signals: longer-horizon agent tasks, default coding-agent use, and platform-level agent adoption make supervision, context discipline, approval gates, and progress visibility part of the workflow definition. Broad OpenAI, Codex, GitHub Copilot, Microsoft, and Linear coverage stays upstream; the local rule is to define delegation thresholds and operating controls before picking the assistant surface.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) adds model and tooling administration signals. Low-latency coding models, review depth defaults, worktree support, and assisted merge or conflict workflows are becoming configurable platform settings. The local rule is to treat those settings as workflow policy, cost, and review-depth decisions rather than individual developer preferences.

The [Affordable AI Agents source](../../../raw/processed/The Affordable AI Agents.md) adds a hosting and routing lens. The workflow definition should identify whether a task is exploratory, high-frequency automation, premium review, background debugging, or local-only execution before selecting a model or infrastructure path. Hosting choices belong downstream of the same workflow analysis because managed APIs, subscriptions, self-hosted clusters, and workstation inference change cost, latency, telemetry, staffing, and auditability.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) and [June 27 leaf update watch source](../../../raw/processed/2026-06-27/ai-dev-wiki-leaf-update-watch-2026-06-27T210128-0400.json) add two routing checks. First, delegated task execution needs delegation boundaries, review checkpoints, escalation paths, and intervention modes before a model or remote-agent surface is selected. Second, multi-model coding environments need task-fit evals and organization defaults, not a single global assistant policy.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) adds pricing, context, and governance as workflow inputs. Seat models, usage packaging, context-window limits, hook support, permission controls, data-control boundaries, and verification costs should be mapped before selecting a coding assistant or agent mode. Broad product pricing belongs upstream; locally, those constraints decide whether the workflow should be chat assist, delegated task, background automation, self-hosted execution, or human-led review.

The [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) adds IDE-native agent and model-update signals. Agent picker defaults, native versus protocol-based integration, authentication path, command availability, reasoning depth, and model availability are workflow settings. They should trigger local task-fit evals and operating-policy review before a team expands delegation or changes defaults.

The [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json) adds task-routed model selection and multimodal context signals. Auto model selection, prompt-cache behavior, reasoning depth, CLI task features, browser-tool verification, image or PDF attachments, and IDE-native agent availability should be evaluated against the workflow before becoming defaults. A team should know when to rely on auto routing, when to pin a model for repeatability, and when visual or browser context is allowed by data and evidence rules.

The [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json) adds workflow-readiness and tool-selection signals. Agent workflows need trusted data, permissions, connected systems, citations, logging, approval checkpoints, state memory, and handoff shape before model or product choice. Coding-agent selection should account for editor fit, runtime constraints, model routing, multi-agent workspace support, and cost transparency as workflow surfaces rather than product rankings.

The [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json) and [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md) add procurement and channel-workflow inputs. Enterprise coding-agent rollout should first answer identity, audit, retention, residency, deployment, support, and evidence requirements. Chat-agent workflows should also decide which channel events matter, when the bot subscribes to a thread, what state store is required, and which responses can be streamed or posted back before choosing a platform or model route.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) adds admin-enabled model routing, repository overview generation, and modernization workflow packages. Workflow selection should decide when a source-backed repository orientation is sufficient, when a stronger model route is justified by task risk or context size, and when a specialized multi-agent modernization workflow needs its own gates, roles, and cost evidence.

The [July 10 leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json) adds agent-provider, managed-settings, and cost-shape signals. Workflow selection should decide whether a task needs IDE-native execution, cloud agent execution, managed settings, persistent workspace state, or a lighter human-led assist pattern before adopting a provider route. Cost analyses should influence the workflow shape only when they are tied to context depth, tool use, retries, verification work, and accepted outcomes.

The [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json) adds engineering-leader literacy as a workflow-selection input. Leaders need enough practical AI-assisted development literacy to judge reliability, hallucination management, governance evidence, evaluation results, and rollout risk before procurement or autonomy defaults are treated as team policy.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) adds adoption-pressure, regulated lifecycle, and modernization-package signals. Workflow selection should decide whether a team is running an experiment, a mandated rollout, a regulated delivery cycle, or a specialized modernization package before choosing tools; each shape needs different review capacity, standards, verification gates, cost telemetry, and human escalation.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) and [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) add shared-capability, service-delivery, and multi-repository workflow signals. Teams should decide whether the workflow needs centrally funded identity, trusted connectors, curated knowledge, evaluations, observability, model routing, reusable agent patterns, domain-expert-owned MCP servers, or multi-repository workspaces before standardizing the model or desktop surface.

The July 18-21 raw sources reinforce workflow selection as routing design. The [July 18 topic news collector source](../../../raw/processed/2026-07-18/ai-dev-wiki-topic-news-collector-2026-07-18T203453-0400.json) and [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json) tie coding-assistant workflows to reusable skills, read-only repository research, task-appropriate models, setup-prompt governance, durable instruction scope, and context-continuity architecture. The [Codex ultra-mode clipping](../../../raw/processed/what does theo have to say about Codex ultra mode.md) adds a cost-control lesson: high-effort or multi-agent modes should be selected by task decomposition, risk, and verification need, not as a blanket default.

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) adds regulated-industry scaling and benchmark-selection evidence. Workflow selection should choose task privilege, workspace isolation, validation loop, platform observability, and workflow-fit evals before selecting a coding model or accepting aggregate leaderboard scores.

The [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json) and [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json) add agent-selection and routing-control evidence. Teams should select the agent surface from the intended supervision model and audit posture before comparing product popularity.

The July 31 raw sources add budget, benchmark, model-policy, and runtime-placement signals. The [leaf update watch source](../../../raw/processed/2026-07-31/ai-dev-wiki-leaf-update-watch-2026-07-31T210319-0400.json) records spend wallets, tokenmaxxing cautions, PR-state differences, sponsored local-infrastructure positioning, and embedded senior execution capacity. The [topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json) records model-policy toggles and autonomous testing controls. Locally, these are workflow-selection inputs, not product defaults: the team should choose the supervision surface, budget envelope, runtime placement, and acceptance evidence before selecting model routes, autonomous test execution, or local-versus-cloud infrastructure.

The [August 4 topic news collector source](../../../raw/processed/2026-08-04/ai-dev-wiki-topic-news-collector-2026-08-04T203217-0400.json) adds generated-app retirement and inference-provider replacement signals. Agent-built application workflows should define exportability, source ownership, managed inference inventories, provider replacement paths, and deprecation review before selecting a builder surface or hosted inference route. Product lifecycle details stay upstream; locally, the workflow needs a survivable source and dependency plan before generated apps become team assets.

The [model-cost benchmark clipping](../../../raw/processed/cheapest-model-per-run-most-expensive-per-real-fix.md) adds a model-routing caution for tool-heavy workflows. Token price is not a sufficient selection criterion when the task depends on repeated benchmark, database, browser, search, or verifier calls, and benchmark success is not enough when the agent can satisfy the measured prompt by changing the workload boundary. Workflow selection should define the accepted fix class, tool-call budget, freshness expectations, and review method before comparing models.

The [August 11 topic news collector source](../../../raw/processed/2026-08-11/ai-dev-wiki-topic-news-collector-2026-08-11T203048-0400.json) adds model-lifecycle governance evidence. New coding models can be default-off enterprise policies, visible across several assistant surfaces, and paired with replacement deadlines for retired models. Locally, model availability should trigger surface inventory, rollout criteria, dependency checks, cost telemetry review, and replacement verification before administrators enable or retire a route for recurring workflows.

The August 12 raw sources add agent-package, usage-metric, ROI, realistic-work-environment, and coding-agent comparison evidence. The [topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json) and [leaf update watch source](../../../raw/processed/2026-08-12/ai-dev-wiki-leaf-update-watch-2026-08-12T210257-0400.json) reinforce that workflow selection should evaluate portability, package governance, review effort, agent activity metrics, cost-to-output assumptions, realistic task environments, review capacity, and workflow fit before standardizing one assistant surface or model family.

The August 13 raw sources add workforce-role, audit-harness, operational-data, and persistent-project-state signals. The [topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json) suggests that workflow selection should include senior review load, AI-evaluation work, production debugging, operational-data exposure, audit-event design, and persistent project state before selecting a coding-agent surface. The [leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json) adds agent activity metrics, ROI dashboards, managed-agent controls, workspace identity, and product status incidents as operating inputs rather than product-selection shortcuts.

The August 14 raw sources add model-policy, plugin-supervision, environment-readiness, and provider-status inputs. The [topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json) records administrator-off-by-default model policies, provider-billed routing, portable plugin management, queued agent work, pinned prompts, rewind recovery, and hosted service incidents. The [leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json) records cloud-agent builds, prior-work reconstruction, incident reporting, repository/tool trust risk, and purpose-based behavioral monitoring. Locally, workflow selection should decide policy enablement, cost ownership, plugin supervision, environment provenance, continuity, and contingency handling before a model or hosted agent route becomes a team default.

The August 15 raw sources add rollout and self-hosting constraints. The [topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json) records admin-gated coding-model availability, self-hosted software-factory deployment choices, file-backed planning packages, and runtime AI gateway controls. The [leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) reinforces that production agent workflows need durable execution, scoped access, runtime containment, behavior baselines, and governance drills. Locally, workflow selection should decide model enablement, spend owner, execution location, inference route, egress policy, retained evidence, and first workflow before adopting a new agent or factory surface.

The August 26 raw sources add model-policy and coding-agent comparison evidence. The [topic news collector source](../../../raw/processed/2026-08-27/ai-dev-wiki-topic-news-collector-2026-08-27T003207Z.json) records GitHub global model policy behavior for default inheritance, preserved explicit choices, open-weight or data-retaining model defaults, and rollout timing, plus secondary comparison evidence about platforms, pricing, autonomy, visual workspaces, parallel agents, worktrees, and approval gates. The [leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json) adds workspace administration and usage-limit review signals. Locally, workflow selection should treat model availability as an enterprise policy object and compare coding-agent surfaces by workflow fit, not generic product rank.

The [August 23 topic news collector source](../../../raw/processed/2026-08-23/ai-dev-wiki-topic-news-collector-2026-08-24T003154Z.json) adds workflow-selection evidence from project-context, enterprise-agent, agent-news, and tool-stack sources. The reusable local signal is that long-horizon agent reliability depends on memory, tool use, feedback, supervision, governance, execution environment, observability, and evaluation budget, not model capability or product ranking alone.

The August 28 and 29 raw sources add workflow redesign, policy, and prototype-to-deployment evidence. The [topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) records signals that AI-native operating models redesign workflows, decisions, governance, and orchestration before tool selection, while managed coding-agent policy changes make retention, billing, sandboxing, review effort, and model or chat policy defaults workflow inputs. The [leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json) reinforces that harness choice, workspace layer, durable execution, and operating ownership should precede product or model comparisons.

The [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-30T003150Z.json) adds workflow-selection inputs:

- Shared custom agents and effort controls should be treated as organization defaults, not just local preferences.
- Cross-app session recovery should be evaluated when a workflow crosses IDE, chat, and application surfaces.
- Formal verification and cost-per-accepted-change routing should be considered before a model, assistant, or IDE integration becomes the default.

The August 30 raw sources add selection criteria from public agent TDD, asynchronous coding-agent workspaces, self-hosting, and assistant comparisons. The [topic news collector source](../../../raw/processed/2026-08-30/ai-dev-wiki-topic-news-collector-2026-08-31T003307Z.json) treats tool comparisons as workflow-fit evidence rather than product rankings, while the [leaf update watch source](../../../raw/processed/2026-08-30/ai-dev-wiki-leaf-update-watch-2026-08-30T210135-0400.json) reinforces that persistent, self-hosted, and skill-driven agents need operating decisions before tool choice.

The August 31 raw sources add execution-boundary, control-layer, and adoption-framework evidence. The [leaf update watch source](../../../raw/processed/2026-08-31/ai-dev-wiki-leaf-update-watch-2026-08-31T210122-0400.json) records coding-agent comparisons by editor-first, terminal, cloud-delegation, and manager-layer fit, plus enterprise control-layer evidence for model-routing policy, workflow versions, run artifacts, outcomes, and provenance. The [topic news collector source](../../../raw/processed/2026-08-31/ai-dev-wiki-topic-news-collector-2026-09-01T003223Z.json) records adoption-framework coverage for workforce readiness, operating models, governance, code review, testing, requirements, quality controls, and team responsibilities. Locally, assistant choice should follow execution boundary, isolation, approval, review, provenance, and adoption measurement requirements rather than generic product rank.

## Practice Boundaries

- Choose the workflow shape before choosing the model or assistant product.
- Define the level of autonomy and the human review points before delegation begins.
- Use model choice as a harness design decision when the workflow requires different cost, latency, context, or verification behavior.
- Link per-workflow use, compose, or build decisions to [use-compose-build-workflow-selection.md](../agent-workflows/use-compose-build-workflow-selection.md).
- Compare agents by workflow fit, governance fit, review burden, context requirements, and measurable delivery impact before product preference.
- Treat recurring loops as a workflow design choice with state, budget, and validation requirements.
- Distinguish short assistant use from delegated work that needs task slicing, progress review, run evidence, and explicit supervision.
- Decide model enablement, review depth, assisted conflict handling, and workspace isolation according to the workflow's risk, cost, latency, and verification needs.
- Decide hosting and routing according to workflow frequency, autonomy, context footprint, latency tolerance, governance requirements, and total operating cost.
- Define delegation boundaries, review checkpoints, escalation paths, and intervention modes before selecting remote-agent or long-running execution surfaces.
- Use task-fit evaluation and organization-level defaults when several coding models or assistant modes are available.
- Map pricing model, feature gates, context limits, hook support, data-control boundaries, and verification cost before choosing an assistant surface.
- Treat IDE-native agents, protocol-based agents, authentication paths, command surfaces, reasoning-depth controls, and model upgrades as workflow-policy inputs.
- Rerun representative local coding, terminal, browser, and verification tasks before changing autonomy defaults for a new model or assistant surface.
- Decide when auto model selection is acceptable and when repeatability, cost, data policy, or review depth requires a pinned route.
- Include browser-driven verification and multimodal input handling in workflow selection when the task depends on rendered UI, PDFs, screenshots, or live applications.
- Require workflow-readiness checks for data access, permissions, citations, logging, approval checkpoints, state memory, and handoffs before selecting an agent surface.
- Compare coding-agent tools by editor fit, runtime shape, model-routing controls, multi-agent workspace support, and cost transparency against the intended workflow.
- Add enterprise identity, audit, retention, residency, deployment, support, and evidence needs to workflow selection before coding-agent procurement expands.
- Define collaboration-channel triggers, subscriptions, state, tool scope, and response posting rules before selecting a chat-agent toolkit.
- Verify repository-overview outputs against authoritative files before treating them as project knowledge or onboarding evidence.
- Route admin-enabled models by task risk, context size, autonomy level, cost envelope, and verification burden rather than developer preference alone.
- Treat specialized multi-agent modernization packages as workflow definitions with explicit roles, gates, evidence, and cost telemetry.
- Choose IDE-native, CLI, cloud-agent, or human-led assist surfaces from the required state, settings, permissions, latency, and handoff evidence.
- Use cost-shape evidence to redesign context depth, tool loops, retry strategy, or verification scope before treating model choice as the primary lever.
- Treat leader enablement, reliability vocabulary, hallucination controls, governance evidence, and evaluation literacy as prerequisites for scaling agentic SDLC workflows.
- Distinguish experiments, peer-driven adoption, mandated rollout, regulated delivery, and legacy modernization packages before selecting tools or model routes.
- Match each workflow shape to review capacity, lifecycle standards, verification gates, cost telemetry, and escalation paths.
- Identify shared platform capabilities, domain-owned service tools, and multi-repository workspace needs before selecting a model, assistant surface, or agent desktop.
- Treat public-sector or service-delivery MCP examples as workflow-grounding evidence, not as permission to expose broad read/write APIs without domain-owner approval.
- Treat high-effort reasoning, subagent fan-out, setup prompts, reusable skills, and context-continuity layers as workflow choices that need cost, risk, and verification criteria before they become defaults.
- Treat model availability inside a coding assistant as a rollout-control event: capture admin enablement, reasoning-effort controls, parallel tool-use behavior, pricing mode, and fallback route before standardizing the workflow.
- Prefer workflow architecture, observability, control points, and task-state durability over marketing claims when deciding whether a process needs static automation, a bounded agent, or a long-running managed agent.
- Compare IDE-supervised, terminal-loop, Git-controlled, cloud, voice-steered, asynchronous, and human-led surfaces by supervision channel and source-control evidence.
- Review permission prompts, network exposure, generated instruction setup, model-router policy, cost transparency, and auditability before adopting open-source, commercial, or voice-steered tools.
- Use budget envelopes, PR-state normalization, runtime-placement constraints, model-policy toggles, and human-supervised test controls as workflow requirements before comparing model or agent products.
- Treat embedded senior execution capacity as a workflow shape when production AI systems need domain ownership, customer-context translation, and launch accountability.
- Require generated-app export paths, source ownership, managed inference inventories, and provider replacement plans before adopting a builder surface for durable work.
- Treat product or inference-provider deprecation as a workflow-selection input, not only a procurement or vendor-news issue.
- Define accepted fix classes, tool-call budgets, freshness requirements, and patch-review expectations before selecting a model for optimization or verifier-heavy tasks.
- Treat low token price as a workflow input only after tool-call discipline, accepted outcome rate, and review burden are measured.
- Treat model enablement, deprecation, and replacement as workflow-lifecycle events that need surface inventory, admin policy, dependent-workflow mapping, cost checks, and local verification before defaults change.
- Treat portable plugin availability, agent activity metrics, review-effort controls, ROI dashboards, and realistic work-environment evidence as workflow inputs that need local task fit and governance review before adoption expands.
- Include review-capacity, AI-evaluation staffing, production-debugging ownership, audit-event design, operational-data exposure, persistent project state, managed-agent controls, and incident history before selecting a recurring agent workflow.
- Treat administrator-off-by-default models, provider-billed routes, portable plugin management, queued work, pinned prompts, rewind recovery, prebuilt environments, prior-work history, provider status, repository/tool trust, and behavioral baselines as workflow-selection inputs before enabling a recurring agent route.
- Treat new coding-model availability, self-hosted factory setup, file-backed planning packages, runtime gateways, durable execution, scoped access, and behavior baselines as workflow-selection inputs before expanding long-horizon agent delegation.
- Record global model defaults, explicit overrides, data-retention exceptions, open-weight model policy, rollout timing, workspace administration, and usage-limit review before standardizing a coding-agent workflow.
- Compare coding-agent surfaces by platform fit, visual or terminal workspace shape, parallel-agent support, worktree behavior, approval gates, pricing, and autonomy boundary against the intended workflow.
- Budget memory, retrieval, tool governance, observability, evaluation, feedback, supervision, and execution-environment evidence as first-order workflow-selection inputs before comparing model capability.
- Review retention, billing, sandboxing, review effort, policy defaults, workspace layer, and prototype-to-deployment trust gates as workflow-selection inputs before standardizing a coding assistant or managed agent route.
- Evaluate shared-agent catalogs, effort defaults, session recovery, formal-verification needs, and cost-per-accepted-change metrics before standardizing an assistant surface or model route.
- Compare coding-agent surfaces by setup surface, editor fit, runtime location, model/provider flexibility, privacy mode, self-hosting option, review workflow, approval mode, and team policy controls.
- Decide persistence, self-hosting, reusable skills, permissions, memory, eval loops, and infrastructure requirements before turning an assistant comparison into a team default.
- Compare assistant and manager layers by execution location, workspace isolation, approval flow, review surface, scheduling, monitoring, provenance, and adoption-measurement requirements before selecting a model or product route.

## Authoritative Sources

- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-30T003150Z.json)
- [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json)
- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [Leaf Update Watch](../source-workflows/leaf-update-watch.md) source: [raw artifact](../../../raw/processed/2026-06-23/ai-dev-wiki-leaf-update-watch-2026-06-23T210209-0400.json)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [Affordable AI Agents source](../../../raw/processed/The Affordable AI Agents.md)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [June 27 leaf update watch source](../../../raw/processed/2026-06-27/ai-dev-wiki-leaf-update-watch-2026-06-27T210128-0400.json)
- [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json)
- [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json)
- [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json)
- [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json)
- [July 6 topic news collector source](../../../raw/processed/2026-07-06/ai-dev-wiki-topic-news-collector-2026-07-06T203053-0400.json)
- [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 10 leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json)
- [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)
- [July 18 topic news collector source](../../../raw/processed/2026-07-18/ai-dev-wiki-topic-news-collector-2026-07-18T203453-0400.json)
- [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json)
- [Codex ultra-mode clipping](../../../raw/processed/what does theo have to say about Codex ultra mode.md)
- [July 22 topic news collector source](../../../raw/processed/2026-07-22/ai-dev-wiki-topic-news-collector-2026-07-22T203140-0400.json)
- [July 22 leaf update watch source](../../../raw/processed/2026-07-22/ai-dev-wiki-leaf-update-watch-2026-07-22T210121-0400.json)
- [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json)
- [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json)
- [July 31 topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json)
- [July 31 leaf update watch source](../../../raw/processed/2026-07-31/ai-dev-wiki-leaf-update-watch-2026-07-31T210319-0400.json)
- [August 4 topic news collector source](../../../raw/processed/2026-08-04/ai-dev-wiki-topic-news-collector-2026-08-04T203217-0400.json)
- [Model-cost benchmark clipping](../../../raw/processed/cheapest-model-per-run-most-expensive-per-real-fix.md)
- [August 11 topic news collector source](../../../raw/processed/2026-08-11/ai-dev-wiki-topic-news-collector-2026-08-11T203048-0400.json)
- [August 12 topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json)
- [August 12 leaf update watch source](../../../raw/processed/2026-08-12/ai-dev-wiki-leaf-update-watch-2026-08-12T210257-0400.json)
- [August 13 topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json)
- [August 13 leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json)
- [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json)
- [August 14 leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json)
- [August 15 topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json)
- [August 27 topic news collector source](../../../raw/processed/2026-08-27/ai-dev-wiki-topic-news-collector-2026-08-27T003207Z.json)
- [August 23 topic news collector source](../../../raw/processed/2026-08-23/ai-dev-wiki-topic-news-collector-2026-08-24T003154Z.json)
- [August 30 leaf update watch source](../../../raw/processed/2026-08-30/ai-dev-wiki-leaf-update-watch-2026-08-30T210135-0400.json)
- [August 30 topic news collector source](../../../raw/processed/2026-08-30/ai-dev-wiki-topic-news-collector-2026-08-31T003307Z.json)
- [August 31 leaf update watch source](../../../raw/processed/2026-08-31/ai-dev-wiki-leaf-update-watch-2026-08-31T210122-0400.json)
- [August 31 topic news collector source](../../../raw/processed/2026-08-31/ai-dev-wiki-topic-news-collector-2026-09-01T003223Z.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption operating agreements](adoption-operating-agreements.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [use compose build workflow selection](../agent-workflows/use-compose-build-workflow-selection.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [agent cost telemetry](agent-cost-telemetry.md)
- [hybrid agent infrastructure economics](hybrid-agent-infrastructure-economics.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-08-31 with execution-boundary, manager-layer, model-routing-policy, workflow-provenance, workforce-readiness, governance, quality-control, and adoption-measurement evidence.
- Maintained on 2026-08-29 with shared custom-agent, effort-control, policy-convergence, formal-verification, session-recovery, and subagent-economics workflow-selection evidence.
- Maintained on 2026-08-29 with AI-native workflow redesign, managed policy, review-effort, retention, billing, sandbox, workspace-layer, and prototype-to-deployment selection inputs.
- Maintained on 2026-08-30 with setup-surface, editor-fit, runtime-location, model-flexibility, privacy, self-hosting, review, approval, team-policy, persistence, skill, memory, eval, and infrastructure selection criteria.
- Maintained on 2026-07-23 with regulated scaling, task-scoped privilege, platform observability, and workflow-fit eval selection guidance.
- Created on 2026-06-23 from source-backed workflow, harness, and model-selection guidance.
- Maintained on 2026-06-23 with public coding-agent selection guidance focused on workflow fit, governance burden, and loop design.
- Maintained on 2026-06-25 with delegated-work operating model signals for supervision, context discipline, progress visibility, and approval gates.
- Maintained on 2026-06-26 with model-policy, review-depth, worktree, and assisted-conflict workflow controls.
- Maintained on 2026-06-27 with hosting and routing as workflow-level operating decisions.
- Maintained on 2026-06-27 with delegation, intervention-mode, and multi-model routing checks.
- Maintained on 2026-06-28 with pricing, context-window, hook, data-control, and verification-cost inputs to workflow selection.
- Maintained on 2026-07-01 with IDE-native agent surfaces, command routing, authentication path, reasoning-depth, and model-upgrade eval triggers.
- Maintained on 2026-07-01 with auto model routing, prompt-cache, browser-tool, and multimodal context inputs to workflow selection.
- Maintained on 2026-07-02 with workflow-readiness checks, editor/runtime fit, model-routing controls, multi-agent workspace support, and cost transparency.
- Maintained on 2026-07-06 with enterprise procurement readiness and collaboration-channel workflow selection inputs.
- Maintained on 2026-07-09 with repository-overview verification, admin-enabled model routing, and specialized modernization workflow package criteria.
- Maintained on 2026-07-10 with agent-provider routing, managed settings, persistent-state, and cost-shape workflow inputs.
- Maintained on 2026-07-12 with engineering-leader AI literacy, reliability, governance evidence, and rollout-risk inputs to workflow selection.
- Maintained on 2026-07-13 with experiment, mandate, regulated lifecycle, and modernization-package workflow distinctions.
- Maintained on 2026-07-14 with shared-capability, domain-owned MCP service-tool, and multi-repository workspace inputs to workflow selection.
- Maintained on 2026-07-22 with high-effort routing, setup-prompt governance, reusable-skill, and context-continuity workflow inputs.
- Maintained on 2026-07-22 with model rollout-control, reasoning-effort, parallel tool-use, architecture, and observability selection signals.
- Maintained on 2026-07-26 with supervision-surface, permission, network-exposure, model-routing, voice-steering, and auditability selection criteria.
- Maintained on 2026-07-31 with budget-envelope, PR-state normalization, runtime-placement, model-policy, autonomous-testing, and embedded execution-capacity workflow inputs.
- Maintained on 2026-08-04 with generated-app exportability, managed-inference inventory, and provider-replacement workflow inputs.
- Maintained on 2026-08-05 with verifier-heavy model selection, accepted-fix classes, and tool-call budget guidance.
- Maintained on 2026-08-11 with model-enable, model-deprecation, replacement-deadline, surface-inventory, and rollout-verification workflow governance.
- Maintained on 2026-08-12 with portable package, usage-metric, ROI, realistic-work-environment, and workflow-fit selection inputs.
- Maintained on 2026-08-13 with workforce-role, audit-harness, operational-data, persistent-project-state, managed-agent, workspace-identity, and incident-history workflow inputs.
- Maintained on 2026-08-14 with model-policy, provider-billing, plugin-supervision, queued-work, pinned-prompt, rewind, environment-provenance, prior-work-history, provider-status, repository/tool-trust, and behavior-baseline workflow inputs.
- Maintained on 2026-08-15 with model rollout, self-hosted factory setup, runtime gateway, durable-execution, scoped-access, evidence-retention, and behavior-baseline workflow inputs.
- Maintained on 2026-08-26 with global model policy defaults, explicit overrides, data-retention exceptions, workspace administration, usage-limit review, and workflow-specific coding-agent comparison criteria.
- Maintained on 2026-08-23 with memory, tool-use, feedback, supervision, governance, execution-environment, observability, and evaluation-budget workflow-selection inputs.
