---
type: "Adoption And Operating Model"
title: "Tier Specific Assistant Conventions"
description: "Tier-specific assistant conventions specialize agent behavior for different work areas when those areas need distinct context, tools, verification, or approval."
tags: ["adoption-and-operating-model"]
---

# Tier Specific Assistant Conventions

## Current Understanding

Tier-specific assistant conventions specialize agent behavior for different work areas when those areas need distinct context, tools, verification, or approval. The stable rule is to specialize by work boundary and risk, not by preference for one assistant personality.

The current sources support specialized agents, model-specific instructions, tool descriptions, output constraints, and eval thresholds. They do not yet define a local taxonomy for frontend, backend, data, security, documentation, or other repository tiers. The exact repository tier taxonomy is Not yet identified.

Tier conventions should remain connected to [durable instructions and skill files](durable-instructions-and-skill-files.md) so agents can load the right procedure without copying every tier rule into each prompt.

The [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json) adds a staged-responsibility lens. Tier conventions can distinguish beginner-safe prompting, source-backed retrieval, MCP/tool access, RAG design, autonomous agent execution, benchmark work, and guardrail work when those stages need different permissions, review, and evidence. The exact repository tier taxonomy remains Not yet identified.

The August 18 raw sources add enterprise-managed convention signals. The [leaf update watch source](../../../raw/processed/2026-08-18/ai-dev-wiki-leaf-update-watch-2026-08-18T210146-0400.json) records managed plugin settings, MCP allowlists, telemetry routing, permission modes, third-party agent connectivity, adoption visibility, and AI access controls. Locally, tier conventions should specify which assistant surfaces are allowed for each work boundary, which plugins or MCP servers are permitted, which telemetry is required, and whether approval-bypass or autopilot behavior is disabled for that tier. Broad product surfaces remain upstream-owned.

## Practice Boundaries

- Create a tier convention only when the work area has different sources, tools, approvals, or verification checks.
- Keep tier guidance in durable instructions or skill files when it applies across tasks.
- Test model-specific or harness-specific behavior through the workflow checks instead of assuming one instruction works everywhere.
- Avoid creating parallel tier rules until the local taxonomy is identified.
- Separate assistant conventions by responsibility stage when prompting, retrieval, MCP access, RAG work, autonomous execution, benchmark design, or guardrail changes have different approval needs.
- Keep tiered autonomy increases tied to verification evidence and human review rather than tool availability alone.
- Include allowed assistant surfaces, plugin/MCP allowlists, telemetry routing, and approval-bypass policy in tier conventions when those controls differ by work boundary.
- Use adoption visibility and access-control evidence to decide when a tier can move from advisory assistance to delegated execution.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [durable instructions and skill files](durable-instructions-and-skill-files.md)
- [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json)
- [August 18 leaf update watch source](../../../raw/processed/2026-08-18/ai-dev-wiki-leaf-update-watch-2026-08-18T210146-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [adoption operating agreements](adoption-operating-agreements.md)
- [durable instructions and skill files](durable-instructions-and-skill-files.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [context router and knowledge layers](../context-architecture/context-router-and-knowledge-layers.md)

## Open Questions

- Which local work tiers need distinct assistant conventions is Not yet identified.

## Maintenance Notes

- Created on 2026-06-23 to separate tier-specific assistant behavior from the broader operating-agreement map while preserving the missing local taxonomy.
- Maintained on 2026-07-09 with staged responsibility conventions for prompting, retrieval, MCP, RAG, agents, benchmarks, and guardrails.
- Maintained on 2026-08-18 with managed plugin, MCP allowlist, telemetry, permission-mode, approval-bypass, and access-control convention signals.
