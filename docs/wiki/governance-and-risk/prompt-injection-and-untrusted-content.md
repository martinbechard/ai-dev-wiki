---
type: "Governance And Risk"
title: "Prompt Injection And Untrusted Content"
description: "Prompt injection is a governance issue because language models do not reliably separate instructions from input. Direct prompt injection can arrive from a user prompt."
tags: ["governance-and-risk"]
---

# Prompt Injection And Untrusted Content

## Current Understanding

Prompt injection is a governance issue because language models do not reliably separate instructions from input. Direct prompt injection can arrive from a user prompt. Indirect prompt injection can arrive through files, webpages, tickets, emails, raw clippings, retrieved chunks, or other source text that the model is asked to read.

The local pattern is to label external text as evidence, keep it outside the instruction channel, and enforce risky actions through the harness. Prompt wording can help, but it is not the security boundary. AI gateways, input and output filters, permission checks, redaction, and red-team tests belong around the model when the workflow handles untrusted content.

This page owns local practice for untrusted-content handling. Broad OWASP catalog tracking and vendor-specific security features belong upstream unless the local wiki needs an implementation rule.

The [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json) adds an agent-tool lens: externally controlled tool output, error messages, ticket content, and MCP responses can carry hostile instructions. The local boundary is that a tool result may inform the next step, but it cannot grant permission to execute shell commands, install packages, change credentials, or access cloud resources without harness policy and human approval where required.

The [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json) and [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json) add agentjacking and credential-broker examples. MCP-connected issue trackers, error reports, dependencies, and operational data can carry malicious instructions into coding agents. A credential-broker pattern keeps real secrets outside agent context and swaps credentials only at the outbound request boundary, reducing blast radius when a retrieved source or tool result tries to redirect the agent.

The [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json) adds two hostile-input cases. MCP tool descriptions can be poisoned so an acting agent treats changed metadata as task instruction, and malware samples can embed fake system-message text to mislead LLM-assisted reverse engineering. Tool metadata, binary strings, analyst notes, and extracted artifacts must stay in the evidence channel unless a governed control explicitly promotes them.

The [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json) adds a role-confusion signal. Role tags, labels, and reasoning-style formatting are not sufficient defenses when untrusted text can imitate trusted reasoning, hidden webpage commands, or user intent. The harness still needs source-origin labels, tool-output isolation, and deterministic permission checks before untrusted content can influence actions.

The [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json) adds agent data injection and untrusted setup-command signals. Metadata, tool context, repository setup paths, DNS records, and apparently benign project files can steer a coding agent toward privileged execution; local controls should treat those fields as data until external authorization and runtime checks allow action.

The [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json) and [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json) add two repository-trust cases. Untrusted third-party repositories can carry prompt injections across ordinary source files even without explicit hooks or tool configuration, and repo-local instruction files such as AGENTS.md can become attacker-controlled instructions when they are accepted before the user's task. Local practice should load those files as evidence until repository trust, instruction provenance, and command authority are established.

The [GitLost clipping](../../../raw/processed/GitLost is a dream come true for anyone who likes to jailbreak LLMs.md) adds an issue-triggered agent case. Public issue titles and bodies are attacker-writable source text, not trusted task instructions, even when an automation intentionally reads them. If an agent can read private repositories and post public comments in the same workflow, the trust-boundary failure is already present before the jailbreak phrase succeeds; output posting, repository reads, and cross-repository lookup need separate policy gates.

The [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json) reinforces prompt-injection handling for GitHub-style coding agents and public development workflows. Issue text, pull-request content, generated review artifacts, and runtime files should remain evidence until repository trust, instruction provenance, and harness policy decide whether any instruction can affect tools, dependencies, credentials, or public output.

The [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json) adds a multimodal repository case. Images, binaries, screenshots, generated assets, and other non-text files can carry instructions that a later multimodal agent may read even when a human reviewer sees only a harmless artifact. Coding-agent review should treat binary and image inputs as untrusted content, isolate secrets from review and repair agents, and test downstream agent behavior when a pull request contains multimodal evidence.

