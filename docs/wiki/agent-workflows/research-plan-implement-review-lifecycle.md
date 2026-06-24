# Research Plan Implement Review Lifecycle

## Current Understanding

Research, plan, implement, and review is the recurring lifecycle shape for professional agent work. Research gathers codebase and requirement evidence without changing files, planning makes the implementation path explicit, implementation remains supervised, and review validates the result against repository standards.

The [Hypervelocity Engineering source](../../../raw/processed/Hypervelocity engineer @edandersen.md) describes RPI as a structured agent-based lifecycle, and the [HVE Core source](../../../raw/processed/microsoft-hve-core.md) packages agents, prompts, instructions, and skills around repeatable workflow entry points. This page keeps the local lifecycle lens without turning HVE Core itself into a local ecosystem entity.

The [ADLC source](../../../raw/processed/ADLC Claude Code's New Lifecycle for AI Coding.md) extends the same lifecycle into agentic systems: preparation and hypothesis, scope, architecture, proof of value, implementation, testing, deployment, and continuous monitoring. The local interpretation is that non-deterministic agent work needs explicit hypotheses, responsibility boundaries, proof-of-value gates, ongoing evals, and post-deployment monitoring instead of a one-time pass or fail handoff.

The lifecycle complements the [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md). RPI describes the larger phase structure; the orient-inspect-patch-verify loop describes how each coding pass stays grounded.

## Practice Boundaries

- Keep research evidence-gathering distinct from file modification.
- Require an explicit plan before supervised implementation when scope, risk, or sequencing matters.
- Keep implementation bounded by the approved plan and repository rules.
- Treat review as verification against source evidence, tests, lint, build output, and project standards.
- Define hypotheses, ownership boundaries, and success metrics before building an agentic workflow.
- Use proof-of-value checks and continuous monitoring when behavior depends on prompts, context, tools, and model updates.

## Authoritative Sources

- [Hypervelocity engineer source](../../../raw/processed/Hypervelocity engineer @edandersen.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [ADLC source](../../../raw/processed/ADLC Claude Code's New Lifecycle for AI Coding.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md)
- [durable instructions and skill files](../adoption-and-operating-model/durable-instructions-and-skill-files.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [generated code refactoring](../coding-practices/generated-code-refactoring.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source-backed RPI and HVE workflow-packaging guidance.
