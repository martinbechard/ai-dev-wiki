---
type: "Application Pattern"
title: "AI Process Layer And Workflow State"
description: "The AI process layer is the application tier between user intent and backend systems."
tags: ["application-patterns"]
---

# AI Process Layer And Workflow State

## Current Understanding

The AI process layer is the application tier between user intent and backend systems. It chooses prompts, models, retrieval steps, tools, verifiers, and human gates while preserving workflow state that the model itself does not remember.

Workflow state includes conversation history, selected files, retrieved context, tool results, forks, checkpoints, approvals, failures, and compaction summaries. The process layer controls which state becomes model context, which state remains application state, and which state must be visible to users or auditors.

The [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json) adds operational-readiness and workflow-memory signals. Agentic applications need observable operational systems, trusted data connections, permission controls, approval checkpoints, citations, logging, state memory, and handoff paths before they can safely automate work. The process layer owns those state transitions even when the model, framework, or product supplies the language capability.

The [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md) adds a collaboration-channel process-layer pattern. Chat bots and agents need event intake, thread subscription state, platform adapters, response rendering, and durable workflow state around the model call. When agent responses stream into Slack, Teams, Discord, or similar surfaces, the process layer should preserve requester identity, thread context, generated artifacts, tool evidence, and follow-up state separately from the model transcript.

The [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json) adds long-running runtime and memory signals. Agent applications should separate model context from durable execution history, event logs, human waits, state buckets, memory retention, and update semantics. Runtime frameworks, memory products, and cloud services stay upstream-owned; locally, the process layer must decide which state is authoritative, resumable, visible, and eligible for rehydration.

The [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) adds [declarative agent workflow artifacts](declarative-agent-workflow-artifacts.md). This page keeps the process-layer boundary: runtime state, approval state, and checkpoint authority still need application ownership when orchestration is loaded from a workflow artifact.

The [July 31 topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json) adds queue-backed orchestration and autonomous test execution as process-layer state examples. A queue item, single-node trace, credential reference, remote-control viewing session, and human intervention event should remain durable workflow state rather than transient model context.

The [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json) adds long-horizon harness evidence for state policy. A manager, fresh-context executor, read-only auditor, execution memory, and learned state-update policy all reinforce that the process layer should decide which task state is durable, which state is injected into a fresh model context, and which state is locked as audit-only evidence.

The August 14 raw sources add held-tool, build, history, and behavior-state examples. The [topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json) records approval requests, pending metadata, queued prompts, queued shell commands, pinned prompts, rewind recovery, and service disruptions. The [leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json) records prebuilt build state, prior-work reconstruction, incident evidence fields, and purpose-based behavioral baselines. Locally, those states belong in the process layer so users and auditors can tell what the model saw, what was waiting, what environment ran, and whether behavior matched the declared task.

The [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json) adds embedded product-workflow and conversation-context evidence. Human-agent collaboration works better when visible channel context, permissions, workflow objects, handoff cycles, and decision state are first-class application state rather than ad hoc prompts. Locally, product agents should store which conversation or workflow context was used, which private context was excluded, what the agent drafted or prepared, and which human decision accepted, redirected, or rejected the output.

The August 21 sources add persistent goal, orchestration-artifact, and collaborative-channel evidence:

- The [leaf update watch source](../../../raw/processed/2026-08-21/ai-dev-wiki-leaf-update-watch-2026-08-21T210236-0400.json) records long-lived goals, event sources, progress, and steering as stateful managed-agent primitives.
- The [topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json) records coding-agent orchestration as a governed process artifact and collaborative channels as places where intermediate work becomes observable.
- Locally, the process layer should persist goals, event subscriptions, orchestration artifacts, intermediate drafts, approvals, and handoff decisions outside the model transcript.

The [August 27 leaf update watch source](../../../raw/processed/2026-08-27/ai-dev-wiki-leaf-update-watch-2026-08-27T210207-0400.json) adds declarative-workflow and persistent-harness state evidence. YAML workflow actions, checkpoint stores, human input requests, telemetry hooks, persistent REPL histories, memories, skill state, subagent specifications, recovery state, resource accounting, and verification records belong in durable process state when they control long-running agent behavior.

The [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json) adds AI-native workflow-state evidence. Cross-surface agent actions that move between chat, CRM, Slack, MCP, APIs, CLI tools, repositories, and approval points should preserve decision owner, automation owner, application boundary, approval point, action evidence, and rollback path as workflow state.

## Practice Boundaries

