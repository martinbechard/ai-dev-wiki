---
type: "Verification And Eval"
title: "Representative Workflow Calibration"
description: "Model and harness changes need calibration against representative work, not only generic benchmark scores."
tags: ["verification-and-evals"]
---

# Representative Workflow Calibration

## Current Understanding

Model and harness changes need calibration against representative work, not only generic benchmark scores. A workflow can depend on code review, tool calls, long-context behavior, retrieval, latency, or local runtime choices, so the calibration set should include those task shapes.

The Dwarf Star source is useful local-harness evidence because it describes calibration prompts that include code reviews, math problems, agent tool calls, and long documents. It also describes comparing local model token probabilities against a reference service to measure drift after quantization. The local practice is to evaluate the behaviors the workflow actually needs before relying on a model, quantization setting, or local inference path.

Runtime telemetry supports calibration because it makes model and tool behavior inspectable. Useful signals include prompt size, prefill behavior, time to first token, decode speed, cache behavior, memory pressure, tool-call validity, and source attribution. Application harness ownership remains in [application harness patterns](../application-patterns/application-harness-patterns.md); this page owns the eval and calibration lens.

The [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json) adds human-review behavior and trace-linked eval signals. Calibration sets for AI-generated code should include prompt provenance and reviewer behavior when those artifacts change review time or scrutiny, and production-agent calibration should connect quality scores to traces, retrieval evidence, tool calls, cost, and latency.

The [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md) adds a calibration requirement for context optimization layers. Compression, cache alignment, reversible retrieval, memory sharing, and provenance tracking should be tested against the same representative workflow prompts as the unoptimized baseline so token savings do not mask accuracy, latency, drift, or governance regressions.

The [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json) adds a model-refresh trigger. New coding, terminal, browser, or agentic-performance claims should refresh the representative local suite before autonomy, default model routing, or cost-performance assumptions change. Public model benchmarks stay upstream; locally, the question is whether the model improves the actual brownfield debugging, review, repair, and verification tasks that this workflow needs.

The [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json) adds two benchmark-methodology examples. Real codebase tasks with reviewed solutions and language-specific end-to-end tasks are stronger calibration signals than generic leaderboards, but they still need local mapping to architecture, APIs, standards, tooling, and verification checks. Benchmark scores should therefore trigger local workflow calibration, not replace it.

## Practice Boundaries

- Build calibration sets from representative workflow prompts, not only generic public benchmarks.
- Include code review, tool calling, long-context, retrieval, and domain-specific cases when the workflow depends on them.
- Compare local model or quantization behavior against a trusted reference when drift matters.
- Track runtime and tool-call telemetry alongside quality results.
- Recalibrate after model, prompt, retrieval, tool schema, quantization, or harness changes.
- Keep broad model-score catalogs upstream unless the score changes a local workflow decision.
- Include prompt provenance, review behavior, trace evidence, retrieval evidence, tool calls, cost, and latency when those signals are part of the target workflow.
- Compare optimized and unoptimized context paths on the same representative workflows when a compression layer changes model input.
- Rerun local representative tasks before changing autonomy, model-routing, or cost-performance defaults after a model refresh.
- Use public or vendor benchmarks as prompts to refresh local calibration, especially when their tasks differ from the repository's language, architecture, or verification surface.
- Include price, latency, reviewed-solution quality, and local fit when comparing coding-agent benchmark results.

## Authoritative Sources

- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)
- [June 26 leaf update watch source](../../../raw/processed/2026-06-26/ai-dev-wiki-leaf-update-watch-2026-06-26T210418-0400.json)
- [Headroom context optimization source](../../../raw/processed/Headroom A Context Optimization Layer for LLM Applications - Tejas Chopra, Netflix, Inc..md)
- [July 1 topic news collector source](../../../raw/processed/2026-07-01/ai-dev-wiki-topic-news-collector-2026-07-01T123923-0400.json)
- [July 11 leaf update watch source](../../../raw/processed/2026-07-11/ai-dev-wiki-leaf-update-watch-2026-07-11T210242-0400.json)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [verification-and-evals](index.md)
- [code review evals and rubrics](code-review-evals-and-rubrics.md)
- [tool call and MCP governance](../retrieval-and-tools/tool-call-and-mcp-governance.md)

## Open Questions

- No open wiki questions are recorded for this topic.

## Maintenance Notes

- Created on 2026-06-23 to hold representative workflow calibration and local-model drift-check practice.
- Maintained on 2026-06-26 with prompt-provenance, human-review behavior, trace-linked quality, retrieval, tool-call, cost, and latency calibration signals.
- Maintained on 2026-06-30 with optimized-versus-baseline context calibration for compression, cache alignment, retrieval, memory, and provenance layers.
- Maintained on 2026-07-01 with model-refresh calibration triggers for coding, terminal, browser, repair, review, and verification tasks.
- Maintained on 2026-07-11 with real-codebase and language-specific benchmark methodology as local calibration inputs.
