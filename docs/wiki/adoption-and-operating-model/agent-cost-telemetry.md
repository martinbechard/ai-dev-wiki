---
type: "Adoption And Operating Model"
title: "Agent Cost Telemetry"
description: "Agent cost telemetry tracks model and tool consumption at the workflow level so teams can decide whether an agent loop is useful, wasteful, or mis-scoped."
tags: ["adoption-and-operating-model"]
---

# Agent Cost Telemetry

## Current Understanding

Agent cost telemetry tracks model and tool consumption at the workflow level so teams can decide whether an agent loop is useful, wasteful, or mis-scoped. The local pattern is to measure cost by run, step, model, tool loop, subagent fan-out, context growth, and outcome instead of treating a monthly spend cap as the only control.

The [tokenomics source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) argues that coding-agent spend should be traced by session, step, model, and outcome, and that more token use does not automatically mean better engineering results. Broad vendor, product, and company coverage belongs upstream; this page owns the local operating-model implication.

Cost telemetry is not only finance reporting. It is feedback for workflow design: a loop that repeatedly expands context, calls tools without new evidence, or fans out subagents without acceptance criteria should be redesigned before it becomes a standing automation.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) adds two adoption-measurement signals. Usage-based model enablement should be tied to workflow value, and adoption reports should pair usage by cohort with outcome measures such as merge throughput, review quality, and acceptance evidence. Product-specific reporting belongs upstream; locally, adoption telemetry is useful only when it changes a workflow decision.

The [Affordable AI Agents source](../../../raw/processed/The Affordable AI Agents.md) adds an infrastructure-economics signal. Autonomous loops make cost scale with every context injection, tool call, retry, and background run, so telemetry should expose marginal spend before monthly invoices become the first warning. Managed APIs, enterprise subscriptions, self-hosted capacity, and local execution each need the same workflow-level cost and outcome evidence before they can be compared honestly.

The [June 27 leaf update watch source](../../../raw/processed/2026-06-27/ai-dev-wiki-leaf-update-watch-2026-06-27T210128-0400.json) and [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) add accountability and context-budget signals. Cost tracking should attribute spend to agent owner, workflow, data sources, permission scope, threshold, and outcome so teams can review autonomous spend as an operating decision rather than an unexplained token bill.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) and [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) add pricing and verification-cost signals. AI coding tool pricing, feature gates, context-window limits, and usage packaging should be tracked alongside verifier effort, retry costs, and review burden. The operating question is whether the workflow produces accepted outcomes for its total cost, not whether a tool is nominally cheaper.

The [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md) adds a token-waste inspection lens. Agent cost telemetry should separate useful context from repeated history, oversized tool output, redundant structured data, and cache-miss churn. Compression savings are only meaningful when paired with accuracy, latency, retrieval, and fallback evidence.

The [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) adds context-depth pricing evidence. Token-rate and provider-inference pricing make task intensity visible: logs, deployments, configuration, runtime data, model routing, sandboxing, and execution depth can all change cost. Cost reports should therefore attach spend to the investigation depth and evidence collected, not only to the count of agent requests.

The [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json) adds session and cost-center budget controls. Session credit limits, per-user cost-center budgets, auto model selection, and model-specific billing turn cost telemetry into an active workflow guardrail. The local practice is to set expected spend envelopes before a run, record when a routed model or browser/tool loop changed cost, and review budget stops as workflow signals rather than treating them only as finance controls.

The [July 2 topic news collector source](../../../raw/processed/2026-07-02/ai-dev-wiki-topic-news-collector-2026-07-02T203134-0400.json) and [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json) add organization-pool and feature-level attribution signals. Shared AI credit pools, workflow session caps, and multi-tool coding-agent bills should be tied to the feature, team, run, subagent fan-out, and accepted outcome. The local operating question is whether the workflow spent a bounded amount on useful work, not whether the charge landed in the right vendor account.

