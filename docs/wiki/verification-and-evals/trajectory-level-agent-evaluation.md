---
type: "Verification And Eval"
title: "Trajectory-Level Agent Evaluation"
description: "Agent evaluation should inspect the path an agent took, not only the final answer or merged diff."
tags: ["verification-and-evals"]
---

# Trajectory-Level Agent Evaluation

## Current Understanding

Agent evaluation should inspect the path an agent took, not only the final answer or merged diff. The local evaluation object includes task framing, retrieved context, reasoning-visible summaries, tool calls, execution order, state transitions, approval waits, errors, retries, generated artifacts, and final verification.

The [topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) records multiple public signals that agent monitoring, observability, and evals are converging around trajectory evidence. Vendor, benchmark, and product pages stay upstream-owned; this page owns the local practice of using trajectory evidence to decide whether an agent workflow is reliable.

Trajectory evaluation complements [representative workflow calibration](representative-workflow-calibration.md). Calibration checks whether a model or harness is suitable for representative tasks. Trajectory evaluation checks whether a particular run, workflow family, or agent configuration behaved safely and effectively across its intermediate decisions.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) adds an agreement and environment-design signal. Agent evals should inspect whether independent runs converge on the same evidence-backed result, whether disagreement exposes missing context or weak rubrics, and whether the harness environment made the relevant tools, context, and feedback visible.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) also routes model benchmark announcements upstream. Locally, benchmark improvements only change practice when they trigger new representative terminal, coding, review, or repair tasks in the acceptance suite before autonomy expands.

The [agent evals source](../../../raw/processed/Making Agent Evals Isn’t As Hard As You Think!.md) adds a test-shape taxonomy for agent behavior. Behavioral unit evals should lock a single expected step or tool call, integration evals should score full-run outcomes, online evals should monitor live traces and trends, and benchmark evals should measure a representative capability across task distributions. The local practice is to choose the eval shape from the failure mode being controlled.

The [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json) adds reproducible environment evaluation signals. Long-running stateful-agent evals should include the environment, instruction, created artifacts, tool trace, and deterministic check script. The evaluation target is whether the agent changed the environment correctly under the intended constraints, not whether the final message describes a plausible outcome.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) adds platform and agentic-testing trajectory signals. Agent-platform runs should preserve control-plane decisions, model routing, tool calls, memory and retrieval events, sandbox boundaries, and runtime observations. Fully agentic tests need trajectory evidence because the path is selected during execution, not pre-authored in a script.

The July 7 raw sources add step-local and hidden-state research signals. The [leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) routes Agent Step Value into local practice as evidence for scoring individual actions against before-and-after state projections. The [topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json) also records latent-programming research that probes model state for parse, test, and regression signals; locally this remains an emerging research direction, while steady-state assurance still depends on observable tests, traces, builds, and review gates.

The [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json) adds benchmark-design and failure-diagnosis evidence for coding-agent trajectories. Performance optimization, long-horizon software tasks, and repository-level failure diagnosis all need traces that show profiling choices, context folding, test-failure pivots, earliest-error localization, and verification decisions. Broad PERFOPT-Bench, DeepSWE, TrajAudit, and paper cataloging belongs upstream; locally, the evaluation rule is to keep trajectories rich enough to explain why the agent path worked or failed.

The [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json) adds provider-adapter and trace-assertion evidence. Coding-agent evaluation should record which harness path ran the task, which side effects were allowed, how traces were asserted, how token or cost pressure shaped the run, and which sandbox or deterministic checks made the result reproducible.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) and [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) add proof-loop and benchmark-shape signals. Completion proof should preserve the specification, agent actions, artifacts, evidence, and independent verifier result so a trajectory can be audited after the final answer. Benchmark indexes that emphasize end-to-end application builds, cleanroom reconstruction, and production-like coding-agent tasks should refresh local trajectory evaluation with tasks that exercise full delivery paths, not only isolated issue patches.

The [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json) adds AgentCompass and production-eval evidence. Trajectory evaluation should separate benchmark, harness, and environment components, preserve asynchronous execution state, and score whether tool calls, arguments, state changes, recovery behavior, cost, and safety controls followed the intended path. Final prose or a generated diff is not enough when the agent mutates files, records, tickets, calendars, deployments, or other stateful systems.

