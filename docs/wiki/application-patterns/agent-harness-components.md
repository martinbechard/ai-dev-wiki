---
type: "Application Pattern"
title: "Agent Harness Components"
description: "An agent harness is the fixed runtime architecture that lets a model act, observe the result, and continue toward a goal."
tags: ["application-patterns"]
---

# Agent Harness Components

## Current Understanding

An agent harness is the fixed runtime architecture that lets a model act, observe the result, and continue toward a goal. The [agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md) distinguishes a harness from a framework: a framework gives a human abstractions to assemble, while a harness ships an operating loop, tool registry, context control, persistence, hooks, and permission layer that an agent can use directly. [Agent session recovery](agent-session-recovery.md) and [agent lifecycle hooks](agent-lifecycle-hooks.md) own those focused details; this page remains the component map.

The local harness component model includes an iteration loop, context management and compaction, a tool and skill registry, subagent management, built-in primitives, session persistence, dynamic instruction assembly, lifecycle hooks, and dispatch-time permissions. These components support the broader [application harness patterns](application-harness-patterns.md) page by naming the runtime pieces that must be present before a model-backed application can safely do work.

The [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json) reinforces harness engineering as an implementation discipline with categories for architecture, context and working state, execution substrates, protocols, evaluation, observability, guardrails, and reference implementations. The local page keeps those as component categories, while named SDKs, frameworks, memory systems, and protocols remain upstream-owned.

The [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json) and [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) add execution-substrate and control-plane signals. Runner groups, parallel workflow steps, remote startup checklists, compiled agent artifacts, content hashes, provenance, and tamper-evident logs are harness components when they determine how an agent environment is provisioned, observed, or reproduced.

The [context collapse source](../../../raw/processed/When Context Collapses Teaching Agents to Detect and Recover from Lost Memory.md) and [lost-in-the-middle source](../../../raw/processed/So Long and Thanks for All the Context.md) add a recovery component to the harness. Multi-step agents need progress files, append-only artifacts, startup continuity checks, and rehydration summaries so a session can resume from disk after compaction, crash, or long-context attention loss.

The [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json) reinforces harness design as environment design: information access, tool boundaries, context feeds, task constraints, progress visibility, and feedback loops are first-class components rather than prompt-only concerns.

The [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json) and [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json) add failure-attribution and managed-control components. A harness should expose task setup, context construction, tool constraints, scoring, traces, lifecycle hooks, deterministic configuration validation, and permission scopes as inspectable surfaces. That keeps agent quality from being treated as a model-only property.

The [harness engineering masterclass source](../../../raw/processed/Harness Engineering Masterclass Technical Deep Dive on how to build Agentic Systems.md) adds a primitive-by-primitive operating model. Instructions, context delivery, context management, tool interfaces, execution environments, durable state, orchestration, subagents, skill layers, verification, and observability should be treated as separable harness responsibilities. When an agent fails, the local diagnostic should ask which primitive failed before treating the model as the only cause.

The [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json) reinforces the harness as the execution boundary around model reasoning. Execution environment, memory, filesystem access, tool access, subagent orchestration, capability bridges, durable pause and resume, and deterministic evaluation scripts are harness responsibilities. A harness should distinguish orchestration-by-code from broad shell access and make isolated environments inspectable for long-running agent work.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) adds an agent-platform layering signal. Orchestration, model inference, tools, memory, retrieval, control plane, and runtime should be treated as separable platform responsibilities so local architecture decisions can assign ownership, telemetry, policy enforcement, and runtime isolation without collapsing the whole system into prompt design.

The [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json) extends that platform boundary to non-code desktop and file agents. File-system readers, work folders, output folders, edit previews, operation-specific approvals, and audit trails are harness components when an agent can inspect or change local documents outside a repository.

The [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md), [Deepsec clipping](../../../raw/processed/vercel-labsdeepsec Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents.md), and [Just Bash clipping](../../../raw/processed/vercel-labsjust-bash Bash for Agents.md) add three harness-component examples without making local product leaves. Chat-agent surfaces need event subscriptions, thread state, adapter boundaries, rich response rendering, and durable workflow handoff when agents live inside collaboration channels. Security scanning harnesses need scan discovery, AI investigation, resumable processing, revalidation, exportable findings, and isolated worker execution. Virtual shell packages are useful as execution substrates for tests and examples when the harness labels simulation boundaries and preserves real verification separately.