The [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json) adds cost-control evidence for coding-agent scale. Spend growth should be traced to observability, workflow governance, subagent delegation, sandbox trials, model routes, and tool loops. Cost caps are most useful when paired with traces and accepted outcomes so a team can identify whether expensive work was valuable, mis-scoped, or blocked by missing verification.

The [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) adds per-user and built-in billing-control evidence. Desktop coding-agent rollout now intersects with plan eligibility, BYOK policy, cost centers, per-user budgets, usage reports, and billing APIs. Locally, spend governance should distinguish access enablement, budget assignment, usage evidence, and budget drift so finance controls become workflow guardrails rather than after-the-fact reports.

The [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) adds review-cycle and policy-managed usage signals. Adoption measurement should pair spend and usage with engineering-process outcomes such as time to first review and review submissions before merge, while cost-center budgets should follow teams or users closely enough that budget drift remains visible during rollout.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) adds provider-priced model access and multi-agent platform analytics. Cost telemetry should record which admin-enabled model route ran, whether the task used a cloud agent, CLI, IDE, or modernization workflow package, and how built-in cost and usage analytics map to accepted outcomes.

The [July 10 leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json) adds budget, observability, and coding-cost taxonomy signals. Per-user budgets, coding-agent cost concepts, and public cost analyses are useful locally when they split token usage, context growth, tool execution, cache behavior, verification work, and accepted outcomes. Broad vendor billing details stay upstream; this page owns the workflow decision about whether a cost spike reflects useful evidence gathering, runaway context, repeated retries, or missing scope controls.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) adds price-claim and benchmark-provenance signals. Coding-agent pricing claims should be interpreted through cost per verified outcome, not list price alone, and benchmark claims should carry provenance and contamination checks before they influence model-routing or adoption decisions.

The [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json) adds multi-agent modernization and spend-dashboard evidence. Enterprise modernization workflows should track cost by role, work package, legacy platform, verification gate, and accepted outcome so multi-agent coordination is measured as an operating model rather than generic agent usage.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) and [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) add model-size, cache, usage-alert, and shared-capability cost signals. Cost telemetry should record when a model route, cache breakpoint, multi-agent run, MCP server, PR review surface, or quality/security feature consumes separate credits or seats. Shared capabilities such as identity, trusted connectors, curated knowledge, evaluations, observability, model routing, and reusable agent patterns should be budgeted as platform infrastructure, not hidden inside one team's assistant spend.

The [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json) adds coding-agent cost and loop-control signals. Multi-model routing, hard spend caps, organization-level budgets, FinOps dashboards, review file limits, on-demand review continuation, and runaway-loop termination should be attached to the workflow outcome they support. Cost telemetry should distinguish useful escalation to a stronger model from repeated retries, excessive review continuation, or an autonomous loop that should have stopped.

The July 19-21 raw sources add budget-pool, subagent, and loop-limit evidence. The [July 19 topic news collector source](../../../raw/processed/2026-07-19/ai-dev-wiki-topic-news-collector-2026-07-19T203449-0400.json) questions whether context compression in one component actually lowers whole-task cost, while the [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json) recommends limits on retries, tool calls, loops, and escalation paths. The [July 21 topic news collector source](../../../raw/processed/2026-07-21/ai-dev-wiki-topic-news-collector-2026-07-21T203101-0400.json) adds credit-pool visibility, per-user credit reporting, review rate-limit impact, and cost-aware model routing as workflow evidence.

The July 22 raw sources add adoption-phase and tokenomics evidence. The [topic news collector source](../../../raw/processed/2026-07-22/ai-dev-wiki-topic-news-collector-2026-07-22T203140-0400.json) records cohort dashboards, code-first versus agent-first usage phases, PR-throughput comparisons, and value-stream telemetry as adoption signals that must be tied to accepted outcomes rather than seat activity. The [leaf update watch source](../../../raw/processed/2026-07-22/ai-dev-wiki-leaf-update-watch-2026-07-22T210121-0400.json) adds production, consumption, and value cost layers, so cost telemetry should separate infrastructure, orchestration, retry, idle-capacity, context-window, and model-routing costs before judging AI value.

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) adds adoption telemetry evidence from the Copilot usage metrics impact dashboard and agent-sprawl cost reporting. Local cost telemetry should separate passive licensed users, code-first users, agent-first users, multi-agent users, external-service consumption, and budget owners instead of treating seat count or aggregate requests as enough adoption evidence.

