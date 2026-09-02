---
type: "Retrieval And Tools"
title: "Portable Agent Plugin Packaging And Governance"
description: "Portable agent plugin packaging governs how reusable skills, MCP servers, manifests, and client-specific extensions travel across agent clients."
tags: ["retrieval-and-tools"]
---

# Portable Agent Plugin Packaging And Governance

## Current Understanding

Portable agent plugin packaging governs how reusable skills, MCP servers, manifests, and client-specific extensions travel across agent clients. The [portable agent plugin classification query source](../../../raw/processed/query/2026-08-12-portable-agent-plugin-classification.md) records the local classification rule: Agent Plugins packaging is broader than MCP. MCP servers are one portable component inside the package, while skills, manifests, installation, distribution, permissions, authentication, and client-specific extensions need their own review.

The August 12 raw sources add public adoption evidence without moving broad standard ownership into this wiki. The [topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json) and [leaf update watch source](../../../raw/processed/2026-08-12/ai-dev-wiki-leaf-update-watch-2026-08-12T210257-0400.json) record Agent Plugins support across several client surfaces, with shared packages, plugin manifests, skills, MCP server configuration, managed settings, allowlists, marketplace installation, and client-specific namespaces. Broad Agent Plugins, GitHub Copilot, VS Code, Google, Vercel, OpenAI, Microsoft, AWS, and Anysphere coverage belongs upstream; locally, the practice is to review the package as a capability bundle before it enters a development workflow.

The August 13 raw sources add follow-on adoption and supply-chain evidence. The [topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json) and [leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json) reinforce that portable packages need manifest review, managed availability policy, MCP allowlist evidence, client-specific namespace checks, and repository provenance before bundled skills or MCP servers become team defaults. Broad vendor and product coverage routes upstream; locally, repository-hosted skills and MCP declarations remain governed capability bundles.

The [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json) adds cross-client plugin lifecycle evidence. Portable package governance should account for app-side plugin management, compatible agent-tool availability, side-channel questions from an agent, queued prompts or shell commands, pinned prompt context, and reversible edit recovery. Locally, these are operating controls around package use and supervision; broad product availability stays upstream-owned.

The August 15 raw sources add installable planning-skill and baiting evidence. The [topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json) records a file-backed planning package as a reusable context architecture pattern and an executable skill-installation surface. The [leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json) records fake repository, skill, and MCP-server baiting risks. Locally, portable package review should verify publisher, source archive, bundled commands, memory and plan-file writes, MCP server declarations, and install-time instructions before a package can influence agent behavior.

The [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json) adds provider-native skill packaging evidence. General-availability APIs for skills, files, browser action, and code execution show portable instruction folders becoming part of a broader governed harness surface. Broad product and API coverage remains upstream-owned; locally, skill packages should be reviewed for versioning, lazy-loading rules, included scripts or templates, file-retention assumptions, sandbox execution, and evidence that the selected skill was actually loaded for the task.

The [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json) adds weak but useful ecosystem signals around Agent Plugins 1.0.0 and `.agents` directory naming. Broad specification and ecosystem background remains upstream-owned; locally, the packaging rule is that a portable folder layout is not enough. Reviewers still need provenance, permission classes, runtime governance, dependency and command review, client compatibility, and a reason to prefer agent-general names over vendor-coupled folder names.

The September 1 raw sources add portable plugin and managed-marketplace evidence. The [leaf update watch source](../../../raw/processed/2026-09-01/ai-dev-wiki-leaf-update-watch-2026-09-01T210240-0400.json) records Agent Plugins 1.0 customizations across compatible clients and managed plugin marketplace settings. The [topic news collector source](../../../raw/processed/2026-09-01/ai-dev-wiki-topic-news-collector-2026-09-02T003202Z.json) records authenticated plugin installation from private repositories and reusable review-skill repositories. Locally, portable plugin intake should preserve client compatibility, source marketplace, repository access path, authentication class, bundled skill behavior, and owner approval.

Portable packages should not erase artifact boundaries. [Portable agent skills and runbooks](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md) owns reusable procedure design; [remote MCP skill discovery and governance](remote-mcp-skill-discovery-and-governance.md) owns skills discovered through MCP; [tool call and MCP governance](tool-call-and-mcp-governance.md) owns runtime tool authorization; this page owns the packaging review that binds those components together.

## Practice Boundaries