The [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json) and [July 21 topic news collector source](../../../raw/processed/2026-07-21/ai-dev-wiki-topic-news-collector-2026-07-21T203101-0400.json) add trace-issue and graph-engineering evidence. Trajectory evaluation should preserve graph/run/node identifiers, routers, joins, deterministic functions, tool calls, human checkpoints, budgets, policies, approvals, failure categories, and issue grouping so multi-agent systems can be debugged at the path level rather than judged only by final output.

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) adds workflow-fit eval evidence from benchmark ledgers and graph-engineering practice. Trajectory evaluation should connect graph stages, deterministic code steps, subagent streaming, tool-use benchmarks, terminal benchmarks, repository-understanding benchmarks, and long-horizon software-engineering tasks to the workflow being authorized.

The [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json) adds multi-domain coding-agent benchmark evidence. Trajectory evaluation should preserve contamination-resistant task construction, repository-code, frontend, office, and security workflow coverage, reproducible harness state, and scoring artifacts when claims about autonomous coding skill inform adoption.

The [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json) and [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json) add benchmark-realism and system-level safety evidence. Coding-agent benchmark claims should affect local autonomy only when the run evidence can explain the path, not only the final score.

The [July 29 topic news collector source](../../../raw/processed/2026-07-29/ai-dev-wiki-topic-news-collector-2026-07-29T203119-0400.json) adds failure-attribution evidence from agent self-improvement research. Non-improving agent runs should be classified against ambiguous specifications, missing task information, brittle evaluators, unstable services, weak retrieval, and prompt or model limits before the local workflow treats prompt optimization as the fix.

The August 5 sources add production-trace and coding-harness evidence. The [LangSmith Engine clipping](../../../raw/processed/Quickstart Autonomous Agent Improvement with LangSmith Engine.md) frames trace review, proposed fixes, experiments, deployment, and monitoring as an improvement lifecycle, while the [August 5 leaf update watch source](../../../raw/processed/2026-08-05/ai-dev-wiki-leaf-update-watch-2026-08-05T210155-0400.json) records coding-harness traces and approval-gated tools. Trajectory evaluation should therefore preserve the production failure trace, proposed change, experiment result, deployed version, and regression monitor together.

The August 7 observability clippings add a trace-to-regression boundary. The [LLM observability quality gates](llm-observability-quality-gates.md) leaf owns tool-selection practice, while this page keeps the trajectory rule: production traces should be convertible into eval cases with the relevant prompt version, tool-call spans, retrieval context, component score, human annotation, and release decision. Final-output scores are not enough when a run can fail because of retrieval, tool choice, argument shape, memory, orchestration, or prompt drift.

The [August 11 topic news collector source](../../../raw/processed/2026-08-11/ai-dev-wiki-topic-news-collector-2026-08-11T203048-0400.json) adds SWE-RPG evidence for repository-level issue-resolution trajectories. Intermediate requirement-clarification and implementation-plan references expose failures that final patch outcomes hide, so local agent evals should preserve clarification questions, recovered implicit requirements, planning artifacts, and implementation evidence before judging whether a repository task was solved.

The August 12 raw sources add evaluation-framework and harness-layer evidence. The [Harbor core concepts clipping](../../../raw/processed/Core Concepts.md), [Harbor motivation clipping](../../../raw/processed/Motivation.md), and [Inspect clipping](../../../raw/processed/Inspect.md) reinforce that trajectory evaluation needs explicit task, dataset, environment, trial, job, solver, scorer, sandbox, log, and tool boundaries. The [topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json) adds a model/context/harness split: a failed agent run should be attributed against retrieved context, permissions, memory, tools, code execution, delegation, environment, and scoring behavior before local practice treats the model as the only failure point.

The August 15 raw sources add containment and milestone-evaluation evidence. The [topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json) records a CI-red incident and self-hosted factory decisions that require trajectories to preserve execution location, egress, inference route, session records, and eval data. The [leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) adds sandbox-escape, behavior-baseline, persistent-memory poisoning, and repository/skill baiting evidence. Trajectory evaluation should inspect whether the run stayed inside containment, used approved memories and tools, reached the external milestone, and recorded enough action history to explain deviations.