The [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json) also reinforces harness instrumentation as an operating control. Cost, sandbox trials, scripted verifiers, traces, datasets, ownership metadata, gateway policies, and hub-and-spoke tool access are component responsibilities when agents run recurring workflows rather than one-off prompts.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) adds shared operation-path and managed-runtime signals. A harness that exposes the same operation through desktop UI and MCP should keep one tested backend command path, and a managed code-execution platform needs runtime isolation, blast-radius controls, audit logs, egress policy, and permission granularity as explicit components.

The [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json) and [July 10 leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json) add bounded-loop, harness-taxonomy, and managed-session signals. Long-running loops need budget envelopes, step ceilings, stall detection, output-path verification, approval gates, and per-step traces. Maintained harness taxonomies are useful locally when they sharpen component ownership for planning artifacts, context delivery, permissions, memory, orchestration, verification, observability, sandboxing, and session governance rather than becoming product catalogs.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) and [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json) add production-control, proof-loop, and programmatic-tool signals. A production coding-agent harness should make isolation, scoped identity, human approvals, monitoring, audit trails, model routing, and proof artifacts explicit runtime components. Programmatic tool calling and repo-task proof loops reinforce that completion claims should be converted into inspectable specifications, evidence bundles, independent verification, and traceable tool execution before the harness treats work as done.

The [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json) and [July 15 leaf update watch source](../../../raw/processed/2026-07-15/ai-dev-wiki-leaf-update-watch-2026-07-15T210218-0400.json) add execution-environment, trust-layer, and loop-termination signals. Coding-agent harnesses need isolated disposable workspaces with filesystem, shell, package, network, and step-persistent state when they must execute and retry code. They also need MCP trust decisions, path-boundary checks, spend caps, runaway-loop termination, and data-residency controls as runtime components rather than optional product settings.

The [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json) and [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json) add managed-agent and sandbox evidence. Harnesses should expose effort controls, lifecycle webhooks, session-start events, memory-store events, thread-level subagent deltas, deterministic containment, egress controls, package-access controls, and brokered just-in-time access as explicit components rather than burying them in model prompts.

The [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json) adds harness-owned memory and eval evidence. Coding-agent memory should be injected by deterministic cues and audit logs, and benchmark harnesses should preserve task provenance, contamination resistance, reproducible setup, and scoring surfaces as first-class runtime components.

The [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) adds persistent workspace and agent-host evidence. Durable filesystem state, sandbox command execution, faster multi-file review surfaces, assisted tool approvals, chat visibility, terminal diff links, and dedicated agent host processes are harness components when they affect handoff quality and event-driven review loops.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds [agent environment readiness](agent-environment-readiness.md) as a focused harness component. Coding-agent environments should expose setup state, dependency readiness, secret isolation, restart behavior, long-job durability, and artifact persistence as inspectable runtime surfaces before teams rely on longer unattended workflows.

## Practice Boundaries