- Put an AI process layer between the interface and backend when the workflow needs tools, state, validation, or approvals.
- Treat the model as stateless across requests unless the harness resends or summarizes the required state.
- Store workflow state in deterministic application structures rather than only in conversation text.
- Use different context, tools, models, and validation checks for different workflow steps when that improves cost, latency, or accuracy.
- Preserve checkpoints and failure evidence when a long-running workflow needs review, retry, or handoff.
- Treat operational telemetry, approval checkpoints, citations, logs, state memory, and handoff records as process-layer state, not only UI or model context.
- Require healthy, observable upstream systems before letting an agent workflow automate across hybrid tools or business processes.
- Store collaboration-channel event, thread, adapter, requester, tool-evidence, and follow-up state outside the model transcript.
- Treat rich chat cards, streamed responses, and channel posts as workflow outputs that need the same provenance and approval handling as other agent artifacts.
- Separate model context from durable execution history, event logs, human waits, memory retention, and update semantics.
- Define which state bucket is authoritative before a long-running agent workflow resumes, retries, or asks for human input.
- Use [declarative agent workflow artifacts](declarative-agent-workflow-artifacts.md) when branching, human approvals, checkpoints, and tool-call policy need source review before runtime execution.
- Store queue events, execution-node traces, credential-reference choices, remote-viewing status, and human intervention events as durable workflow state when autonomous tests or flows run.
- Treat long-horizon manager state, executor context, auditor observations, and learned memory updates as separate process-layer state channels with explicit authority.
- Store approval-request state, queued work, pinned context, rewind points, provider-status checks, build provenance, prior-work history, incident evidence, and purpose baselines outside the model transcript when they affect execution or review.
- Store shared-channel context, workflow-object permissions, excluded private context, reasoning reconstruction, draft artifacts, and human accept or redirect decisions as process-layer state for human-agent collaboration.
- Treat agent-first product workflows as application architecture: context, permissions, governance, and handoff state need durable owners before agents can act inside recurring work.
- Persist long-lived goals, event subscriptions, steering state, orchestration artifacts, intermediate channel-visible work, approvals, and handoff decisions as application state outside the model transcript.
- Persist declarative action state, checkpoints, human-input requests, telemetry hooks, REPL histories, memories, subagent specs, recovery state, resource accounting, and verification records outside the model transcript for long-running harnesses.

## Authoritative Sources

- [August 29 topic news collector source](../../../raw/processed/2026-08-29/ai-dev-wiki-topic-news-collector-2026-08-29T003241Z.json)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Application harness patterns](application-harness-patterns.md)
- [Orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [July 2 leaf update watch source](../../../raw/processed/2026-07-02/ai-dev-wiki-leaf-update-watch-2026-07-02T210052-0400.json)
- [Chat SDK clipping](../../../raw/processed/Universal chat layer for building bots and agents.md)
- [July 7 leaf update watch source](../../../raw/processed/2026-07-07/ai-dev-wiki-leaf-update-watch-2026-07-07T210326-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [July 31 topic news collector source](../../../raw/processed/2026-07-31/ai-dev-wiki-topic-news-collector-2026-07-31T203150-0400.json)
- [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json)
- [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json)
- [August 14 leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json)
- [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json)
- [August 21 topic news collector source](../../../raw/processed/2026-08-21/ai-dev-wiki-topic-news-collector-2026-08-21T203246-0400.json)
- [August 21 leaf update watch source](../../../raw/processed/2026-08-21/ai-dev-wiki-leaf-update-watch-2026-08-21T210236-0400.json)
- [August 27 leaf update watch source](../../../raw/processed/2026-08-27/ai-dev-wiki-leaf-update-watch-2026-08-27T210207-0400.json)
- [declarative agent workflow artifacts](declarative-agent-workflow-artifacts.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [structured output and drafter patterns](structured-output-and-drafter-patterns.md)
- [user-visible progress and runtime telemetry](user-visible-progress-and-runtime-telemetry.md)
- [context selection and compaction](../context-architecture/context-selection-and-compaction.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-08-29 with AI-native orchestration, cross-surface action, approval-point, owner, evidence, and rollback workflow-state signals.
- Created on 2026-06-23 from local source guidance on AI process layers, workflow state, validation loops, tools, checkpoints, and compaction.
- Maintained on 2026-07-02 with operational-readiness, workflow-memory, citation, logging, approval, and handoff-state requirements.
- Maintained on 2026-07-06 with collaboration-channel event, thread, adapter, streamed-response, and follow-up state requirements.
- Maintained on 2026-07-07 with long-running execution history, event-log, human-wait, state-bucket, and memory-retention boundaries.
- Maintained on 2026-07-28 with declarative workflow, branching, tool-call, human-approval, checkpoint, and resume-state guidance.
- Maintained on 2026-07-31 with queue event, execution-node trace, credential-reference, remote-viewing, and human-intervention state guidance.
- Maintained on 2026-08-08 with manager, fresh-context executor, read-only auditor, and learned state-policy boundaries.
- Maintained on 2026-08-14 with approval-request, queued-work, pinned-context, rewind, status-check, build-provenance, prior-work-history, incident-evidence, and behavior-baseline state boundaries.
- Maintained on 2026-08-20 with embedded human-agent workflow state for channel context, permissions, private-context exclusion, draft artifacts, and human accept or redirect decisions.
- Maintained on 2026-08-21 with durable-goal, event-subscription, steering-state, orchestration-artifact, intermediate-work, approval, and handoff state guidance.
- Maintained on 2026-08-27 with declarative workflow, checkpoint, human-input, telemetry, persistent REPL, memory, subagent, recovery, resource-accounting, and verification state guidance.
