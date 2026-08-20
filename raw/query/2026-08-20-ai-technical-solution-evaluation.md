# Query Fragment: AI Technical Solution Evaluation

## Query Asked

What factors should be used for the technical evaluation of a proposed AI solution when choosing a software development partner?

## Answer Summary

Evaluate the proposed solution separately from the partner. Score functional and workflow fit, architecture proportionality, data and grounding quality, representative quality evaluations, security and privacy, reliability and failure handling, performance and scalability, observability and operational readiness, maintainability and portability, and total lifecycle cost. Require reproducible evidence from a representative pilot, record assumptions, and use mandatory gates for unacceptable security, data-rights, evaluation, and exit risks.

## Wiki Pages Consulted

- `docs/wiki/adoption-and-operating-model/workflow-before-model-selection.md`
- `docs/wiki/application-patterns/agent-harness-components.md`
- `docs/wiki/application-patterns/user-visible-progress-and-runtime-telemetry.md`
- `docs/wiki/governance-and-risk/sensitive-data-and-supply-chain-controls.md`
- `docs/wiki/governance-and-risk/prompt-injection-and-untrusted-content.md`
- `docs/wiki/retrieval-and-tools/rag-provenance-ranking-and-chunking.md`
- `docs/wiki/retrieval-and-tools/tool-call-and-mcp-governance.md`
- `docs/wiki/verification-and-evals/verification-loops-and-evals.md`
- `docs/wiki/verification-and-evals/representative-workflow-calibration.md`
- `docs/wiki/verification-and-evals/llm-observability-quality-gates.md`

## Authoritative Sources Consulted

- `raw/processed/gen-ai-app-complete.md`
- `raw/processed/gen-ai-developer-coding.md`

## Durable Concepts Detected

- Partner capability and technical-solution quality need separate evaluation scorecards.
- AI solution evaluation needs both weighted criteria and mandatory pass/fail gates.
- Quality claims should be reproduced on representative data and workflows with baselines, thresholds, traces, and failure evidence.
- Portability includes source, data, prompts, evaluation datasets, configuration, telemetry, and model or provider replacement paths.

## Candidate Wiki Destinations

- A new evaluation leaf under `docs/wiki/verification-and-evals/` for AI technical solution evaluation.
- A cross-link from the candidate AI development partner selection leaf proposed by the related query fragment.

## Existing Pages To Link

- `docs/wiki/verification-and-evals/verification-loops-and-evals.md`
- `docs/wiki/verification-and-evals/representative-workflow-calibration.md`
- `docs/wiki/verification-and-evals/llm-observability-quality-gates.md`
- `docs/wiki/application-patterns/user-visible-progress-and-runtime-telemetry.md`
- `docs/wiki/governance-and-risk/sensitive-data-and-supply-chain-controls.md`
- `docs/wiki/retrieval-and-tools/rag-provenance-ranking-and-chunking.md`

## Open Questions

- What default score weights should apply to customer-facing, employee-facing, and regulated solutions?
- Which risks should always be knockout gates rather than weighted tradeoffs?

## Privacy And Sensitivity Notes

No private, proprietary, sensitive, personal, or company-internal information was captured.

## Ingest Rationale

The repository contains the component evaluation practices but no single reusable technical due-diligence rubric for evaluating a proposed AI solution. A dedicated leaf could provide a common scorecard, evidence requirements, and acceptance gates.
