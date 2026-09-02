---
type: "Application Pattern"
title: "User-Visible Progress And Runtime Telemetry"
description: "Long-running AI workflows need visible progress so users can understand what the system is doing, where it is waiting, and which checks still matter."
tags: ["application-patterns"]
---

# User-Visible Progress And Runtime Telemetry

## Current Understanding

Long-running AI workflows need visible progress so users can understand what the system is doing, where it is waiting, and which checks still matter. Token streaming can show generation, but useful progress also includes retrieved files, tool activity, approval waits, unresolved items, generated drafts, and runtime health.

Progress events are product signals, not proof of hidden reasoning. The harness should expose enough state for the user to judge whether the workflow is alive, blocked, waiting for approval, or ready for acceptance. Local and long-running model workflows also need operational telemetry such as latency, memory pressure, cache behavior, GPU or accelerator use, token counts, and quality drift signals.

The [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json) adds a latency boundary for user-facing agents: time to first token should be separated from total pipeline latency, and tool-call pauses should produce explicit progress states. A streaming model response is not enough when retrieval, tool use, pre-inference work, or approval waits can create silence before or between tokens.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) adds remote-startup and permission-telemetry signals. Remote agent provisioning should expose checklist progress, background-agent visibility, restart state, permission denials, telemetry controls, authentication notices, and resource cleanup when those states affect trust or user acceptance.

The [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) adds semantic-failure telemetry. A workflow can look healthy at the infrastructure layer while the agent is looping, using irrelevant evidence, or failing the task objective. Runtime telemetry should therefore include traces, tool-loop summaries, evaluation outcomes, retry reasons, and failure-attribution fields in addition to latency and resource metrics.

The [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md) adds context-layer telemetry. When a harness compresses or routes context, users and operators need visible signals for token savings, cache hits, retrieval fallbacks, compressor choice, provenance, latency, and drift checks so optimization remains inspectable.

The [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json) adds security and behavior telemetry. Agent observability should include tool calls, reasoning-loop state, state transitions, quality checks, verification results, and security posture signals so operators can distinguish healthy execution from unsafe, looping, or task-wrong behavior.

The July 7 raw sources add session-level telemetry and emerging runtime semantics. The [topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) records sandbox resource metrics grouped by sandbox name and session ID. The [leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) records a draft agent runtime telemetry model with tool calls, context changes, memory lifecycle events, trace identifiers, anomaly detection, and remediation workflows. Locally, session and trace IDs should join cost, runtime, and semantic-failure evidence.

The [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json) adds centrally managed telemetry and remote-session notification signals. Local telemetry design should separate OTLP-style trace routing from product analytics, decide whether prompt, response, and tool content are retained, and expose remote session states such as active work, waiting for user input, idle, finished, and linkable logs when a human may need to resume or intervene.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) adds session-forensics and multi-agent analytics signals. Agent telemetry should make cost, usage, command execution, tool and MCP activity, session state, modernization workflow package, and runtime policy decisions joinable by run or session so operators can investigate both cost and behavior without reading raw chat history first.

The [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json) adds trajectory-diagnosis and bounded-loop telemetry signals. Progress events should expose budgets, step ceilings, stall safeguards, approval gates, output-path checks, per-step traces, test-failure pivots, and earliest-error localization when an agent loop can run long enough that final output alone is insufficient.

The [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) adds clearer task-progress and inline-visualization signals. Progress surfaces should distinguish task links, current run state, review annotations, generated visualizations, computer-use activity, and no-user-facing-change patch notes so users can tell whether a task is blocked, waiting, visually reporting, or merely updated at the runtime layer.

The [July 25 topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json) adds coding-agent observability evidence. Agent telemetry should join prompts, agent sessions, pull requests, standards checks, cost, quality, MCP activity, and production or incident signals so adoption and reliability reviews can trace what an AI coding session changed and whether the workflow improved.

The July 28 raw sources add IDE agent telemetry and adoption-reporting evidence. The [topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json) supports per-user and surface-level usage joins, while the [leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) adds IDE-hosted OpenTelemetry export, token-limit controls, MCP diagnostics, custom-agent routing, CLI session forks, and durable todo/progress surfaces.

The [July 31 topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json) adds audit and live-trace signals from autonomous workflow and testing surfaces. Runtime telemetry should expose queue-triggered starts, single-node traces, AI-processing input/output audit records, remote-control viewing state, and human supervision events when the agentic workflow can continue without a hand-authored path.

The [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json) adds IDE agent-window and trace-routing evidence. Long-running coding-agent surfaces should show session state, subagent model and elapsed time, active tool calls, PR update state, and review context alongside trace identifiers so users can decide whether to supervise, interrupt, or accept the work.