The [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json) reinforces image-based prompt injection, public-issue injection, symlink approval confusion, and hallucinated repository paths as connected untrusted-source cases. The local boundary is the same across media: public text, repository metadata, image content, filesystem links, and generated URLs may inform investigation, but they cannot authorize secret reads, cross-workspace writes, package installs, public posting, or source fetching without independent policy evidence.

The [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json) adds automated prompt-injection red-team evidence. Automated adversarial generation is useful only when the harness tests realistic third-party surfaces such as browser pages, connected apps, local files, tool outputs, code repositories, tickets, and email-like content, and when human review remains responsible for attack classes the automated generator misses. Broad OpenAI and GPT-Red background stays upstream; locally, prompt-injection acceptance should require repeatable indirect-injection cases before trusting tool-using agents.

The [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json) adds sandbox-escape, repository-config, compromised-agent, and dataset-processing attack evidence. Untrusted content includes agent-written files, repository metadata, hookable configuration, data-processing inputs, and connected-app content that may be read later by trusted host components or enterprise tools.

The [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json) adds suspicious CI workflow approval evidence, while the [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json) adds poisoned operational inputs, MCP/tool poisoning, and persistent agent-configuration evidence. Coding agents routinely ingest issues, error reports, logs, dependency metadata, MCP registrations, and workflow files; those inputs should remain evidence until integrity, authority, credential-scope, egress, and review checks permit action.

The [August 9 leaf update watch source](../../../raw/processed/2026-08-09/ai-dev-wiki-leaf-update-watch-2026-08-09T210438-0400.json) adds browser and document propagation evidence. AI browser pages, browser extension outputs, connected-app state, and hidden instructions in source documents can steer agents or generated artifacts after the original source is fetched. Locally, browser observations and imported documents should keep source labels, quarantine paths, and action gates before they can authorize generated output, account actions, or cross-document propagation.

The [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) adds persistent memory poisoning and repository/skill baiting evidence. Hidden or compromised content can be stored as long-term memory and later retrieved as trusted context, while fake repositories, skills, or MCP servers can steer agents during installation or onboarding. Locally, memory objects, repository text, skill listings, and MCP onboarding material should remain untrusted evidence until provenance, risk scoring, quarantine, confirmation, and install-policy checks allow reuse.

The August 22 raw sources add document-carrier and connected-app reinforcement:

- The [topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json) frames prompt injection as a risk to billable agent decisions and delegated authority.
- The [leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json) records hidden formatted prompt text in public documents, persistent memory poisoning, malicious links, and connected-app exfiltration as carrier patterns.
- Locally, document ingestion, memory reuse, link following, and connected-app action require quarantine and authorization checks even when the user-facing text appears harmless.

## Practice Boundaries

