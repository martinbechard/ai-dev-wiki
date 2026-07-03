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

## Authoritative Sources

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