The August 17 topic news collector adds agentic web-development evaluation evidence. Frontend-agent trajectories should preserve deployed behavior, retries, tool-call traces, recovery steps, and screenshot or runtime evidence so a leaderboard-style success score can be reconciled against the actual user-visible workflow.

## Evaluation Signals

- Whether the request package preserved source authority and task boundaries.
- Whether retrieval and context additions were relevant, attributed, and sufficient.
- Whether tool calls used the intended schemas, order, permissions, and inputs.
- Whether retries corrected real failures instead of hiding them.
- Whether approval waits, blocked states, and handoffs were visible.
- Whether safety, governance, cost, and latency constraints held across the run.
- Whether final verification matched the risk surface of the work.
- Whether independent agents or repeated runs agree on the evidence-backed result and expose the same residual risks.
- Whether model or harness changes were tested against representative local terminal, coding, review, and repair tasks before autonomy changed.
- Whether a behavior needs a single-step regression check, a full-run outcome check, live trace monitoring, or a capability benchmark.
- Whether the eval includes the environment, instruction, created artifacts, tool trace, and deterministic checker needed to reproduce the outcome.
- Whether platform-layer decisions, model routing, memory access, retrieval, tool calls, and sandbox boundaries are visible in the trace.
- Whether an agentic test loop records planned path, observations, adaptations, and stopping criteria.
- Whether step-level scoring can explain which action improved, degraded, or failed to change the task state.
- Whether emerging internal-state signals are clearly separated from deployable assurance evidence such as tests, builds, traces, and review outcomes.
- Whether performance optimization trajectories preserve profiling evidence, correctness checks, speedup measurement, and benchmark-shortcut controls.
- Whether long-horizon task trajectories show planning, multi-file state management, verification pacing, and sustained recovery from intermediate failures.
- Whether failure-diagnosis traces identify the earliest consequential error instead of only summarizing the final failed state.
- Whether completion proof ties specification, artifacts, evidence, independent verification, and final handoff together.
- Whether calibration tasks cover end-to-end builds, reconstruction, and production-like delivery paths when public benchmark scope moves beyond issue patches.
- Whether benchmark, harness, and environment components are separated enough to compare agent systems without hiding setup or runtime differences.
- Whether tool-call order, argument correctness, state-change results, recovery behavior, cost, and safety controls match the intended path.
- Whether graph/run/node identifiers, routers, joins, deterministic functions, policies, budgets, human checkpoints, and issue-grouping records explain the path in multi-agent workflows.
- Whether repository-level issue-resolution runs preserve requirement clarification, implicit-requirement recovery, implementation planning, and final patch evidence as separate trajectory stages.
- Whether the evaluated run preserves task, dataset, environment, trial, job, solver, scorer, sandbox, log, and tool evidence strongly enough to reproduce and attribute the path.
- Whether model, context, harness, memory, permission, tool, environment, and scorer failures are separated before a trajectory verdict is used to change a workflow.
- Whether execution location, egress, inference route, session records, eval data, memory writes, containment state, external milestone state, and behavior deviations are visible in the run history.
- Whether deployed behavior, retries, tool-call traces, recovery steps, screenshots, and runtime evidence support frontend-agent or web-development verdicts.

The [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) adds high-impact action and persistent-agent trajectory evidence. Trajectory evals should inspect cross-session memory, follow-up task creation, action sequences, capability metadata, safety-specific eval checkpoints, and human oversight decisions when agents can operate beyond ordinary code text.

## Practice Boundaries