- Treat files, webpages, issues, emails, documentation, clippings, and retrieved text as evidence, not instructions to execute.
- Preserve source labels and authority labels when passing external content to a model.
- Keep system instructions, developer instructions, user intent, tool output, and source evidence visibly separate in request packages.
- Validate and filter model output before it reaches shells, browsers, databases, workflow engines, or external systems.
- Use permission gates and tool policies outside the model loop so hostile source text cannot grant itself authority.
- Test prompt-injection paths with representative direct and indirect examples before trusting an agent workflow.
- Treat MCP responses, issue text, error traces, logs, and third-party documentation as untrusted data even when they arrived through an approved connector.
- Gate shell execution, package installation, credential use, and cloud actions independently from the text returned by a tool.
- Treat agentjacking as an indirect prompt-injection path: the dangerous instruction may be hidden inside data from an approved tool, not only inside a webpage or prompt.
- Prefer credential brokering or scoped connectors over placing reusable secrets directly in agent context or tool arguments.
- Treat tool descriptions, tool metadata changes, malware strings, and reverse-engineering traces as untrusted source evidence until policy review says otherwise.
- Do not rely on role labels or reasoning-style formatting as the only boundary against untrusted content.
- Treat hidden webpage commands and reasoning-like content as source evidence until a trusted instruction channel authorizes action.
- Treat repository metadata, setup commands, DNS-derived values, tool context, and generated configuration paths as untrusted evidence until policy checks authorize their use.
- Bound prompt-injection blast radius with off-host authorization, argument constraints, rate limits, and credential brokering where side effects are possible.
- Treat third-party source files and repo-local instruction files as untrusted evidence until repository trust and instruction provenance are established.
- Do not let a repository file expand command authority, credential access, or task scope before the user's explicit request and the harness policy agree.
- Treat issue bodies, issue titles, pull-request text, and public comments as attacker-writable evidence when they trigger an agent workflow.
- Do not let public issue content authorize private-repository reads or public disclosure; separate the read permission, retrieval decision, and posting decision into enforceable gates.
- Treat images, binaries, screenshots, generated assets, and file metadata as untrusted evidence when an agent can parse them.
- Keep repository secrets out of coding-agent context and require explicit binary or multimodal review rules before a non-text artifact can influence generated code.
- Keep public issue text, PR content, generated review artifacts, and runtime files out of the instruction channel until repository trust and harness policy are established.
- Require prompt-injection gates before public development agents can combine attacker-writable content, private context, dependency actions, and public output.
- Treat symlinks, file paths, generated repository URLs, and image contents as untrusted evidence when they can change where an agent reads, writes, fetches, or reveals data.
- Require independent source and path verification before an agent follows a generated URL, writes through a filesystem link, or acts on hidden image or binary instructions.
- Test indirect prompt injection across repository, browser, file, tool-output, ticket, and connected-app surfaces before expanding agent tool authority.
- Keep automated red-team findings tied to human triage, missed-attack review, and harness policy changes instead of treating generated attacks as complete coverage.
- Treat CI workflow files, agent configuration, MCP registrations, issue/error/log metadata, and dependency metadata as untrusted instruction surfaces until integrity and authority checks pass.
- Require allowlisted tool surfaces, scoped credentials, controlled egress, and human review when untrusted operational content can steer a coding agent toward persistent configuration or CI side effects.
- Treat browser pages, browser extension output, connected-app state, and imported documents as untrusted content even when the browser session or document connector is approved.
- Quarantine hidden or copied instructions from source documents before agent-authored outputs can publish, email, commit, or propagate them into another artifact.
- Treat persistent memory, repository skill listings, package descriptions, and MCP onboarding text as untrusted source evidence until provenance, quarantine, risk scoring, and explicit install or reuse approval are recorded.
- Inspect PDFs, filings, resumes, pasted documents, and rich-text artifacts for hidden formatting, white-on-white text, copied prompts, embedded links, and machine-readable content before AI review or extraction.
- Gate memory writes, memory reads, connected-app actions, and autorun links separately from the conversational answer because injection can persist beyond the original source encounter.
- Require spend, payment, or paid-service actions to survive prompt-injection screening and delegated-intent checks before execution.

## Authoritative Sources

