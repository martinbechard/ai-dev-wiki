---
type: "Agent Workflow"
title: "Terminal Agent Workflows"
description: "Terminal agent workflows run coding-agent work through shell or IDE terminal sessions where command safety and session evidence are part of the workflow."
tags: ["agent-workflows"]
---

# Terminal Agent Workflows

## Current Understanding

Terminal agent workflows run coding-agent work through shell or IDE terminal sessions where command safety and session evidence are part of the workflow. The local practice is to treat the terminal session as a governed workflow surface, not only a convenient prompt interface.

The [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) records terminal coding agents, IDE-managed skills, and destructive-command denial improvements as product evidence for this local pattern. Broad product coverage belongs upstream in [OpenAI Codex](../../../upstream-ai-wiki/developer-tools/openai-codex.md), [Claude Code](../../../upstream-ai-wiki/developer-tools/claude-code.md), and the [AI coding agents hub](../../../upstream-ai-wiki/developer-tools/ai-coding-agents-and-autonomous-engineering-platforms.md); locally, terminal agents need session scope, command-risk controls, denial reasons, approval handoffs, and evidence before they can affect files, dependencies, credentials, external services, or long-lived workspace state.

The [Herdr clipping](../../../raw/processed/Herdr one terminal for the whole herd.md) adds an agent-multiplexer operating pattern. When a terminal surface keeps several coding agents, logs, servers, and long-lived jobs in one session, the workflow should preserve pane identity, workspace path, model or agent label, permission mode, running command, output stream, and attach or detach history as evidence. Multiplexing is useful only when it improves operator visibility and session recovery without hiding which agent or pane owns a command, approval, or verification result.

This page owns terminal-session workflow shape. [Destructive command controls](../governance-and-risk/destructive-command-controls.md) owns destructive shell enforcement, [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md) owns policy and audit enforcement, and [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md) owns human decisions around command execution and consequential state changes.

The [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json) adds sandbox-escape and allowlist-bypass evidence for terminal coding agents. Locally, terminal command policy should evaluate arguments, file writes, repository configuration, host-side readers, hooks, IDE integrations, and downstream command effects instead of classifying commands only by executable name.

The [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) adds terminal-agent manager evidence. Terminal workflows should preserve whether the work ran in a local CLI, server-mode remote control surface, scheduled worktree, tmux-style manager, or IDE-integrated host because each surface changes reconnect evidence, command visibility, and approval timing.

The August 14 raw sources add cloud-build, prior-work-history, queued-command, and hosted-status evidence. The [leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json) records prebuilt environment snapshots, fallback to the last successful build, build logs, commit SHAs, and prior-work reconstruction across apps or websites. The [topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json) records queued shell commands and provider status incidents. Locally, terminal-agent workflows should preserve build provenance, history-derived context, queue state, and service-health checks before unattended work proceeds.

The [August 21 leaf update watch source](../../../raw/processed/2026-08-21/ai-dev-wiki-leaf-update-watch-2026-08-21T210236-0400.json) adds convergence between terminal, cloud, and repo-hosted agent workflows:

- Event wakes, durable goals, and steering semantics should be recorded as session evidence.
- Repo-scoped agents, PR-aware execution, and source-host integrations should preserve their own review context.
- Reviewers should be able to see whether work happened in a terminal, a managed cloud agent, or a mirrored code-hosting surface.

The August 27 raw sources add prototype-first and runtime-control signals. The [leaf update watch source](../../../raw/processed/2026-08-27/ai-dev-wiki-leaf-update-watch-2026-08-27T210207-0400.json) records cloud-agent sessions that can start before a connected third-party repository exists, create a repository in the background, expose browser previews, and publish through a connected deployment account. The [topic news collector source](../../../raw/processed/2026-08-28/ai-dev-wiki-topic-news-collector-2026-08-28T003339Z.json) records coding-agent runtime control changes. Locally, terminal and cloud-agent workflows should distinguish prototype-first sessions from repository-bound implementation sessions and preserve when SCM ownership, preview evidence, publishing authority, and CLI or runtime settings became binding.