- Treat the plugin manifest as a governed capability declaration, not only install metadata.
- Review bundled skills, MCP server declarations, client-specific extension folders, marketplace source, managed settings, and allowlist requirements before installation.
- Keep portable components separate from client-specific behavior so teams know which parts should work across clients and which parts depend on one agent surface.
- Require ownership, version, source registry, compatibility target, credential assumptions, permission classes, and rollback path before approving a shared package.
- Do not treat an Agent Plugins package as an MCP-only artifact; route MCP server details through MCP governance and skill procedure details through portable skill governance.
- Preserve client enforcement evidence when package availability, MCP allowlists, or permission-bypass settings differ across IDE, CLI, app, or cloud-agent surfaces.
- Treat repository-hosted skills, plugin packages, and MCP server declarations as supply-chain inputs until provenance, namespace, managed-availability policy, and allowlist evidence are recorded.
- Treat plugin-management UI, side-channel agent questions, queued commands, pinned prompts, and rewind or recovery features as supervision and audit surfaces when portable packages enter recurring workflows.
- Review publisher identity, source archive, bundled commands, memory writes, plan-file writes, MCP declarations, and install instructions before an installable skill or plugin package can change agent behavior.
- Review skill package versioning, lazy-loading triggers, bundled scripts, templates, file identifiers, retention assumptions, and sandbox execution before a reusable skill becomes a shared team capability.
- Preserve run evidence that names which skill package and version loaded, which files it read or wrote, and which execution sandbox handled its scripts.
- Treat shared plugin folder layouts and `.agents` naming as portability aids, not as proof of permission safety, provenance, dependency safety, client compatibility, or runtime governance.
- Record compatible clients, marketplace or repository source, private-repository authentication class, bundled skill behavior, owner approval, and update policy before plugin use.

## Authoritative Sources

- [portable agent plugin classification query source](../../../raw/processed/query/2026-08-12-portable-agent-plugin-classification.md)
- [August 12 topic news collector source](../../../raw/processed/2026-08-12/ai-dev-wiki-topic-news-collector-2026-08-12T203213-0400.json)
- [August 12 leaf update watch source](../../../raw/processed/2026-08-12/ai-dev-wiki-leaf-update-watch-2026-08-12T210257-0400.json)
- [August 13 topic news collector source](../../../raw/processed/2026-08-13/ai-dev-wiki-topic-news-collector-2026-08-13T203147-0400.json)
- [August 13 leaf update watch source](../../../raw/processed/2026-08-13/ai-dev-wiki-leaf-update-watch-2026-08-13T210415-0400.json)
- [August 14 topic news collector source](../../../raw/processed/2026-08-14/ai-dev-wiki-topic-news-collector-2026-08-14T203128-0400.json)
- [August 15 topic news collector source](../../../raw/processed/2026-08-15/ai-dev-wiki-topic-news-collector-2026-08-15T203041-0400.json)
- [August 15 leaf update watch source](../../../raw/processed/2026-08-15/ai-dev-wiki-leaf-update-watch-2026-08-15T210242-0400.json)
- [August 20 topic news collector source](../../../raw/processed/2026-08-20/ai-dev-wiki-topic-news-collector-2026-08-20T203145-0400.json)
- [August 26 leaf update watch source](../../../raw/processed/2026-08-26/ai-dev-wiki-leaf-update-watch-2026-08-26T210330-0400.json)
- [September 1 leaf update watch source](../../../raw/processed/2026-09-01/ai-dev-wiki-leaf-update-watch-2026-09-01T210240-0400.json)
- [September 1 topic news collector source](../../../raw/processed/2026-09-01/ai-dev-wiki-topic-news-collector-2026-09-02T003202Z.json)
- [remote MCP skill discovery and governance](remote-mcp-skill-discovery-and-governance.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [portable agent skills and runbooks](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md)
- [federation.md](../federation.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [remote MCP skill discovery and governance](remote-mcp-skill-discovery-and-governance.md)
- [tool call and MCP governance](tool-call-and-mcp-governance.md)
- [sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md)
- [portable agent skills and runbooks](../adoption-and-operating-model/portable-agent-skills-and-runbooks.md)

## Open Questions

- Should the upstream AI wiki create a broad Agent Plugins specification entity page so this local practice leaf can link to an upstream owner?

## Maintenance Notes

- Maintained on 2026-09-01 with Agent Plugins 1.0 compatibility, managed marketplace, private-repository authentication, reusable review-skill, and update-policy evidence.
- Created on 2026-08-12 from the portable Agent Plugins classification query and August 12 public Agent Plugins adoption evidence.
- Maintained on 2026-08-13 with portable package policy, repository-skill provenance, MCP allowlist, and client-namespace review evidence.
- Maintained on 2026-08-14 with plugin-management, side-channel-question, queued-command, pinned-prompt, and recovery-feature supervision evidence.
- Maintained on 2026-08-15 with installable planning-skill, publisher, source-archive, memory-write, plan-file, MCP-declaration, and repository-baiting package-review evidence.
- Maintained on 2026-08-20 with provider-native skill package versioning, lazy-loading, file-retention, sandbox-execution, and run-evidence guidance.
- Maintained on 2026-08-26 with Agent Plugins layout and `.agents` naming signals treated as portability aids that still require provenance, permission, dependency, compatibility, and runtime-governance review.