The August 7 observability clippings add an LLM application telemetry boundary. [LLM observability quality gates](../verification-and-evals/llm-observability-quality-gates.md) owns release-control practice, while this page owns the runtime surface: traces, prompt versions, cost, latency, errors, feedback, session replay, product events, and human annotations should be joinable when operators need to decide whether a user-facing AI workflow is healthy, degraded, costly, or quality-regressing.

The August 11 raw sources add IDE and workflow operating-record telemetry. The [topic news collector source](../../../raw/processed/2026-08-11/ai-dev-wiki-topic-news-collector-2026-08-11T203048-0400.json) records agent debug logs, session visibility, OpenTelemetry settings, and per-model token breakdowns, while the [leaf update watch source](../../../raw/processed/2026-08-11/ai-dev-wiki-leaf-update-watch-2026-08-11T210210-0400.json) records reasoning effort, context compaction, prompt caching, tool approvals, and region-aware fallback as operating-record fields. Locally, progress and telemetry should make those fields joinable by session when they explain approval, cost, or behavior.

The August 14 raw sources add approval, queue, build, service-health, and behavior telemetry. The [topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json) records side-channel agent questions, queued prompts and shell commands, rewind recovery, approval pending states, and hosted service disruptions. The [leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json) records build status, logs, commit SHAs, run-to-build mapping, incident evidence fields, and purpose-based behavior baselines. Locally, progress surfaces should show whether work is waiting for approval, queued, running on a known environment, degraded by provider status, or deviating from expected behavior.

The August 15 raw sources add runtime control-plane and behavior-intelligence telemetry. The [topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json) records self-hosted factory session records, retained eval data, CI milestone truth, gateway request and response audit tables, action-level controls, spend attribution, budgets, and unified tracing. The [leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) adds continuous-agent behavior baselines, activity logging, deviation evidence, and memory-object inspection. Locally, telemetry should show not only progress but whether the run's actions, memory writes, cost, and recovery path match the approved workflow.

The August 21 sources add collaborative-channel and event-subscription telemetry:

- The [topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json) records collaborative coding-agent channels where intermediate work is observable.
- The [leaf update watch source](../../../raw/processed/2026-08-21/ai-dev-wiki-leaf-update-watch-2026-08-21T210236-0400.json) records event subscriptions, long-lived goals, and non-interrupting steering.
- Locally, progress surfaces should show channel-visible draft state, event source, steering changes, active goal, approval waits, and handoff status without treating visibility as proof of correctness.

The August 22 raw sources add execution-edge telemetry:

- The [topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json) records shared-channel coding-agent sessions, database-agent traces, layered production evals, and billable agent actions.
- The [leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json) records trust receipts, append-only verdict logs, OpenTelemetry-style GenAI conventions, memory writes, connected-app actions, sandbox events, and graph-edge evidence.
- Locally, runtime telemetry should join progress, authority, spend, memory, connected-app, and eval evidence by session so a reviewer can inspect not only what happened, but who or what authorized each edge.

The August 28 and 29 raw sources add runtime inventory, observability, and IDE usage-visibility evidence. The [leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json) records tracing and governance for agents that open pull requests, fix CI, upgrade dependencies, remediate CVEs, use model harnesses, and need running-agent inventories. The [topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) adds context-window usage, cost information, review effort, shared sessions, and persistent follow-up signals. Locally, progress telemetry should join what the user sees with runtime identity, cost, state, and approval evidence.

The [September 1 topic news collector source](../../../raw/processed/2026-09-01/ai-dev-wiki-topic-news-collector-2026-09-02T003202Z.json) adds long-running task and monitor telemetry signals. Mobile task lists expose running tasks, unread updates, tasks awaiting response, editable queued prompts, live working time, and thread identifiers. Supervisory workflows expose safe-output counts, grader pass rates, and blocked-network-call observations. Locally, telemetry should make waiting, unread, queued, blocked, graded, and actively-working states visible before a human decides whether to intervene.

## Practice Boundaries

