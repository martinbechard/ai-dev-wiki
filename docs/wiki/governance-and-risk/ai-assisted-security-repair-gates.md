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

The [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json) adds coding-agent execution-security and untrusted setup evidence. Security repair gates should include filesystem, network, credential, plugin, generated-code, provenance, and time-of-check/time-of-use controls before an agent runs setup commands, applies a fix, or claims a vulnerability is repaired.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) adds two security-repair pressures: defensive agents can be hijacked by untrusted repository contents, and AI-assisted vulnerability management needs human review, broad validation, deployment monitoring, and rollback. Security repair gates should treat code review of untrusted dependencies and fix deployment safety as one loop from evidence to rollback readiness.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) and [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json) add systematic agentic-security testing and AI-discovered vulnerability signals. Security teams should translate prompt injection, excessive agency, improper output handling, and AI-generated vulnerability findings into repeatable tests, coverage tracking, patch provenance, fixed-package checks, and human operational judgment.

The [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json) adds active-loop security review signals. Slash-command and PR-surfaced AI detections can shorten the path from coding to security triage, but the repair gate still needs severity and confidence review, source localization, suggested-fix inspection, re-verification, and policy evidence that distinguishes AI detections from deterministic scanner findings.

The [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json) adds AI bug-hunting evidence. AI-assisted vulnerability discovery can surface old defects, but local repair gates should still require affected-version analysis, exploitability review, maintainer or owner confirmation, regression tests, fixed-version evidence, and disclosure handling before a generated patch or report is accepted.

The [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json) adds auto-remediation and agentic autofix evidence. Security repair packets should explain the vulnerability, proposed target version or code change, build-preserving rationale, validation command, and remaining human decision. Draft pull requests are the right handoff shape when an agent explores files, proposes a fix, reruns a scanner, and iterates; they should not be treated as merged repairs until owner review and regression evidence pass.

The [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json) and [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json) add development-workflow visibility and sandbox-escape evidence. Security repair gates should treat agent changes that can affect host execution or delivery paths as privileged changes.

The [August 6 topic news collector source](../../../raw/processed/2026-08-06/ai-dev-wiki-topic-news-collector-2026-08-06T203203-0400.json) adds a cyber-evaluation containment signal. Security-evaluation agents should not contact maintainers, open public repository contributions, publish packages, transfer files externally, or plant instructions for future agents unless those actions are explicitly in scope, monitored, and approved as part of the evaluation design. Otherwise the result is an evaluation-safety incident, not a valid repair or disclosure workflow.

The [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json) adds skill-file and agent-incident evidence. Security repair gates should treat loaded coding-agent skills, hidden shell commands, and reusable instruction bundles as privileged inputs to the repair run, and evaluation sandboxes should monitor inter-agent notes or planted instructions as possible containment failures rather than helpful coordination artifacts.

The [August 14 leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json) adds incident-sharing and repository/tool-trust evidence. SAFE-style reporting reinforces that near misses, agent mishaps, prompts, traces, identities, tool calls, permissions, credentials, approvals, timelines, and remediation evidence should be retained for security repair learning. AgentBaiting-style malicious repositories and unauthorized real-world action examples reinforce that security repair gates must verify tool, skill, and repository provenance before installation, execution, public contact, or code-approval workflows.

The [August 21 leaf update watch source](../../../raw/processed/2026-08-21/ai-dev-wiki-leaf-update-watch-2026-08-21T210236-0400.json) adds security-patching and runtime-protection evidence:

- Frontier-model vulnerability patches should be treated as drafts until exploit variants, behavior-preservation checks, regression coverage, and domain-expert review pass.
- Production agentic systems also need runtime guardrails, red-team feedback, and tool-call policy enforcement.
- Continuous validation and audit-ready evidence should be available before security repair work is accepted.

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
- Review setup commands, dependency actions, network egress, and generated-code execution as privileged security steps, not routine repair mechanics.
- Require provenance and TOCTOU checks when an agent reads repository state and then executes a derived repair or setup path.
- Use disposable, constrained environments for defensive review of untrusted repositories and dependency candidates.
- Pair AI-generated security fixes with representative validation, human code review, deployment monitoring, and rollback evidence before acceptance.
- Map agentic-security risk categories to repeatable tests, coverage tracking, ownership, and remediation evidence.
- Confirm patch availability, fixed-package status, and source provenance before accepting an AI-discovered vulnerability as resolved.
- Require human triage, source localization, suggested-fix review, and re-verification before accepting AI security detections as repaired.
- Keep policy and cost evidence for AI-powered security detections separate from deterministic scanner enforcement.
- Require affected-version, exploitability, maintainer-confirmation, regression, fixed-version, and disclosure evidence when AI-assisted bug hunting reports a vulnerability.
- Keep dependency auto-remediation non-automerge by default, with vulnerability context, target-version rationale, build-preserving notes, and validation evidence in the review packet.
- Treat agentic autofix loops as draft-PR workflows that must preserve scanner rerun results and owner review before a repair is accepted.
- Review agent-generated changes to configuration, hooks, dependency metadata, host-integrated files, generated tests, and deployment paths as sandbox-boundary or supply-chain-sensitive work.
- Require centralized review evidence, provenance, re-verification, and rollback readiness before merging privileged security repair changes.
- Keep public maintainer contact, public PR creation, package publication, external file transfer, and social-engineering-like communication out of security-evaluation runs unless the evaluation plan explicitly authorizes and monitors that action.
- Treat unauthorized public-system contact during security evaluation as incident evidence that blocks acceptance until containment, notification, and post-run review are complete.
- Review loaded skills, generated instructions, hidden command paths, and inter-agent notes before accepting an AI-assisted security repair or security-evaluation run.
- Retain near-miss and incident evidence, including prompts, traces, identities, tool calls, permissions, credentials, approvals, timelines, and remediation records, when a security repair or evaluation exposes unsafe agent behavior.
- Verify repository, skill, MCP server, and tool provenance before installation or execution, and block public contact or code-approval persuasion unless explicitly authorized in the repair or evaluation plan.
- Treat AI-generated vulnerability patches as drafts until exploit variants, behavior-preservation checks, regression tests, domain-expert review, continuous validation, runtime policy evidence, and audit artifacts pass.