- Treat the outer iteration loop as the runtime boundary that decides when to call tools, observe results, continue, or stop.
- Keep tool descriptors, permissions, and handlers in a registry so execution can be inspected and controlled.
- Persist session events in an append-only form when resume, audit, or crash recovery matters.
- Assemble durable instructions from stable project files without letting dynamic context break source authority.
- Use lifecycle hooks for policy, logging, and observability without putting every control in model instructions.
- Enforce permissions before tool execution, especially for file writes, shell commands, network access, and external systems.
- Keep harness categories explicit enough that context, execution, evaluation, observability, and guardrail responsibilities do not collapse into a single framework choice.
- Route named framework or SDK comparisons upstream unless the local decision is about which harness component the workflow needs.
- Treat environment provisioning, runner selection, parallel setup, compiled configuration, provenance, and tamper-evident logs as harness responsibilities for long-running or high-impact agent work.
- Add progress and artifact stores when a workflow can span sessions, hit context pressure, or require audit after interruption.
- Run startup continuity checks that compare progress records with the last material output before resuming work.
- Treat context feeds, task constraints, progress visibility, and feedback loops as harness design surfaces, not as incidental prompt text.
- Include task setup, context construction, tool constraints, scoring, lifecycle hooks, configuration validation, and permission scopes in the harness boundary.
- Preserve traces and failure-attribution fields so semantic failures can be debugged without guessing from the final answer.
- Diagnose failures against the harness primitive that owns the missing support: instruction, context, tool schema, environment, durable state, orchestration, delegation, skill procedure, verification, or traceability.
- Treat execution environment, memory, filesystem access, tool bridges, subagent orchestration, durable pauses, and deterministic evaluators as explicit harness components.
- Prefer narrow capability bridges and inspectable isolated environments when agents execute generated code or delegate dynamic subwork.
- Separate orchestration, model routing, memory, retrieval, tools, control plane, and runtime ownership when designing production agent platforms.
- Preserve trace evidence across platform layers so long-running agent behavior can be debugged by component responsibility.
- Treat desktop file access, work folders, edit previews, operation-specific approvals, and audit trails as harness responsibilities when agents operate on local documents.
- Treat chat adapters, thread subscriptions, response rendering, and durable workflow handoff as harness responsibilities for collaboration-channel agents.
- Treat scan discovery, AI investigation, resumable processing, revalidation, finding export, and isolated workers as harness responsibilities for agent-powered security review.
- Keep simulated shell substrates separate from host execution evidence when they are used for agent tests, examples, or comparison runs.
- Make sandbox trials, scripted verifiers, trace records, datasets, cost telemetry, and gateway policy evidence part of the harness boundary for recurring agent workflows.
- Use one tested backend operation path when human UI controls and MCP tools perform the same action.
- Treat runtime isolation, egress policy, blast-radius controls, audit logs, and permission granularity as harness components for code-enabled managed agent platforms.
- Bound autonomous loops with step ceilings, cost budgets, stall safeguards, and explicit approval gates before increasing unattended work volume.
- Verify declared output paths and preserve per-step traces so long-running loops can be inspected, resumed, or stopped without relying on a final summary.
- Use harness taxonomies to assign ownership for planning, context, permissions, memory, orchestration, verification, observability, and sandboxing components.
- Include isolation, scoped identity, approval gates, monitoring, audit trails, and model-routing policy as harness components for production coding agents.
- Convert done claims into specifications, evidence bundles, independent verification results, and traceable tool execution before a harness marks a delegated task complete.
- Provide isolated disposable workspaces for code execution, dependency setup, retry loops, and runtime feedback when generated code may run before human review.
- Treat MCP trust decisions, canonical path checks, spend caps, loop termination, and data-residency placement as harness components for autonomous coding workflows.
- Model long-running managed agents with lifecycle webhooks, seeded initial session state, explicit effort controls, optimistic update-version handling, memory-store events, and stream deltas.
- Treat production voice or chat agents as harnesses with scoped knowledge, scoped system access, guardrails, simulations, graders, escalations, approvals, and tested update proposals.
- Design gateway-style agent harnesses so identity, authorization, workflow coverage, and audit evidence remain externalized instead of buried inside one agent session.
- Deliver memory from deterministic path, symbol, event, semantic, or time cues with traceable source links instead of relying on model-initiated recall.
- Preserve benchmark task construction, contamination controls, execution setup, scoring, and artifact evidence as harness components when eval results guide workflow authorization.
- Treat persistent filesystems, sandbox execution, agent host processes, approval UX, multi-file review surfaces, and terminal diff links as harness components when they determine reviewability.
- Treat environment setup, dependency availability, secret scoping, restart semantics, and long-job durability as harness components rather than prompt-only assumptions.

## Authoritative Sources