- Stream progress when users need visible state during multi-step work.
- Separate user-visible progress from unsupported claims about hidden reasoning.
- Show tool activity, approval waits, generated artifacts, unresolved issues, and verification status when they affect user acceptance.
- Surface runtime metrics when latency, memory, cache behavior, or model operation can change the user experience.
- Keep progress and telemetry aligned with actual workflow state instead of smoothing over failures or blocked steps.
- Track time to first token separately from total workflow latency when user perception matters.
- Show visible states for retrieval, pre-inference work, tool-call pauses, approval waits, retries, and verification.
- Surface remote provisioning, background-agent state, denial reasons, authentication notices, telemetry settings, and resource cleanup when they affect user trust.
- Record semantic failure signals, trace summaries, retry reasons, tool-loop patterns, and evaluation outcomes when agent behavior can appear operationally healthy but task-wrong.
- Expose context-optimization telemetry when compression, cache alignment, or retrieval fallback can change latency, cost, or task accuracy.
- Include behavior, verification, and security signals in operator telemetry when agents can call tools, cross trust boundaries, or continue across sessions.
- Track tool-call traces, state transitions, and quality metrics together so semantic failures are not hidden behind infrastructure health.
- Attach sandbox session IDs, trace identifiers, resource metrics, tool calls, context changes, memory lifecycle events, anomaly signals, and remediation steps when they affect verification or cost control.
- Separate trace transport settings, service metadata, secrets, and content-capture policy before exporting agent telemetry.
- Show remote-session states and log handoff links when long-running agents can continue outside the user's active editor session.
- Join cost, usage, command execution, MCP activity, tool usage, policy decisions, and workflow-package state by run or session when agents operate across IDEs or enterprise modernization workflows.
- Show loop budget, step limit, stall, approval, and output-path status when autonomous work is bounded by harness policy.
- Preserve test-failure pivots, trace saliency summaries, and earliest-error markers for operator diagnosis of failed agent runs.
- Distinguish task links, current run state, review annotations, generated visualizations, computer-use activity, and runtime-only patch updates in progress surfaces.
- Avoid presenting version-only or no-user-facing-change runtime updates as workflow progress for the user's task.
- Join prompt, session, pull-request, standards-check, cost, quality, MCP, and production-signal telemetry when coding-agent observability is used for rollout or reliability decisions.
- Join per-user adoption reports with IDE telemetry, token budgets, MCP diagnostics, custom-agent routes, session forks, and todo/progress state when agent work can cross surfaces.
- Keep token-limit changes, model enablement, MCP diagnostics, and telemetry export settings visible as runtime controls, not only developer preferences.
- Show queue-triggered starts, live node traces, AI-processing audit records, remote-control viewing state, and human supervision events when an autonomous workflow or test run is active.
- Show session state, subagent model, elapsed time, active tool calls, PR update state, and review context when IDE or agent-window workflows manage long-running coding tasks.
- Keep trace identifiers and visible progress joined so a user can move from progress UI to audit or review evidence.
- Join LLM traces, prompt versions, cost, latency, errors, feedback, product events, and human annotations when quality or release decisions depend on runtime behavior.
- Join session/debug logs, telemetry export settings, token categories, reasoning effort, compaction, prompt-cache behavior, tool approvals, and fallback routes when they explain runtime behavior or cost.
- Show side-channel questions, queued prompts, queued shell commands, approval-pending metadata, rewind points, service-health state, build status, build logs, commit SHA, run-to-build mapping, and purpose-baseline deviations when they affect review or acceptance.
- Join session records, retained eval data, milestone checks, action-level controls, spend attribution, budgets, behavior baselines, activity logs, memory-object inspections, and recovery evidence when an agent can continue or act across systems.
- Show channel-visible intermediate work, event subscriptions, active goals, steering events, approval waits, and handoff status for collaborative or long-running coding-agent workflows.
- Join shared-channel messages, integration identity, repository permission checks, sandbox policy, budget owner, generated pull request, and extra approval state for chat-started coding-agent work.
- Record memory writes, connected-app access, trust receipts, append-only verdict logs, sandbox events, graph-edge authorization, and downstream log links when they influence an agent's behavior or accountability.
- Use common trace vocabulary for model, retrieval, tool, gateway, human approval, cost, latency, and eval events so runtime evidence can be reused in trajectory-level evaluation.
- Expose unread updates, waiting-for-response state, queued prompt state, live working time, durable task identifiers, safe-output counts, grader pass rates, and blocked-network observations for long-running tasks.

## Authoritative Sources