## Practice Boundaries

- Record the terminal session, workspace, repository, branch, environment, and operator context before command-capable work begins.
- Keep command previews, denial reasons, target paths, tool arguments, and policy decisions visible in the session record.
- Distinguish inspection commands, generated-script execution, dependency changes, destructive file operations, and external-system calls before approval.
- Route destructive shell actions through destructive-command controls instead of relying on terminal-agent prose.
- Preserve verification evidence and final workspace state before claiming a terminal-agent run completed safely.
- Treat IDE-managed skills, imported rules, and terminal helpers as instruction or supply-chain inputs when they can change command behavior.
- For multiplexed terminal sessions, keep each pane's agent identity, repository, command stream, permission mode, and verification evidence distinguishable after reconnects or server replacement.
- Record execution surface and reconnect history when terminal-agent work moves through local CLI, remote control, scheduled worktree, tmux, or IDE-hosted sessions.
- Record prebuilt environment version, last-successful-build fallback, commit SHA, build logs, queued command state, prior-work-history source, and provider-status checks when terminal agents run in hosted or cloud workspaces.
- Record event wake source, durable goal, steering event, repo scope, PR context, and source-host integration when terminal-agent work crosses into managed cloud or code-hosting surfaces.
- Record the transition from prototype-first cloud work to repository-bound implementation, including created repository, source owner, preview URL evidence, deployment account, publishing approval, and runtime-control settings.

## Authoritative Sources

- [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [Herdr clipping](../../../raw/processed/Herdr one terminal for the whole herd.md)
- [destructive command controls](../governance-and-risk/destructive-command-controls.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [upstream shell command safety for coding agents](../../../upstream-ai-wiki/techniques/shell-command-safety-for-coding-agents.md)
- [upstream OpenAI Codex](../../../upstream-ai-wiki/developer-tools/openai-codex.md)
- [upstream Claude Code](../../../upstream-ai-wiki/developer-tools/claude-code.md)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json)
- [August 14 leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json)
- [August 21 leaf update watch source](../../../raw/processed/2026-08-21/ai-dev-wiki-leaf-update-watch-2026-08-21T210236-0400.json)
- [August 27 leaf update watch source](../../../raw/processed/2026-08-27/ai-dev-wiki-leaf-update-watch-2026-08-27T210207-0400.json)
- [August 28 topic news collector source](../../../raw/processed/2026-08-28/ai-dev-wiki-topic-news-collector-2026-08-28T003339Z.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent-workflows](index.md)
- [event-triggered agent workflows](event-triggered-agent-workflows.md)
- [persistent agent workspaces](persistent-agent-workspaces.md)
- [sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md)

## Open Questions

- The upstream AI wiki does not yet have JetBrains, WebStorm, or GoLand entity leaves to link for IDE-managed skill product signals.

## Maintenance Notes

- Maintained on 2026-07-23 with sandbox-escape, allowlist-bypass, repository-configuration, and host-side trust boundary guidance.
- Created on 2026-07-17 from public raw artifacts about terminal coding agents, IDE-managed skills, and destructive-command denial evidence.
- Maintained on 2026-07-22 with agent-multiplexer session evidence, pane identity, and reconnect boundaries.
- Maintained on 2026-07-27 with local CLI, remote-control, scheduled-worktree, tmux, and IDE-hosted execution-surface evidence.
- Maintained on 2026-08-14 with prebuilt environment, build-fallback, commit-SHA, build-log, queued-command, prior-work-history, and hosted-status evidence.
- Maintained on 2026-08-21 with event-wake, durable-goal, steering, repo-scope, PR-context, and source-host integration evidence.
- Maintained on 2026-08-27 with prototype-first cloud-agent sessions, repository creation, preview, publishing, SCM ownership, and runtime-control evidence.