- [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json)
- [July 23 topic news collector source](../../../raw/processed/2026-07-23/ai-dev-wiki-topic-news-collector-2026-07-23T203146-0400.json)
- [Agent harness source](../../../raw/processed/What is an Agent Harness? and How to build a great one!.md)
- [June 24 leaf update watch source](../../../raw/processed/2026-06-24/ai-dev-wiki-leaf-update-watch-2026-06-24T210337-0400.json)
- [June 26 topic news collector source](../../../raw/processed/2026-06-26/ai-dev-wiki-topic-news-collector-2026-06-26T203331-0400.json)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [Context collapse source](../../../raw/processed/When Context Collapses Teaching Agents to Detect and Recover from Lost Memory.md)
- [Lost-in-the-middle source](../../../raw/processed/So Long and Thanks for All the Context.md)
- [June 27 topic news collector source](../../../raw/processed/2026-06-27/ai-dev-wiki-topic-news-collector-2026-06-27T203047-0400.json)
- [June 28 topic news collector source](../../../raw/processed/2026-06-28/ai-dev-wiki-topic-news-collector-2026-06-28T203100-0400.json)
- [June 28 leaf update watch source](../../../raw/processed/2026-06-28/ai-dev-wiki-leaf-update-watch-2026-06-28T210247-0400.json)
- [Harness engineering masterclass source](../../../raw/processed/Harness Engineering Masterclass Technical Deep Dive on how to build Agentic Systems.md)
- [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 5 topic news collector source](../../../raw/processed/2026-07-05/ai-dev-wiki-topic-news-collector-2026-07-05T203304-0400.json)
- [July 6 leaf update watch source](../../../raw/processed/2026-07-06/ai-dev-wiki-leaf-update-watch-2026-07-06T210312-0400.json)
- [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md)
- [Deepsec clipping](../../../raw/processed/vercel-labsdeepsec Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents.md)
- [Just Bash clipping](../../../raw/processed/vercel-labsjust-bash Bash for Agents.md)
- [application harness patterns](application-harness-patterns.md)
- [subagent coordination](../agent-workflows/subagent-coordination.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 10 topic news collector source](../../../raw/processed/2026-07-10/ai-dev-wiki-topic-news-collector-2026-07-10T203059-0400.json)
- [July 10 leaf update watch source](../../../raw/processed/2026-07-10/ai-dev-wiki-leaf-update-watch-2026-07-10T210209-0400.json)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 14 leaf update watch source](../../../raw/processed/2026-07-14/ai-dev-wiki-leaf-update-watch-2026-07-14T210238-0400.json)
- [July 15 topic news collector source](../../../raw/processed/2026-07-15/ai-dev-wiki-topic-news-collector-2026-07-15T203238-0400.json)
- [July 15 leaf update watch source](../../../raw/processed/2026-07-15/ai-dev-wiki-leaf-update-watch-2026-07-15T210218-0400.json)
- [July 22 topic news collector source](../../../raw/processed/2026-07-22/ai-dev-wiki-topic-news-collector-2026-07-22T203140-0400.json)
- [July 24 topic news collector source](../../../raw/processed/2026-07-24/ai-dev-wiki-topic-news-collector-2026-07-24T203056-0400.json)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [application harness patterns](application-harness-patterns.md)
- [agent session recovery](agent-session-recovery.md)
- [agent lifecycle hooks](agent-lifecycle-hooks.md)
- [agent environment readiness](agent-environment-readiness.md)
- [AI process layer and workflow state](ai-process-layer-and-workflow-state.md)
- [user-visible progress and runtime telemetry](user-visible-progress-and-runtime-telemetry.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-07-23 with managed-agent lifecycle hooks, session events, memory events, subagent deltas, containment, egress, package-access, and brokered-access components.
- Maintained on 2026-07-27 with persistent filesystem, sandbox execution, agent-host, tool-approval, multi-file-review, and terminal-diff-link harness components.
- Maintained on 2026-07-30 with agent-environment readiness components for setup, secrets, restart, and long-job durability.
- Created on 2026-06-23 to hold harness runtime components separately from broader application architecture.
- Maintained on 2026-06-24 with public harness taxonomy signals for context, execution, evaluation, observability, and guardrails.
- Maintained on 2026-06-26 with runner, parallel-step, remote-startup, compiled-configuration, provenance, and tamper-evident logging signals.
- Maintained on 2026-06-27 with progress stores, startup continuity checks, rehydration summaries, and context-feed design signals.
- Maintained on 2026-06-28 with harness-level failure attribution, lifecycle hooks, deterministic configuration validation, and trace evidence.
- Maintained on 2026-06-30 with the harness primitive taxonomy and primitive-level failure diagnostics.
- Maintained on 2026-07-02 with execution-boundary, isolated-environment, durable-pause, and deterministic-evaluator signals.
- Maintained on 2026-07-04 with agent-platform layering, control-plane ownership, and cross-layer trace evidence.
- Maintained on 2026-07-05 with desktop file-agent permission, folder, edit-preview, and audit-boundary signals.
- Maintained on 2026-07-06 with chat-agent adapter, security-scanning harness, virtual shell, and recurring workflow instrumentation components.
- Maintained on 2026-07-09 with shared UI-and-MCP operation paths and code-enabled managed-runtime isolation controls.
- Maintained on 2026-07-10 with bounded loop controls, output-path verification, per-step traces, and harness taxonomy ownership.
- Maintained on 2026-07-14 with production control components, programmatic tool execution, and proof-loop evidence for delegated completion claims.
- Maintained on 2026-07-15 with isolated disposable workspaces, MCP trust decisions, path-boundary checks, spend caps, loop termination, and data-residency controls.
- Maintained on 2026-07-22 with managed-agent lifecycle hooks, seeded sessions, stream deltas, production-agent simulations, and gateway-style identity controls.
- Maintained on 2026-07-24 with cue-delivered memory, benchmark provenance, contamination-resistance, setup, scoring, and artifact-evidence components.
