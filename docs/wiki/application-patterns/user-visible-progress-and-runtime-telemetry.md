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

## Authoritative Sources

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

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

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
