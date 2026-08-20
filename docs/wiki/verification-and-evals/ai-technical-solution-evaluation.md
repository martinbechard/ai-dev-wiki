---
type: "Verification And Eval"
title: "AI Technical Solution Evaluation"
description: "AI technical solution evaluation scores a proposed AI solution separately from the partner proposing it."
tags: ["verification-and-evals"]
---

# AI Technical Solution Evaluation

## Current Understanding

AI technical solution evaluation scores the proposed solution separately from the partner or vendor. A strong proposal should prove functional fit, architecture proportionality, grounding quality, evaluation discipline, security controls, reliability, observability, maintainability, portability, and lifecycle cost with reproducible evidence.

The [technical-solution evaluation query fragment](../../../raw/processed/query/2026-08-20-ai-technical-solution-evaluation.md) turns existing verification, governance, retrieval, telemetry, and workflow pages into a reusable due-diligence rubric. Its core rule is that claims should be reproduced on representative data and workflows with baselines, thresholds, traces, and failure evidence before the solution is accepted.

Partner capability belongs in [AI development partner selection](../adoption-and-operating-model/ai-development-partner-selection.md). This page owns the technical quality gates for the proposed solution itself.

## Evaluation Criteria

- Functional and workflow fit: the solution supports the real user journey, decision points, exception handling, and measurable outcome.
- Architecture proportionality: the design explains when it uses prompting, retrieval, tools, agents, fine-tuning, deterministic code, human review, and fallback paths.
- Data and grounding quality: source systems, permissions, provenance, freshness, retrieval ranking, citations, and data-rights boundaries are explicit.
- Representative quality evaluation: test cases, eval datasets, baselines, thresholds, traces, and reviewer rubrics reflect actual work rather than generic demos.
- Security and privacy: the design addresses sensitive data, prompt injection, tool authorization, supply-chain risk, audit logs, and incident handling.
- Reliability and failure handling: the proposal defines degradation, retry, escalation, abstention, rollback, and human takeover behavior.
- Performance and scalability: latency, concurrency, context size, tool-call volume, cost, and operational limits are measured against representative load.
- Observability and operations: traces, prompt versions, datasets, model routes, tool calls, incidents, and release decisions are inspectable.
- Maintainability and portability: source, prompts, evaluation datasets, configuration, telemetry, and model/provider replacement paths can survive handoff.
- Lifecycle cost: build, data work, model use, tools, evaluation, review, monitoring, support, and change costs are visible.

## Knockout Gates

Mandatory pass/fail gates should stop a proposal when it cannot show acceptable security, data-rights, evaluation, operability, or exit evidence. Weighted scoring is useful only after these non-negotiable risks are resolved.

## Authoritative Sources

- [Technical-solution evaluation query fragment](../../../raw/processed/query/2026-08-20-ai-technical-solution-evaluation.md)
- [Verification loops and evals](verification-loops-and-evals.md)
- [Representative workflow calibration](representative-workflow-calibration.md)
- [LLM observability quality gates](llm-observability-quality-gates.md)
- [Agent harness components](../application-patterns/agent-harness-components.md)
- [User-visible progress and runtime telemetry](../application-patterns/user-visible-progress-and-runtime-telemetry.md)
- [Sensitive data and supply-chain controls](../governance-and-risk/sensitive-data-and-supply-chain-controls.md)
- [Prompt injection and untrusted content](../governance-and-risk/prompt-injection-and-untrusted-content.md)
- [RAG provenance, ranking, and chunking](../retrieval-and-tools/rag-provenance-ranking-and-chunking.md)
- [Tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [AI development partner selection](../adoption-and-operating-model/ai-development-partner-selection.md)
- [Representative workflow calibration](representative-workflow-calibration.md)
- [LLM observability quality gates](llm-observability-quality-gates.md)
- [RAG provenance, ranking, and chunking](../retrieval-and-tools/rag-provenance-ranking-and-chunking.md)

## Open Questions

- What default score weights should apply to customer-facing, employee-facing, and regulated solutions?
- Which risks should always be knockout gates rather than weighted tradeoffs?

## Maintenance Notes

- Created on 2026-08-20 from the technical-solution evaluation query fragment as a durable due-diligence rubric.
