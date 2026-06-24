# Verification Tax And Acceptance Gates

## Current Understanding

Agentic delivery shifts bottlenecks from generation to validation. Generated code, agent actions, and candidate answers can arrive quickly, but review, source grounding, runtime inspection, and human acceptance decide whether the result is usable.

The local operating model should budget a verification tax for AI-assisted work. Faster generation without stronger validation creates more untrusted output, not more finished work. Acceptance gates should match the change surface: source reconciliation for wiki claims, build and tests for code, runtime checks for user-visible behavior, and human review for consequential decisions.

The [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md) adds a reusable-procedure boundary: a skill should define the evidence that must exist before an agent can call the work complete. This page owns the delivery-level acceptance practice. The mechanics of eval graders live in [judge grader boundaries](judge-grader-boundaries.md), and the general workflow loop lives in [verification loops and evals](verification-loops-and-evals.md).

## Practice Boundaries

- Decide the acceptance gate before claiming a task is complete.
- Use build, test, lint, runtime checks, source checks, and human review according to the risk of the change.
- Report material verification results in completion notes so trust is attached to evidence.
- Treat blocked verification as a blocker or residual risk, not as a successful result.
- Budget review time when agentic workflows increase output volume.
- Keep human acceptance explicit for consequential changes, external actions, or uncertain evidence.
- Encode recurring proof standards in skills and runbooks so completion checks travel with the procedure.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [Agentic team structures source](../../../raw/processed/A leader’s guide to advanced team structures in an agentic world  AWS Events.md)
- [orient inspect patch verify loop](../agent-workflows/orient-inspect-patch-verify-loop.md)
- [Open Skills source](../../../raw/processed/The Skill vs Prompt Problem Everyone Gets Wrong.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification-and-evals](index.md)
- [generated code refactoring](../coding-practices/generated-code-refactoring.md)
- [portable agent skills and runbooks](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold verification-tax and acceptance-gate practice for agentic delivery.
- Maintained on 2026-06-23 to connect reusable skill contracts to proof standards.
