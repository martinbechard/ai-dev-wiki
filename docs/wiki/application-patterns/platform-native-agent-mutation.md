---
type: "Application Pattern"
title: "Platform-Native Agent Mutation"
description: "Platform-native agent mutation uses a managed platform's ordinary objects and validation paths instead of creating opaque generated code forks."
tags: ["application-patterns"]
---

# Platform-Native Agent Mutation

## Current Understanding

Platform-native agent mutation uses a managed platform's ordinary objects and validation paths instead of creating opaque generated code forks. It is useful for low-code, internal-tool, workflow, and builder surfaces where maintainability depends on the result staying editable through the platform's normal interface.

The [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json) records a ToolJet MCP case study where Codex built through a validation-first sequence:

1. Plan the next phase.
2. Validate the phase.
3. Fix validation errors.
4. Apply the phase.
5. Verify the result.

The key local pattern is that the operations created normal platform pages, components, queries, data, and events, preserving GUI editability after the agent run.

This page owns the platform-native mutation pattern. [Application harness patterns](application-harness-patterns.md) owns the broader harness architecture boundary.

## Practice Boundaries

- Prefer platform-native mutation APIs when post-agent maintenance should happen in the platform's normal UI.
- Validate each phase before mutation and verify the result after mutation.
- Preserve the platform's ordinary objects, events, queries, and data shape instead of bypassing them with a generated parallel codebase.
- Record validation failures and fixes as part of the agent run evidence.
- Route source-controlled builder artifacts through [file-oriented enterprise builder workflows](file-oriented-enterprise-builder-workflows.md) when the platform exports files.

## Authoritative Sources

- [September 15 topic news collector source](../../../raw/processed/2026-09-15/ai-dev-wiki-topic-news-collector-2026-09-15T003123Z.json)
- [application harness patterns](application-harness-patterns.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [application patterns](index.md)
- [application harness patterns](application-harness-patterns.md)
- [file-oriented enterprise builder workflows](file-oriented-enterprise-builder-workflows.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-09-14 from platform-native MCP mutation evidence in the September 15 topic news collector.