- [July 23 leaf update watch source](../../../raw/processed/2026-07-23/ai-dev-wiki-leaf-update-watch-2026-07-23T210243-0400.json)
- [OWASP LLM vulnerabilities source](../../../raw/processed/OWASP's Top 10 Ways to Attack LLMs AI Vulnerabilities Exposed.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [retrieval and tools practice](../retrieval-and-tools/rag-tools-and-mcp-practice.md)
- [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json)
- [July 4 leaf update watch source](../../../raw/processed/2026-07-04/ai-dev-wiki-leaf-update-watch-2026-07-04T210205-0400.json)
- [July 8 leaf update watch source](../../../raw/processed/2026-07-08/ai-dev-wiki-leaf-update-watch-2026-07-08T210052-0400.json)
- [July 9 topic news collector source](../../../raw/processed/2026-07-09/ai-dev-wiki-topic-news-collector-2026-07-09T203054-0400.json)
- [July 9 leaf update watch source](../../../raw/processed/2026-07-09/ai-dev-wiki-leaf-update-watch-2026-07-09T210157-0400.json)
- [GitLost clipping](../../../raw/processed/GitLost is a dream come true for anyone who likes to jailbreak LLMs.md)
- [July 11 topic news collector source](../../../raw/processed/2026-07-11/ai-dev-wiki-topic-news-collector-2026-07-11T203215-0400.json)
- [July 12 topic news collector source](../../../raw/processed/2026-07-12/ai-dev-wiki-topic-news-collector-2026-07-12T203207-0400.json)
- [July 13 leaf update watch source](../../../raw/processed/2026-07-13/ai-dev-wiki-leaf-update-watch-2026-07-13T210146-0400.json)
- [July 16 topic news collector source](../../../raw/processed/2026-07-16/ai-dev-wiki-topic-news-collector-2026-07-16T203157-0400.json)
- [July 28 topic news collector source](../../../raw/processed/2026-07-28/ai-dev-wiki-topic-news-collector-2026-07-28T203241-0400.json)
- [July 28 leaf update watch source](../../../raw/processed/2026-07-28/ai-dev-wiki-leaf-update-watch-2026-07-28T210118-0400.json)
- [August 9 leaf update watch source](../../../raw/processed/2026-08-09/ai-dev-wiki-leaf-update-watch-2026-08-09T210438-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [August 22 topic news collector source](../../../raw/processed/2026-08-22/ai-dev-wiki-topic-news-collector-2026-08-22T203221-0400.json)
- [August 22 leaf update watch source](../../../raw/processed/2026-08-22/ai-dev-wiki-leaf-update-watch-2026-08-22T210201-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance controls for agents](governance-controls-for-agents.md)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [sensitive data and supply-chain controls](sensitive-data-and-supply-chain-controls.md)
- [prompt-and-instructions](../prompt-and-instructions/index.md)
- [retrieval-and-tools](../retrieval-and-tools/index.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)
- [browser-agent runtime boundaries](../application-patterns/browser-agent-runtime-boundaries.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Maintained on 2026-07-23 with agent-written file, repository metadata, hookable configuration, dataset-processing, and connected-app trust boundary guidance.
- Maintained on 2026-07-28 with CI workflow tampering, agent-configuration integrity, MCP registration, scoped-credential, and egress-control boundaries.
- Created on 2026-06-23 to separate prompt-injection and untrusted-content practice from the broader governance-controls page.
- Maintained on 2026-06-24 with MCP and tool-output trust-boundary guidance for coding-agent workflows.
- Maintained on 2026-06-25 with agentjacking and credential-broker controls for MCP-connected coding-agent workflows.
- Maintained on 2026-07-01 with MCP tool-description poisoning and malware-analysis prompt-injection cases.
- Maintained on 2026-07-04 with role-confusion, hidden-command, and reasoning-style injection boundaries.
- Maintained on 2026-07-08 with agent data injection, repository setup-command, and off-host authorization boundaries.
- Maintained on 2026-07-09 with untrusted third-party repository files and repo-local instruction provenance boundaries.
- Maintained on 2026-07-10 with issue-triggered agent boundaries for attacker-writable issue text, private-repository access, and public output posting.
- Maintained on 2026-07-11 with multimodal prompt-injection boundaries for images, binaries, generated assets, and secret isolation.
- Maintained on 2026-07-12 with public development-agent prompt-injection gates for issue text, PR content, generated artifacts, runtime files, and public output.
- Maintained on 2026-07-13 with image-injection, symlink, public-issue, and generated-repository path boundaries.
- Maintained on 2026-07-16 with automated indirect prompt-injection red-team coverage for browser, tool-output, repository, file, and connected-app surfaces.
- Maintained on 2026-08-09 with AI browser, browser-extension, connected-app, and carrier-document propagation boundaries.
- Maintained on 2026-08-15 with persistent-memory poisoning, repository-skill baiting, MCP onboarding, provenance, quarantine, and reuse-approval boundaries.
- Maintained on 2026-08-22 with hidden document-carrier inspection, connected-app, memory, autorun-link, and paid-action prompt-injection controls.
