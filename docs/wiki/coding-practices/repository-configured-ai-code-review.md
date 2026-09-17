---
type: "Coding Practice"
title: "Repository-Configured AI Code Review"
description: "Repository-configured AI code review treats AI review settings as governed project policy rather than hidden reviewer behavior."
tags: ["coding-practices"]
---

# Repository-Configured AI Code Review

## Current Understanding

Repository-configured AI code review treats AI review settings as governed project policy rather than hidden reviewer behavior. The [September 17 topic news collector source](../../../raw/processed/2026-09-17/ai-dev-wiki-topic-news-collector-2026-09-17T003308Z.json) records CodeRabbit-style configuration as a practice signal. Review inputs include:

- Path-specific instructions and progress reporting.
- Reviewer assignment rules and request-changes behavior.
- Tool configuration and security review sections.
- Agent-facing remediation prompts.

Broad CodeRabbit product background stays upstream-owned; locally, the durable rule is that review configuration must be versioned, inspectable, and tied to human merge authority.

Repository configuration is useful only when it changes review behavior in a traceable way. Review records should preserve which instruction set, path rule, label rule, tool setting, security section, and agent-facing prompt applied to a pull request or pre-PR review. Human-facing summaries and agent-facing remediation prompts should remain distinct because they serve different audiences and risk surfaces.

## Practice Boundaries

- Keep AI-review rules, path scopes, labels, reviewer assignment, security sections, tool settings, and request-changes behavior in repository-owned or team-owned configuration.
- Preserve the configuration version or commit that governed each generated review.
- Distinguish human-facing findings from prompts intended for a follow-on remediation agent.
- Treat configuration changes as review-system changes that need owner approval and regression checks when they affect merge gates.
- Route general AI-review practice through [intelligent code review](intelligent-code-review.md) and review-quality measurement through [code review evals and rubrics](../verification-and-evals/code-review-evals-and-rubrics.md).

## Authoritative Sources

- [September 17 topic news collector source](../../../raw/processed/2026-09-17/ai-dev-wiki-topic-news-collector-2026-09-17T003308Z.json)
- [intelligent code review](intelligent-code-review.md)
- [code review evals and rubrics](../verification-and-evals/code-review-evals-and-rubrics.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [intelligent code review](intelligent-code-review.md)
- [code review evals and rubrics](../verification-and-evals/code-review-evals-and-rubrics.md)
- [pre-PR independent review](pre-pr-independent-review.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-09-16 from raw-source evidence about repository-local AI review configuration and agent-facing review prompts; next check should verify config examples preserve reviewer authority and repository-specific rule provenance.
