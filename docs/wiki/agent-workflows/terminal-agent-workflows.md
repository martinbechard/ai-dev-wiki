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

This page owns terminal-session workflow shape. [Destructive command controls](../governance-and-risk/destructive-command-controls.md) owns destructive shell enforcement, [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md) owns policy and audit enforcement, and [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md) owns human decisions around command execution and consequential state changes.

## Practice Boundaries

- Record the terminal session, workspace, repository, branch, environment, and operator context before command-capable work begins.
- Keep command previews, denial reasons, target paths, tool arguments, and policy decisions visible in the session record.
- Distinguish inspection commands, generated-script execution, dependency changes, destructive file operations, and external-system calls before approval.
- Route destructive shell actions through destructive-command controls instead of relying on terminal-agent prose.
- Preserve verification evidence and final workspace state before claiming a terminal-agent run completed safely.
- Treat IDE-managed skills, imported rules, and terminal helpers as instruction or supply-chain inputs when they can change command behavior.

## Authoritative Sources

- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [destructive command controls](../governance-and-risk/destructive-command-controls.md)
- [agent governance infrastructure](../governance-and-risk/agent-governance-infrastructure.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)
- [upstream shell command safety for coding agents](../../../upstream-ai-wiki/techniques/shell-command-safety-for-coding-agents.md)
- [upstream OpenAI Codex](../../../upstream-ai-wiki/developer-tools/openai-codex.md)
- [upstream Claude Code](../../../upstream-ai-wiki/developer-tools/claude-code.md)

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

- Created on 2026-07-17 from public raw artifacts about terminal coding agents, IDE-managed skills, and destructive-command denial evidence.
