---
type: "Governance And Risk"
title: "AI Assisted Security Repair Gates"
description: "AI-assisted security repair needs stricter gates than ordinary feature work because the output can affect vulnerability disclosure, maintainer trust, CI behavior, and downstream..."
tags: ["governance-and-risk"]
---

# AI Assisted Security Repair Gates

## Current Understanding

AI-assisted security repair needs stricter gates than ordinary feature work because the output can affect vulnerability disclosure, maintainer trust, CI behavior, and downstream users. The local pattern is to treat the agent as a drafter and investigator while humans or trusted security reviewers own vulnerability validation, scope, disclosure decisions, and final acceptance.

The [Patch the Planet source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json) describes AI-assisted security research paired with expert review, maintainer consultation, patch development, tests, CI improvements, disclosure coordination, and reusable workflows. Broad OpenAI, Daybreak, Trail of Bits, and program coverage belongs upstream; this page keeps the local repair workflow gates.

Security repair work should not stop at a plausible patch. The workflow needs a reproduction or evidence package, affected-version scope, explicit non-goals, regression tests, CI impact, reviewer notes, and disclosure handling when the issue is externally relevant.

The [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json) and [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json) add a scan-to-merge lens. Dashboard findings and generated patches are not sufficient handoffs by themselves; the local gate needs severity context, triage rationale, affected scope, regression evidence, rescan evidence when available, and human merge review that checks for new security issues.

The [Deepsec clipping](../../../raw/processed/vercel-labsdeepsec Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents.md) adds security-harness operating detail. Agent-powered vulnerability scanning should be treated as an expensive, high-privilege workflow with short project-specific bootstrap context, resumable batch processing, optional revalidation, finding exports, and sandboxed worker execution for large repositories. The local gate is to review setup context for sensitive data, scope the scan, preserve resumability evidence, and require human triage before exported findings become repair work.

## Practice Boundaries

- Validate the finding before patching or reporting it as a vulnerability.
- Confirm scope with the maintainer, owner, or responsible human before changing security-sensitive behavior.
- Keep exploit details, secrets, customer data, and private vulnerability evidence out of public prompts and raw artifacts unless explicitly approved.
- Pair each security patch with focused tests or reproducible verification evidence.
- Check CI, dependency, configuration, and operational side effects before handoff.
- Coordinate disclosure and communication before sending externally visible reports or patches.
- Treat agent-generated security assurances as untrusted until reviewed against source evidence and tests.
- Carry scan findings through triage, prioritization, fix evidence, rescan evidence, and merge review instead of treating the scanner dashboard as the workflow.
- Require human review of AI-generated security patches for regression coverage and absence of new security issues.
- Keep security-scan bootstrap context short, project-specific, and free of unnecessary sensitive detail.
- Require triage, optional revalidation, export review, and sandbox boundary evidence before agent-generated security findings drive fixes.

## Authoritative Sources

- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [governance controls for agents](governance-controls-for-agents.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json)
- [Deepsec clipping](../../../raw/processed/vercel-labsdeepsec Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md)
- [fix branch and PR packaging](../coding-practices/fix-branch-and-pr-packaging.md)
- [code review evals and rubrics](../verification-and-evals/code-review-evals-and-rubrics.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 from public source guidance on AI-assisted vulnerability validation, maintainer consultation, patching, tests, CI, and disclosure coordination.
- Maintained on 2026-07-04 with scan-to-merge severity, triage, rescan, regression, and human merge-review gates.
- Maintained on 2026-07-06 with agent-powered vulnerability scanning setup, resumability, revalidation, export, and sandbox gates.