- [August 28 leaf update watch source](../../../raw/processed/2026-08-28/ai-dev-wiki-leaf-update-watch-2026-08-28T210306-0400.json)
- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json)
- [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md)
- [July 3 leaf update watch source](../../../raw/processed/2026-07-03/ai-dev-wiki-leaf-update-watch-2026-07-03T210126-0400.json)
- [Application harness patterns](application-harness-patterns.md)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 8 topic news collector source](../../../raw/processed/2026-07-08/ai-dev-wiki-topic-news-collector-2026-07-08T203125-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)
- [July 25 topic news collector source](../../../raw/processed/2026-07-25/ai-dev-wiki-topic-news-collector-2026-07-25T203314-0400.json)
- [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 31 topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json)
- [August 4 leaf update watch source](../../../raw/processed/2026-08-04/ai-dev-wiki-leaf-update-watch-2026-08-04T210145-0400.json)
- [LLM observability quality gates](../verification-and-evals/llm-observability-quality-gates.md)
- [August 11 topic news collector source](../../../raw/processed/2026-08-11/ai-dev-wiki-topic-news-collector-2026-08-11T203048-0400.json)
- [August 11 leaf update watch source](../../../raw/processed/2026-08-11/ai-dev-wiki-leaf-update-watch-2026-08-11T210210-0400.json)
- [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json)
- [August 14 leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json)
- [August 15 topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json)
- [August 21 leaf update watch source](../../../raw/processed/2026-08-21/ai-dev-wiki-leaf-update-watch-2026-08-21T210236-0400.json)
- [August 22 topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json)
- [August 22 leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json)
- [September 1 topic news collector source](../../../raw/processed/2026-09-01/ai-dev-wiki-topic-news-collector-2026-09-02T003202Z.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [ai process layer and workflow state](ai-process-layer-and-workflow-state.md)
- [local model runtime harness](local-model-runtime-harness.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [trajectory-level agent evaluation](../verification-and-evals/trajectory-level-agent-evaluation.md)
- [LLM observability quality gates](../verification-and-evals/llm-observability-quality-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-08-29 with running-agent inventory, runtime tracing, cost, context-window, review-effort, shared-session, and persistent-follow-up telemetry evidence.
- Maintained on 2026-09-01 with running-task, unread-update, awaiting-response, queued-prompt, working-time, thread-identifier, safe-output, and grader telemetry.
- Created on 2026-06-23 from source guidance on progress events, agent UI updates, and runtime metrics for local or long-running AI workflows.
- Maintained on 2026-06-24 with TTFT, pipeline latency, and tool-call pause state guidance.
- Maintained on 2026-06-26 with remote provisioning, background-agent visibility, permission-denial, authentication, telemetry, and cleanup states.
- Maintained on 2026-06-28 with semantic-failure telemetry, trace summaries, and evaluation outcomes.
- Maintained on 2026-06-30 with context-optimization telemetry for compression, cache hits, retrieval fallbacks, provenance, latency, and drift checks.
- Maintained on 2026-07-03 with behavior, verification, state-transition, and security-posture telemetry for agentic workflows.
- Maintained on 2026-07-07 with sandbox session metrics, trace identifiers, context and memory lifecycle telemetry, anomaly signals, and remediation workflows.
- Maintained on 2026-07-08 with managed telemetry export boundaries and remote coding-agent session states.
- Maintained on 2026-07-09 with session-forensics, cost-and-use analytics, and run-level policy-decision telemetry.
- Maintained on 2026-07-10 with bounded-loop progress, output-path checks, trace saliency, and earliest-error diagnostics.
- Maintained on 2026-07-14 with task-link, review-annotation, visualization, computer-use, and runtime-only update progress boundaries.
- Maintained on 2026-07-25 with coding-agent observability joins across prompts, sessions, pull requests, standards checks, cost, quality, MCP, and production signals.
- Maintained on 2026-07-28 with per-user adoption, IDE OpenTelemetry, token-limit, MCP diagnostic, custom-agent, session-fork, and todo/progress telemetry guidance.
- Maintained on 2026-07-31 with queue-trigger, live-node trace, AI-processing audit, remote viewing, and human-supervision telemetry guidance.
- Maintained on 2026-08-04 with IDE agent-window session state, subagent timing, active tool-call, PR update, and trace-linkage guidance.
- Maintained on 2026-08-07 with LLM trace, prompt-version, product-event, annotation, cost, latency, and quality-regression telemetry joins.
- Maintained on 2026-08-11 with session/debug logs, token categories, reasoning effort, compaction, prompt-cache, tool-approval, and fallback-route telemetry joins.
- Maintained on 2026-08-14 with side-channel question, queued-work, approval-pending, rewind, service-health, build-status, commit-SHA, run-to-build, and purpose-baseline telemetry.
- Maintained on 2026-08-15 with session-record, eval-retention, milestone-check, action-control, spend-attribution, behavior-baseline, memory-inspection, and recovery telemetry.
- Maintained on 2026-08-21 with channel-visible intermediate work, event-subscription, active-goal, steering-event, approval-wait, and handoff-status telemetry.
- Maintained on 2026-08-22 with execution-edge telemetry for shared channels, database traces, billable actions, trust receipts, memory writes, connected apps, sandbox events, and reusable trace vocabulary.
