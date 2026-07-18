---
type: "Governance And Risk"
title: "Destructive Command Controls"
description: "Destructive command controls treat file deletion, recursive mutation, path-crossing shell operations, and cleanup commands as high-risk agent actions."
tags: ["governance-and-risk"]
---

# Destructive Command Controls

## Current Understanding

Destructive command controls treat file deletion, recursive mutation, path-crossing shell operations, and cleanup commands as high-risk agent actions. The local rule is that a coding agent should not rely on model intent when a command can remove data, overwrite work, alter dependency state, or affect files outside the intended workspace.

The [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json) first routed destructive shell operations into local governance as a higher-risk action class. The [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) adds terminal-agent hardening evidence for broader forced-`rm` detection and clearer denial reasons. Broader shell-aware parsing, normalization, isolation, approval semantics, and audit controls are linked to the upstream-owned [shell command safety for coding agents](../../../upstream-ai-wiki/techniques/shell-command-safety-for-coding-agents.md) technique.

This page owns the downstream destructive-action enforcement rule. [Terminal agent workflows](../agent-workflows/terminal-agent-workflows.md) owns terminal-session workflow shape, [agent governance infrastructure](agent-governance-infrastructure.md) owns policy enforcement and audit, and [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md) owns the human decision boundary.

## Practice Boundaries

- Classify forced removal, recursive delete, overwrite, cleanup, forced checkout, generated-script execution, dependency mutation, and path-crossing shell commands as destructive or high-risk unless policy proves otherwise.
- Preserve the proposed command, detected risk class, denial reason, terminal session, current workspace, and operator-visible decision in the run record.
- Deny or escalate destructive commands when the local harness cannot explain the target scope, intended side effect, or recovery path.
- Route shell-aware parsing, normalization, sandboxing, approval semantics, and command-audit architecture to the upstream shell command safety technique.

## Authoritative Sources

- [July 3 topic news collector source](../../../raw/processed/2026-07-03/ai-dev-wiki-topic-news-collector-2026-07-03T203137-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [upstream shell command safety for coding agents](../../../upstream-ai-wiki/techniques/shell-command-safety-for-coding-agents.md)
- [governance controls for agents](governance-controls-for-agents.md)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [human agent approval boundaries](../adoption-and-operating-model/human-agent-approval-boundaries.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance-and-risk](index.md)
- [terminal agent workflows](../agent-workflows/terminal-agent-workflows.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-17 from public raw artifacts about terminal-agent forced-removal detection and denial reasons, with broader command-safety controls routed to the upstream AI wiki.
