---
type: "Topic"
title: "Research Plan Implement Review Lifecycle"
description: "Research, plan, implement, and review is the recurring lifecycle shape for professional agent work."
tags: ["agent-workflows"]
---

# Research Plan Implement Review Lifecycle

## Current Understanding

Research, plan, implement, and review is the recurring lifecycle shape for professional agent work. Research gathers codebase and requirement evidence without changing files, planning makes the implementation path explicit, implementation remains supervised, and review validates the result against repository standards.

The [Hypervelocity Engineering source](../../../raw/processed/Hypervelocity engineer @edandersen.md) describes RPI as a structured agent-based lifecycle, and the [HVE Core source](../../../raw/processed/microsoft-hve-core.md) packages agents, prompts, instructions, and skills around repeatable workflow entry points. This page keeps the local lifecycle lens without turning HVE Core itself into a local ecosystem entity.

The [ADLC source](../../../raw/processed/ADLC Claude Code's New Lifecycle for AI Coding.md) extends the same lifecycle into agentic systems: preparation and hypothesis, scope, architecture, proof of value, implementation, testing, deployment, and continuous monitoring. The local interpretation is that non-deterministic agent work needs explicit hypotheses, responsibility boundaries, proof-of-value gates, ongoing evals, and post-deployment monitoring instead of a one-time pass or fail handoff.

The lifecycle complements the [orient inspect patch verify loop](orient-inspect-patch-verify-loop.md). RPI describes the larger phase structure; the orient-inspect-patch-verify loop describes how each coding pass stays grounded.

The [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json) adds asynchronous research and execution-boundary evidence. The lifecycle should treat managed deep research as a research-phase artifact that needs citation and data-sensitivity review, and should choose local, cloud, worktree, or repository-native implementation paths before coding starts.

The [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json) adds control-plane phase evidence. Reliable coding-agent workflows should preserve phase evidence rather than run as one continuous open-ended session:

1. Research gathers source, codebase, and requirement evidence.
2. Planning records scope, memory boundaries, and implementation path.
3. Implementation stays inside the approved execution boundary.
4. Verification records tests, checks, and independent grading where needed.
5. Review preserves human gates, unresolved risks, and acceptance evidence.
6. Shipping records release, handoff, or deployment decisions separately from agent completion claims.

The [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json) adds startup operating principles that map cleanly onto this lifecycle: automate tedium, trust but verify, build for rebuilding, and prototype before productionizing. Locally, these principles translate into lifecycle evidence: reusable hooks for repetitive checks, plan records before implementation, rebuildable worktrees or drafts, evals and verification before trust, and dogfood or pilot evidence before a workflow becomes a production dependency.

## Practice Boundaries

- Keep research evidence-gathering distinct from file modification.
- Require an explicit plan before supervised implementation when scope, risk, or sequencing matters.
- Keep implementation bounded by the approved plan and repository rules.
- Treat review as verification against source evidence, tests, lint, build output, and project standards.
- Define hypotheses, ownership boundaries, and success metrics before building an agentic workflow.
- Use proof-of-value checks and continuous monitoring when behavior depends on prompts, context, tools, and model updates.
- Treat asynchronous research reports as lifecycle inputs that need source, citation, and sensitivity review before they become implementation plans.
- Choose the implementation execution boundary before coding starts when local files, credentials, approvals, or reproducible setup affect risk.
- Preserve phase evidence and gate decisions across research, planning, implementation, verification, review, and shipping.
- Use hooks and reusable checks to automate repetitive verification, while keeping human ownership over trust, productionization, and final acceptance.
- Treat rebuildable drafts, worktree isolation, and pilot or dogfood evidence as lifecycle gates before recurring agent workflows are promoted.

## Authoritative Sources

- [Hypervelocity engineer source](../../../raw/processed/Hypervelocity engineer @edandersen.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [ADLC source](../../../raw/processed/ADLC Claude Code's New Lifecycle for AI Coding.md)
- [July 27 leaf update watch source](../../../raw/processed/2026-07-27/ai-dev-wiki-leaf-update-watch-2026-07-27T210149-0400.json)
- [July 30 topic news collector source](../../../raw/processed/2026-07-30/ai-dev-wiki-topic-news-collector-2026-07-30T203228-0400.json)
- [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json)

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
- Maintained on 2026-07-27 with asynchronous research report review and execution-boundary selection guidance.
- Maintained on 2026-07-30 with explicit control-plane phases, memory boundaries, and human gate evidence.
- Maintained on 2026-08-20 with startup operating principles for automated tedium, trust-but-verify gates, rebuildable drafts, and prototype-to-production promotion.
