# Intelligent Code Review

## Current Understanding

Intelligent code review uses an AI reviewer to compare a change against project rules, source references, risk tiers, contracts, tests, security expectations, and runtime behavior. The reviewer reduces human review load only when it is given the evidence needed to produce actionable findings.

The local practice is source-backed review. Review requests should embed repository instructions, architecture standards, important files, design docs, schema references, known risky modules, and tier-specific checklists. Coherence checks matter because generated changes can make front-end assumptions drift from backend contracts, generated clients, database fields, feature flags, or authorization rules.

## Practice Boundaries

- Attach project rules, source references, and relevant diffs before asking for review.
- Use tier-specific checks for UI, app server, data, infrastructure, and security-sensitive changes.
- Check coherence across front-end assumptions, backend contracts, generated clients, database fields, and feature flags.
- Include security checks for secret exposure, authorization gaps, unsafe tool use, prompt injection surfaces, and risky dependencies.
- Keep review output finding-focused so humans can decide whether to accept, reject, or request a fix.
- Treat review as evidence, not as final acceptance.

## Authoritative Sources

- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [Governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [Generated code refactoring](generated-code-refactoring.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [governance controls for agents](../governance-and-risk/governance-controls-for-agents.md)
- [fix branch and PR packaging](fix-branch-and-pr-packaging.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from source guidance on intelligent self-code-review, source references, tier-specific review, coherence checks, and security checks.
