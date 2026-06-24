# Representative Workflow Calibration

## Current Understanding

Model and harness changes need calibration against representative work, not only generic benchmark scores. A workflow can depend on code review, tool calls, long-context behavior, retrieval, latency, or local runtime choices, so the calibration set should include those task shapes.

The Dwarf Star source is useful local-harness evidence because it describes calibration prompts that include code reviews, math problems, agent tool calls, and long documents. It also describes comparing local model token probabilities against a reference service to measure drift after quantization. The local practice is to evaluate the behaviors the workflow actually needs before relying on a model, quantization setting, or local inference path.

Runtime telemetry supports calibration because it makes model and tool behavior inspectable. Useful signals include prompt size, prefill behavior, time to first token, decode speed, cache behavior, memory pressure, tool-call validity, and source attribution. Application harness ownership remains in [application harness patterns](../application-patterns/application-harness-patterns.md); this page owns the eval and calibration lens.

## Practice Boundaries

- Build calibration sets from representative workflow prompts, not only generic public benchmarks.
- Include code review, tool calling, long-context, retrieval, and domain-specific cases when the workflow depends on them.
- Compare local model or quantization behavior against a trusted reference when drift matters.
- Track runtime and tool-call telemetry alongside quality results.
- Recalibrate after model, prompt, retrieval, tool schema, quantization, or harness changes.
- Keep broad model-score catalogs upstream unless the score changes a local workflow decision.

## Authoritative Sources

- [Local model operations source](../../../raw/processed/This 284B Model Shouldn't Fit On Your Laptop. It Does.md)
- [Gen AI application deck](../../../raw/processed/gen-ai-app-complete.md)
- [AI-assisted coding deck](../../../raw/processed/gen-ai-developer-coding.md)
- [application harness patterns](../application-patterns/application-harness-patterns.md)

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