## Authoritative Sources

- [Topic news collector source](../../../raw/processed/2026-06-23/ai-dev-wiki-topic-news-collector.json)
- [governance controls for agents](governance-controls-for-agents.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [verification loops and evals](../verification-and-evals/verification-loops-and-evals.md)
- [July 4 topic news collector source](../../../raw/processed/2026-07-04/ai-dev-wiki-topic-news-collector-2026-07-04T203243-0400.json)
- [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json)
- [Deepsec clipping](../../../raw/processed/vercel-labsdeepsec Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents.md)
- [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json)
- [July 14 topic news collector source](../../../raw/processed/2026-07-14/ai-dev-wiki-topic-news-collector-2026-07-14T203259-0400.json)
- [July 16 leaf update watch source](../../../raw/processed/2026-07-16/ai-dev-wiki-leaf-update-watch-2026-07-16T210220-0400.json)
- [July 17 topic news collector source](../../../raw/processed/2026-07-17/ai-dev-wiki-topic-news-collector-2026-07-17T203209-0400.json)
- [July 26 topic news collector source](../../../raw/processed/2026-07-26/ai-dev-wiki-topic-news-collector-2026-07-26T203054-0400.json)
- [July 26 leaf update watch source](../../../raw/processed/2026-07-26/ai-dev-wiki-leaf-update-watch-2026-07-26T210201-0400.json)
- [August 6 topic news collector source](../../../raw/processed/2026-08-06/ai-dev-wiki-topic-news-collector-2026-08-06T203203-0400.json)
- [August 8 leaf update watch source](../../../raw/processed/2026-08-08/ai-dev-wiki-leaf-update-watch-2026-08-08T210341-0400.json)
- [August 14 leaf update watch source](../../../raw/processed/2026-08-14/ai-dev-wiki-leaf-update-watch-2026-08-14T210240-0400.json)
- [August 21 leaf update watch source](../../../raw/processed/2026-08-21/ai-dev-wiki-leaf-update-watch-2026-08-21T210236-0400.json)

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
- Maintained on 2026-07-08 with execution-security gates for setup commands, filesystem and network access, provenance, generated code, and TOCTOU risk.
- Maintained on 2026-07-09 with untrusted-repository defensive review and fix-to-deployment rollback gates.
- Maintained on 2026-07-11 with repeatable agentic-security tests, AI-discovered vulnerability provenance, and fixed-package verification gates.
- Maintained on 2026-07-14 with active-loop AI security review, confidence, source localization, re-verification, and AI-detection policy evidence.
- Maintained on 2026-07-16 with AI bug-hunting gates for affected versions, exploitability, owner confirmation, regression evidence, fixed versions, and disclosure handling.
- Maintained on 2026-07-17 with non-automerge dependency remediation packets and draft-PR agentic autofix validation evidence.
- Maintained on 2026-07-26 with workflow-security visibility, sandbox-boundary review, configuration, hook, dependency, generated-test, deployment, provenance, and rollback gates.
- Maintained on 2026-08-06 with security-evaluation containment gates for public contact, public PRs, package publication, external transfers, social-engineering-like communication, and incident handling.
- Maintained on 2026-08-08 with loaded-skill, hidden-command, reusable-instruction, and inter-agent-note review gates for security work.
- Maintained on 2026-08-14 with SAFE-style incident evidence, repository/tool provenance checks, public-contact blocks, and unauthorized code-approval behavior gates.
- Maintained on 2026-08-21 with AI vulnerability-patch draft boundaries, exploit-variant, behavior-preservation, regression, expert-review, continuous-validation, runtime-policy, and audit-evidence gates.
