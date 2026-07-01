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

## Authoritative Sources

- [OWASP LLM vulnerabilities source](../../../raw/processed/OWASP's Top 10 Ways to Attack LLMs AI Vulnerabilities Exposed.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [retrieval and tools practice](../retrieval-and-tools/rag-tools-and-mcp-practice.md)
- [June 24 topic news collector source](../../../raw/processed/2026-06-24/ai-dev-wiki-topic-news-collector-2026-06-24T203219-0400.json)
- [June 25 topic news collector source](../../../raw/processed/2026-06-25/ai-dev-wiki-topic-news-collector-2026-06-25T203154-0400.json)
- [June 25 leaf update watch source](../../../raw/processed/2026-06-25/ai-dev-wiki-leaf-update-watch-2026-06-25T210126-0400.json)
- [July 1 leaf update watch source](../../../raw/processed/2026-07-01/ai-dev-wiki-leaf-update-watch-2026-07-01T123920-0400.json)

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

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to separate prompt-injection and untrusted-content practice from the broader governance-controls page.
- Maintained on 2026-06-24 with MCP and tool-output trust-boundary guidance for coding-agent workflows.
- Maintained on 2026-06-25 with agentjacking and credential-broker controls for MCP-connected coding-agent workflows.
- Maintained on 2026-07-01 with MCP tool-description poisoning and malware-analysis prompt-injection cases.
