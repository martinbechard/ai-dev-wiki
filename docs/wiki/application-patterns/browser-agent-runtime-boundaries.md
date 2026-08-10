---
type: "Application Pattern"
title: "Browser Agent Runtime Boundaries"
description: "Browser-agent runtimes let agents operate the web through real browsers, search, fetch, identity, and proxy surfaces."
tags: ["application-patterns"]
---

# Browser Agent Runtime Boundaries

## Current Understanding

Browser-agent runtimes let agents operate the web through real browsers, search, fetch, identity, and proxy surfaces. The [Browserbase use-cases clipping](../../../raw/processed/Browserbase Use Cases Web Scraping & AI Agent Examples.md) frames browser infrastructure as a production surface for search, fetch, authenticated workflows, proxies, session recording, model routing, and headless browser fleets. Broad product and framework background belongs upstream; this page owns the local practice rule that browser access is an agent execution substrate with privileged side effects.

Browser-agent work combines retrieval and action. Search and fetch APIs can provide token-efficient context, while browser control can log in, navigate dynamic pages, submit forms, extract documents, or synchronize records. Local harnesses should classify those paths separately: retrieval-only browser context can be lower risk, but authenticated browser sessions, proxy-backed scraping, captcha handling, account administration, and cross-system data entry require explicit domain allowlists, identity controls, data retention review, and audit evidence.

Stagehand-style natural-language browser automation and generated browser steps are useful only when selectors, observations, and extracted data remain reviewable. If a model can decide what to click or extract, the harness should preserve the allowed domains, identity used, observed page state, extracted fields, side effects, and verification result so a later reviewer can tell whether the browser run followed the approved task.

## Practice Boundaries

- Treat browser sessions as execution environments, not only retrieval tools.
- Separate search, fetch, observe, extract, and act permissions before a browser agent can run.
- Require domain allowlists, account-scope review, proxy policy, data-retention review, and captcha/identity approval before authenticated or evasive browser automation.
- Preserve browser-session recordings, extracted-field schemas, tool-call arguments, model-routing metadata, and verification evidence when browser actions affect business records or external systems.
- Treat fetched pages, scraped content, and browser observations as untrusted evidence until source labels and prompt-injection controls are applied.
- Review natural-language browser actions and generated selectors as tool instructions whose meaning can drift when page structure changes.
- Route broad Browserbase, Stagehand, Playwright, Puppeteer, Selenium, and browser-use background to the upstream AI wiki unless a source changes local runtime, governance, or verification practice.

## Authoritative Sources

- [Browserbase use-cases clipping](../../../raw/processed/Browserbase Use Cases Web Scraping & AI Agent Examples.md)
- [agent harness components](agent-harness-components.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)
- [prompt injection and untrusted content](../governance-and-risk/prompt-injection-and-untrusted-content.md)
- [upstream browser-use page](../../../upstream-ai-wiki/agentic-frameworks/browser-use.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [agent harness components](agent-harness-components.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)
- [prompt injection and untrusted content](../governance-and-risk/prompt-injection-and-untrusted-content.md)
- [user-visible progress and runtime telemetry](user-visible-progress-and-runtime-telemetry.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-08-09 from Browserbase clipping evidence about browser-agent infrastructure, search/fetch APIs, session recording, proxies, identity, and production browser automation.