The [July 25 topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json) and [July 25 leaf update watch source](../../../raw/processed/2026-07-25/ai-dev-wiki-leaf-update-watch-2026-07-25T210250-0400.json) add cost-per-outcome and workload-placement evidence. Agentic workflows can multiply spend through repeated context replay, planning, checking, revision loops, external service calls, and local-versus-cloud routing choices. Sponsored or vendor-positioned cost claims should be treated cautiously, but the local operating rule is still durable: budget by workflow shape, owner, run location, context growth, policy logs, and accepted outcome rather than by seat activity or nominal token price.

The [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json) and [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json) add opt-in community telemetry and benchmark-efficiency signals. Cost telemetry should separate representative market claims from local operating evidence before using external usage data in workflow decisions.

The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) adds coding-agent observability evidence from a CloudWatch guide, with AWS primary context from the [CloudWatch Coding Agent Insights launch](https://aws.amazon.com/about-aws/whats-new/2026/07/cloudwatch-coding-agent-insights/) and an [AWS CloudWatch and OpenTelemetry operations blog](https://aws.amazon.com/blogs/mt/analyzing-claude-code-usage-with-cloudwatch-and-opentelemetry/). Local telemetry should connect agent spend, adoption, accepted edits, commits, pull-request flow, and alerting so teams do not confuse raw token activity with productivity.

The [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json) adds per-user agent-app attribution evidence. Adoption telemetry should distinguish individual users, organizations, feature surfaces, models, languages, daily active use, code activity, generated lines, accepted edits, and pull-request flow before claims about adoption or generated-code volume influence rollout or value decisions.

The [July 29 topic news collector source](../../../raw/processed/2026-07-29/ai-dev-wiki-topic-news-collector-2026-07-29T203119-0400.json) adds token-volume measurement risk. Telemetry should detect overuse incentives such as raw AI activity, token spend, generated lines, or tool-call counts being treated as productivity when they are not joined to quality, maintainability, review burden, delivery throughput, and accepted outcomes.

The [July 31 leaf update watch source](../../../raw/processed/2026-07-31/ai-dev-wiki-leaf-update-watch-2026-07-31T210319-0400.json) adds external evidence for budget wallets, capped spend, limit notifications, additional-fund requests, PR-state normalization, and cost-per-outcome infrastructure claims. The local telemetry rule is unchanged but sharper: cost, token use, generated activity, and benchmark success rates need accepted-output, review-quality, privacy, run-location, and workflow-shape joins before they influence adoption or model-routing decisions.

The [August 4 topic news collector source](../../../raw/processed/2026-08-04/ai-dev-wiki-topic-news-collector-2026-08-04T203217-0400.json) adds a reporting-surface retirement signal. When preview billing tools disappear, governed agent rollouts should rely on durable usage exports, billing APIs, budget settings, cost-center allocation, and user-level spend limits rather than screenshots or temporary consoles. The local practice is to preserve cost evidence that can survive product-console churn and still map spend to agent owners, workflows, and accepted outcomes.

## Practice Boundaries

- Track model, token, tool, runtime, and subagent costs by workflow run and step when the work is recurring or expensive.
- Pair cost records with outcome evidence such as accepted patch, failed verification, useful research, rejected draft, or blocked handoff.
- Bound subagent fan-out, retry loops, and long context growth with explicit budget or stop rules.
- Compare cost against workflow value and review burden, not against model capability claims alone.
- Treat high spend without better acceptance evidence as a workflow smell.
- Feed cost findings back into workflow-before-model-selection decisions.
- Pair adoption and usage reports with outcome signals before treating tool uptake as success.
- Track marginal cost for background runs, retry loops, repository ingestion, and long-context traversal before those behaviors become standing automation.
- Compare managed, subscription, self-hosted, and local execution options with total cost of ownership, not only token price or nominal infrastructure cost.
- Attribute recurring agent spend to a named owner, workflow, permission scope, and outcome.
- Set alert thresholds for context growth, tool loops, retrieval expansion, and background runs before they become normal operating cost.
- Pair context budgets with workflow ROI review when agents expand planning, retrieval, and verification work.
- Track seat, usage, feature-gate, context-window, retry, verifier, and review costs as part of workflow total cost.
- Compare tool pricing against accepted outcomes, risk reduction, and reviewer effort rather than nominal subscription or token price alone.
- Track compression savings, cache-hit behavior, fallback retrievals, and latency alongside quality so cost reduction does not hide degraded task performance.
- Attribute token-rate agent spend to context retrieval, log joining, sandboxing, execution depth, model routing, and accepted outcome.
- Set session-level and owner-level spend envelopes for long-running or delegated agent work.
- Record model-routing, browser-tool, and tool-orchestration choices when they explain cost variance.
- Treat budget exhaustion as evidence that the task scope, model route, or verification loop needs review.
- Attribute shared AI-credit pool consumption to team, feature, run, tool surface, subagent fan-out, and accepted outcome.
- Compare cross-tool coding-agent bills at the workflow level so cost governance does not fragment by product console.
- Tie cost caps and alerts to trace evidence, sandbox trials, model routing, tool loops, subagent delegation, and accepted outcomes.
- Separate agent access, per-user budget assignment, usage reporting, and budget drift reviews when onboarding desktop coding agents.
- Prefer durable billing and usage APIs for recurring cost evidence instead of relying on preview reporting surfaces.
- Pair coding-agent spend with review-cycle, merge, and accepted-outcome evidence before treating usage growth as adoption success.
- Keep cost-center and per-user budget membership synchronized with the teams or owners responsible for the agent workflow.
- Record admin-enabled model routes and provider-priced usage when task-to-model routing changes cost or review evidence.
- Map multi-agent platform cost and use analytics to workflow packages, roles, and accepted modernization or repair outcomes.
- Separate token, context, cache, tool, sandbox, verification, retry, and reviewer-effort costs before deciding whether to cap, redesign, or expand a workflow.
- Treat per-user or cost-center budgets as guardrails that should trigger workflow review when they stop useful work or permit wasteful loops.
- Compare coding-agent prices by verified outcome, review effort, verification cost, and accepted result rather than list price alone.
- Record benchmark provenance and contamination risk when benchmark claims influence cost-performance or model-routing decisions.
- Attribute multi-agent modernization spend to roles, legacy platform, work package, verification gate, and accepted outcome.
- Treat built-in cost dashboards as workflow telemetry inputs that still need local mapping to review effort, risk reduction, and completed modernization work.
- Attribute model-size choices, cache policy, multi-agent concurrency, PR review features, MCP usage, and quality/security scans to the workflow outcome they support.
- Budget shared identity, connector, knowledge, evaluation, observability, routing, and reusable-pattern capabilities as platform costs before expanding agent adoption.
- Record model-routing complexity, hard spend caps, organization budgets, PR review file limits, on-demand continuation, and loop-termination events as workflow-level cost evidence.
- Review runaway-loop stops and review-continuation spend as scope or verification signals, not only as billing events.
- Validate context-compression savings against whole-task spend, accepted outcome, latency, and verification cost instead of extrapolating from one shortened context component.
- Track shared credit pools, per-user credit visibility, rate-limit wait time, subagent model choices, loop counts, retry counts, and escalation events as workflow telemetry.
- Pair adoption-phase dashboards and PR-throughput measures with accepted outcomes before treating AI usage growth as operating-model success.
- Split tokenomics evidence into production, consumption, and value layers so routing, context size, retries, orchestration, and idle capacity can be corrected separately.
- Budget agentic workflows by task shape, context replay, run location, external-service consumption, policy logs, owner, and accepted outcome when local, self-hosted, or cloud routes are compared.
- Treat sponsored or vendor-positioned cost claims as weak evidence unless they are mapped to local traces, verification cost, privacy constraints, and accepted outcomes.
- Track tool share, active users, active days, tokens, local execution, model-router choices, and review burden only when those signals explain workflow cost.
- Treat public dollars-per-completed-task and wall-clock benchmark efficiency as comparison inputs that need local normalization by workflow, task mix, user cohort, privacy boundary, and accepted outcome.
- Join cost, activity, accepted edits, commits, pull-request flow, and alerts when evaluating whether coding-agent usage is producing accepted delivery outcomes.
- Attribute agent-app usage to user, organization, feature surface, model, language, daily activity, code activity, generated lines, and accepted delivery outcomes before using it as adoption evidence.
- Reject AI-usage leaderboards or token-volume goals as success metrics unless they are tied to accepted outcomes and review quality.
- Treat AI wallets, spend caps, limit notifications, and additional-fund requests as workflow signals that should trigger scope, routing, or verification review.
- Normalize benchmark and productivity telemetry by pull-request state, accepted merges, review burden, task mix, and workflow shape before comparing tools or teams.
- Preserve sponsored cost-infrastructure claims as weak evidence unless local traces show privacy, runtime placement, and accepted-outcome benefits.
- Prefer durable usage exports, billing APIs, budget settings, and cost-center allocation over temporary reporting apps for recurring agent-cost evidence.
- Keep user-level spend limits and budget ownership joined to the workflow, owner, and accepted outcome when product billing surfaces change.

## Authoritative Sources

- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [workflow before model selection](workflow-before-model-selection.md)
- [subagent coordination](../agent-workflows/subagent-coordination.md)
- [user-visible progress and runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [Affordable AI Agents source](../../../raw/processed/The Affordable AI Agents.md)
- [June 27 leaf update watch source](../../../raw/processed/2026-06-27/ai-dev-wiki-leaf-update-watch-2026-06-27T210128-0400.json)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json)
- [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json)
- [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md)
- [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json)
- [July 1 evening topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T203225-0400.json)
- [July 2 topic news collector source](../../../raw/processed/2026-07-02/ai-dev-wiki-topic-news-collector-2026-07-02T203134-0400.json)
- [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json)
- [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 10 leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 13 topic news collector source](../../../raw/processed/2026-07-13/ai-dev-wiki-topic-news-collector-2026-07-13T203320-0400.json)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)
- [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json)
- [July 19 topic news collector source](../../../raw/processed/2026-07-19/ai-dev-wiki-topic-news-collector-2026-07-19T203449-0400.json)
- [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json)
- [July 21 topic news collector source](../../../raw/processed/2026-07-21/ai-dev-wiki-topic-news-collector-2026-07-21T203101-0400.json)
- [July 22 topic news collector source](../../../raw/processed/2026-07-22/ai-dev-wiki-topic-news-collector-2026-07-22T203140-0400.json)
- [July 22 leaf update watch source](../../../raw/processed/2026-07-22/ai-dev-wiki-leaf-update-watch-2026-07-22T210121-0400.json)
- [July 25 topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json)
- [July 25 leaf update watch source](../../../raw/processed/2026-07-25/ai-dev-wiki-leaf-update-watch-2026-07-25T210250-0400.json)
- [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json)
- [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json)
- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json)
- [July 29 topic news collector source](../../../raw/processed/2026-07-29/ai-dev-wiki-topic-news-collector-2026-07-29T203119-0400.json)
- [July 31 leaf update watch source](../../../raw/processed/2026-07-31/ai-dev-wiki-leaf-update-watch-2026-07-31T210319-0400.json)
- [August 4 topic news collector source](../../../raw/processed/2026-08-04/ai-dev-wiki-topic-news-collector-2026-08-04T203217-0400.json)
- [AWS CloudWatch Coding Agent Insights launch](https://aws.amazon.com/about-aws/whats-new/2026/07/cloudwatch-coding-agent-insights/)
- [AWS CloudWatch and OpenTelemetry operations blog](https://aws.amazon.com/blogs/mt/analyzing-claude-code-usage-with-cloudwatch-and-opentelemetry/)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [AI process layer and workflow state](../application-patterns/ai-process-layer-and-workflow-state.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-07-23 with adoption-phase telemetry, agent-sprawl cost visibility, external-service dependency, and budget-owner signals.
- Created on 2026-06-23 from public source guidance on coding-agent token economics, step-level cost tracing, subagent fan-out, and outcome-linked telemetry.
- Maintained on 2026-06-26 with adoption-phase reporting and usage-based model enablement as outcome-linked telemetry inputs.
- Maintained on 2026-06-27 with marginal-cost and infrastructure total-cost signals for autonomous agent loops.
- Maintained on 2026-06-27 with owner-attributed cost monitoring, thresholds, showback, and context-budget review.
- Maintained on 2026-06-28 with tool-pricing, feature-gate, verifier-cost, and review-burden signals.
- Maintained on 2026-06-30 with context-compression cost telemetry, cache behavior, latency, and quality guardrails.
- Maintained on 2026-07-01 with token-rate task-intensity pricing, context-depth attribution, and execution-depth cost evidence.
- Maintained on 2026-07-01 with session credit limits, cost-center budgets, auto routing, and budget stops as workflow telemetry.
- Maintained on 2026-07-02 with shared credit-pool caps, feature-level coding-agent cost attribution, and cross-tool spend review.
- Maintained on 2026-07-06 with trace-linked cost caps, sandbox-trial costs, model-routing costs, and subagent delegation cost evidence.
- Maintained on 2026-07-07 with desktop-agent onboarding budgets, per-user cost centers, usage-reporting APIs, and budget drift as workflow guardrails.
- Maintained on 2026-07-08 with review-cycle outcome metrics and synchronized cost-center budget membership.
- Maintained on 2026-07-09 with admin-enabled model-route cost attribution and multi-agent platform cost analytics.
- Maintained on 2026-07-10 with token, context, cache, tool, verification, retry, and budget-stop cost taxonomy signals.
- Maintained on 2026-07-11 with cost-per-verified-outcome and benchmark-provenance controls for coding-agent price claims.
- Maintained on 2026-07-13 with multi-agent modernization cost attribution and spend-dashboard mapping to accepted outcomes.
- Maintained on 2026-07-14 with model-size, cache, multi-agent, MCP, PR-review, quality-feature, and shared-capability cost attribution.
- Maintained on 2026-07-15 with multi-model routing, spend caps, organization budgets, PR file limits, review continuation, and runaway-loop cost signals.
- Maintained on 2026-07-22 with whole-task context-compression checks, shared credit pools, rate-limit impact, subagent model, and retry-loop cost telemetry.
- Maintained on 2026-07-22 with adoption-phase dashboard, value-stream telemetry, and tokenomics cost-layer controls.
- Maintained on 2026-07-25 with workload-placement cost governance, sponsored-claim caution, context-replay budgeting, and cost-per-outcome routing evidence.
- Maintained on 2026-07-26 with opt-in telemetry caution, benchmark-efficiency, active-user, token, cost-per-completed-task, local-execution, and model-router cost guidance.
- Maintained on 2026-07-27 with spend, activity, accepted-edit, commit, pull-request-flow, and alerting telemetry joins.
- Maintained on 2026-07-28 with per-user, organization, feature, model, language, daily-active-use, code-activity, and generated-line attribution for agent-app adoption reporting.
- Maintained on 2026-07-29 with token-volume and AI-activity measurement anti-pattern controls.
- Maintained on 2026-07-31 with AI wallet, budget alert, PR-state normalization, sponsored tokenomics, and cost-per-outcome routing evidence.
- Maintained on 2026-08-04 with durable billing exports, budget settings, cost-center allocation, and preview-reporting retirement controls.
