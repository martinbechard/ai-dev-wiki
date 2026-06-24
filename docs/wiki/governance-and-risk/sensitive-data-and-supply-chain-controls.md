# Sensitive Data And Supply-Chain Controls

## Current Understanding

Sensitive data and supply-chain controls protect prompts, raw artifacts, tools, dependencies, models, and third-party source material. The local rule is to keep secrets, credentials, PII, company-internal content, proprietary source, and license-sensitive material out of prompts and public raw artifacts unless the human explicitly approves that use.

Package installs and third-party artifacts deserve explicit review because they can introduce vulnerable, malicious, unnecessary, or license-incompatible dependencies. The same supply-chain lens applies to model artifacts, training data, retrieved source collections, MCP servers, browser extensions, workflow plugins, and copied prompt or skill libraries. HVE Core is useful as a source example because it exposes license, third-party notice, security, governance, and responsible-AI signals alongside reusable agent artifacts.

This page owns the local acceptance and routing rules. Broad provider security announcements, model catalogs, package ecosystem watchlists, and product-specific vulnerability tracking belong upstream unless a local approval rule depends on them.

## Practice Boundaries

- Keep secrets, credentials, PII, and company-internal material outside prompts, raw artifacts, screenshots, logs, and public source collectors unless explicitly approved.
- Review package installs for necessity, provenance, maintenance health, security posture, and license fit before accepting them.
- Vet model artifacts, retrieved data, source collections, MCP servers, workflow plugins, and copied prompt libraries before allowing them into the local workflow.
- Preserve license and third-party notice signals when source artifacts are used to shape local instructions, prompts, skills, or governance pages.
- Use access controls on model endpoints, source data, tool servers, and stored artifacts when sensitive information may be present.
- Record unresolved source or license uncertainty as an open question instead of converting it into an implied approval.

## Authoritative Sources

- [OWASP LLM vulnerabilities source](../../../raw/processed/OWASP's Top 10 Ways to Attack LLMs AI Vulnerabilities Exposed.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [HVE Core source](../../../raw/processed/microsoft-hve-core.md)
- [request packages and file boundaries](../prompt-and-instructions/request-packages-and-file-boundaries.md)
- [source-workflows](../source-workflows/index.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [governance controls for agents](governance-controls-for-agents.md)
- [prompt injection and untrusted content](prompt-injection-and-untrusted-content.md)
- [agent governance infrastructure](agent-governance-infrastructure.md)
- [source-workflows](../source-workflows/index.md)
- [retrieval-and-tools](../retrieval-and-tools/index.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to separate sensitive-data, package-install, dependency, model-artifact, source, and licensing controls from the broader governance-controls page.