- Evaluate tool-using agent workflows with trace and transcript evidence, not only final outputs.
- Record the model or routing policy when available, but do not block evaluation when a tool provider hides exact routing.
- Treat public long-horizon benchmarks as context for benchmark design, not as proof that a local workflow is reliable.
- Keep benchmark entities and vendor products upstream unless a local acceptance rule depends on them.
- Use human review when trajectory evidence contains judgment-heavy product, security, architecture, or operational tradeoffs.
- Track cross-run agreement and disagreement as evidence about task clarity, retrieval sufficiency, and rubric quality.
- Treat public benchmark gains as candidate eval inputs, not as local authorization to increase tool or write access.
- Use behavioral unit evals for expected next actions, integration evals for final artifacts, online evals for deployed trend monitoring, and benchmarks for capability-level comparison.
- Prefer environment-backed eval datasets for long-running agents when correctness depends on filesystem, tool, browser, or service state.
- Evaluate platform agent runs at the trajectory level when control-plane, runtime, memory, retrieval, or tool decisions affect trust.
- Use step-local diagnostics when final-run scores hide which agent action caused success, drift, or failure.
- Treat model-internal probing as research context unless it is backed by observable verification evidence in the local workflow.
- Fold low-signal trace detail into saliency summaries only when the raw trace, tests, and source evidence remain available for audit.
- Use test-failure reports as investigation priors, not as substitutes for source inspection and reproducible verification.
- Record provider adapter, side-effect permissions, trace assertions, cost signals, and sandbox checks when the evaluated agent surface changes.
- Preserve proof artifacts and independent verifier outputs as first-class trajectory evidence for delegated coding claims.
- Expand local trajectory suites when benchmark scope shifts toward realistic end-to-end delivery, architecture reconstruction, or production task realism.
- Separate benchmark, harness, and environment evidence when comparing agent systems across coding, research, productivity, or tool-use tasks.
- Score tool-call order, argument correctness, state-change results, recovery behavior, cost, and safety controls alongside final-task outcome.
- Preserve graph topology, run identifiers, node identifiers, routed decisions, grouped failures, and human checkpoint records when evaluating multi-agent systems.
- Preserve production failure traces, proposed fixes, experiment results, deployed versions, and regression-monitor signals when evaluating agent-loop improvements.
- Record benchmark domain coverage, task provenance, contamination controls, execution environment, scoring rules, and produced artifacts before using an agent benchmark to justify workflow expansion.
- Prefer representative local workflow calibration when public benchmark tasks do not match the repository, toolchain, data sensitivity, or approval path.
- Preserve task provenance, contamination controls, harness configuration, verifier behavior, and cost per completed task before using benchmark results to justify workflow expansion.
- Evaluate retrieval, memory, runtime constraints, tool authorization, abstention, refusal, and human-review paths as deployment evidence, not as model-only score details.
- Diagnose failed or flat eval runs with an attribution taxonomy before changing prompts, model routes, or autonomy levels.
- Convert production traces into trajectory-level regression cases when trace evidence can explain which step, tool call, retrieval span, or prompt version caused the failure.
- Use intermediate requirement-clarification and implementation-plan evidence when evaluating repository-level issue resolution so implicit-requirement failures are not hidden by final patch scoring.
- Keep evaluation-framework concepts as local harness evidence while routing broad Harbor, Inspect, benchmark, provider, and sandbox-product coverage upstream.
- Preserve deployed behavior, retries, tool-call traces, recovery steps, screenshots, and runtime evidence when evaluating frontend or web-development agents.
- Evaluate whether the trajectory preserved containment boundaries, approved memory/tool provenance, external CI or deployment truth, and behavior-baseline deviations before treating completion as reliable.

## Authoritative Sources

- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
- [Topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [representative workflow calibration](representative-workflow-calibration.md)
- [verification loops and evals](verification-loops-and-evals.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)
- [user-visible progress and runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [Agent evals source](../../../raw/processed/Making Agent Evals Isn’t As Hard As You Think!.md)
- [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 7 topic news collector source](../../../raw/processed/2026-07-07/ai-dev-wiki-topic-news-collector-2026-07-07T203239-0400.json)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json)
- [July 12 leaf update watch source](../../../raw/processed/2026-07-12/ai-dev-wiki-leaf-update-watch-2026-07-12T210403-0400.json)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)
- [July 17 leaf update watch source](../../../raw/processed/2026-07-17/ai-dev-wiki-leaf-update-watch-2026-07-17T210227-0400.json)
- [July 20 topic news collector source](../../../raw/processed/2026-07-20/ai-dev-wiki-topic-news-collector-2026-07-20T203200-0400.json)
- [July 21 topic news collector source](../../../raw/processed/2026-07-21/ai-dev-wiki-topic-news-collector-2026-07-21T203101-0400.json)
- [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json)
- [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json)
- [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json)
- [July 29 topic news collector source](../../../raw/processed/2026-07-29/ai-dev-wiki-topic-news-collector-2026-07-29T203119-0400.json)
- [August 5 leaf update watch source](../../../raw/processed/2026-08-05/ai-dev-wiki-leaf-update-watch-2026-08-05T210155-0400.json)
- [LangSmith Engine clipping](../../../raw/processed/Quickstart Autonomous Agent Improvement with LangSmith Engine.md)
- [LLM observability quality gates](llm-observability-quality-gates.md)
- [August 11 topic news collector source](../../../raw/processed/2026-08-11/ai-dev-wiki-topic-news-collector-2026-08-11T203048-0400.json)
- [Harbor core concepts clipping](../../../raw/processed/Core Concepts.md)
- [Harbor motivation clipping](../../../raw/processed/Motivation.md)
- [Inspect clipping](../../../raw/processed/Inspect.md)
- [August 12 topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json)
- [August 15 topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [August 17 topic news collector source](../../../raw/processed/2026-08-17/ai-dev-wiki-topic-news-collector-2026-08-17T203101-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification-and-evals](index.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [agent harness components](../application-patterns/agent-harness-components.md)
- [code review evals and rubrics](code-review-evals-and-rubrics.md)
- [LLM observability quality gates](llm-observability-quality-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-08-29 with persistent-agent, action-sequence, capability-metadata, high-impact-tool, safety-eval, and oversight trajectory signals.
- Maintained on 2026-07-23 with workflow-fit benchmark routing, graph-stage, deterministic-step, subagent-streaming, and long-horizon task evidence.
- Created on 2026-06-24 to hold trajectory, trace, and intermediate-decision evaluation practice for agent workflows.
- Maintained on 2026-06-27 with cross-run agreement, environment-design, and benchmark-to-local-suite routing rules.
- Maintained on 2026-06-30 with behavioral unit, integration, online, and benchmark eval shape guidance.
- Maintained on 2026-07-02 with environment-backed stateful-agent eval datasets and deterministic checker requirements.
- Maintained on 2026-07-04 with platform-layer traces and agentic-testing trajectory evidence.
- Maintained on 2026-07-07 with step-level action scoring and internal-state probing as research-only assurance context.
- Maintained on 2026-07-10 with performance, long-horizon, and failure-diagnosis trajectory evidence.
- Maintained on 2026-07-12 with provider-adapter, side-effect, trace-assertion, cost, and sandbox signals for coding-agent trajectories.
- Maintained on 2026-07-14 with proof-loop artifacts and end-to-end delivery benchmark signals for trajectory evaluation.
- Maintained on 2026-07-17 with benchmark-harness-environment separation, asynchronous execution state, tool-call scoring, state-change checks, recovery behavior, cost, and safety controls.
- Maintained on 2026-07-22 with graph/run/node identifiers, routed decisions, human checkpoints, issue grouping, and multi-agent topology evidence.
- Maintained on 2026-07-24 with multi-domain benchmark, contamination-control, reproducible-harness, and local-calibration guidance.
- Maintained on 2026-07-26 with benchmark-realism, cost-per-task, system-level safety, retrieval, memory, tool-authorization, refusal, and human-escalation evaluation guidance.
- Maintained on 2026-07-29 with failure-attribution taxonomy guidance for non-improving agent eval runs.
- Maintained on 2026-08-05 with production-trace, experiment, deployment, and regression-monitor evidence for agent-loop improvements.
- Maintained on 2026-08-07 with trace-to-regression, component-score, annotation, and release-decision evidence.
- Maintained on 2026-08-11 with repository-level issue-resolution trajectory checks for requirement clarification, implicit requirements, planning, and final patch evidence.
- Maintained on 2026-08-12 with Harbor, Inspect, and model/context/harness separation as trajectory failure-attribution evidence.
- Maintained on 2026-08-15 with execution-location, egress, inference-route, retained-eval, containment, memory-provenance, repository-skill baiting, behavior-baseline, and external-milestone trajectory evidence.
- Maintained on 2026-08-17 with frontend-agent deployed-behavior, retry, tool-call trace, recovery, screenshot, and runtime evidence.
