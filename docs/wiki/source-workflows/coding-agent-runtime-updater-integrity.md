---
type: "Source Workflow"
title: "Coding Agent Runtime Updater Integrity"
description: "Coding agent runtime updater integrity keeps automated runtime refreshes reproducible, verifiable, and bounded by human control for security-sensitive patches."
tags: ["source-workflows"]
---

# Coding Agent Runtime Updater Integrity

## Current Understanding

Coding agent runtime updater integrity keeps automated runtime refreshes reproducible, verifiable, and bounded by human control for security-sensitive patches. The [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json) records an updater log that regenerates version-coupled artifacts, verifies a signed manifest, fails closed when expected markers are missing, and leaves a security-relevant byte-patch target manual. Broad runtime and package-manager background stays upstream; locally, this page owns the updater-integrity workflow.

The local rule is to automate repeatable regeneration while making trust checks deterministic. Signed manifests, exact marker checks, generated-artifact diffs, and fail-closed behavior prevent an updater from silently rewriting prompts, wrappers, runtime metadata, or binary patch targets beyond its verified scope.

The [August 16 leaf update watch source](../../../raw/processed/2026-08-16/ai-dev-wiki-leaf-update-watch-2026-08-16T210208-0400.json) extends the updater boundary to agent-facing skills and MCP runtime inputs. Runtime update jobs should not fetch, install, or rewrite skill files, MCP manifests, setup scripts, or wrapper prompts from public repositories unless provenance, tool scope, command behavior, and quarantine checks pass before the regenerated artifact becomes active.

## Practice Boundaries

- Regenerate version-coupled runtime artifacts from a declared source version and preserve the generated diff.
- Verify signed manifests or equivalent provenance before accepting runtime artifacts.
- Assert exact markers before patching generated files or wrappers, and fail closed when markers are absent.
- Keep security-sensitive binary or byte-patch targets under explicit human control unless the patch process has equivalent provenance and rollback evidence.
- Record which runtime artifacts changed, which checks passed, and which manual patch targets remain outside automation.
- Treat public skill files, MCP manifests, setup scripts, and wrapper prompts as runtime inputs that need provenance, command-behavior, and tool-scope review before automated refresh.
- Quarantine generated runtime artifacts when marker checks, manifest signatures, repository provenance, or allowed tool scopes do not match the expected update package.

## Authoritative Sources

- [July 27 topic news collector source](../../../raw/processed/2026-07-27/ai-dev-wiki-topic-news-collector-2026-07-27T203132-0400.json)
- [August 16 leaf update watch source](../../../raw/processed/2026-08-16/ai-dev-wiki-leaf-update-watch-2026-08-16T210208-0400.json)
- [source reconciliation and routing](source-reconciliation-and-routing.md)
- [raw project-wiki monitor](raw-project-wiki-monitor.md)
- [sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md)
- [verification tax and acceptance gates](../verification-and-evals/verification-tax-and-acceptance-gates.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [source reconciliation and routing](source-reconciliation-and-routing.md)
- [sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md)
- [verification tax and acceptance gates](../verification-and-evals/verification-tax-and-acceptance-gates.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-07-27 from July 27 raw-source evidence about signed-manifest runtime updates, exact-marker checks, fail-closed behavior, and manual security-sensitive patches.
- Maintained on 2026-08-16 with public skill, MCP manifest, setup-script, wrapper-prompt, provenance, and quarantine checks for runtime updater inputs.
