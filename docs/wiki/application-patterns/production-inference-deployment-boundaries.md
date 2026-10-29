---
type: "Application Pattern"
title: "Production Inference Deployment Boundaries"
description: "Production inference deployment boundaries separate model, runtime, infrastructure, and operational responsibility for AI-assisted development applications."
tags: ["application-patterns"]
---

# Production Inference Deployment Boundaries

## Current Understanding

Production language-model hosting separates model artifacts, inference runtime, infrastructure, and application operations. Broad vendor, model, and runtime catalogs remain upstream-owned. The principal responsibility options are:

- **Hosted API:** transfers most inference operations to a provider.
- **Managed endpoint:** retains more configuration control while the provider operates the serving layer.
- **Self-operated runtime:** retains the most runtime control on controlled GPU infrastructure and the most operational responsibility.

The [small language model production hosting query](../../../raw/processed/query/2026-10-28-small-language-model-production-hosting.md) records the local decision boundary. Select an option by:

- Required data and administrative control, jurisdiction, and acceptable operator access.
- Outage tolerance and recovery objectives.
- Workload quality, latency, concurrency, and cost under representative load.

Managed hosting alone does not prove sovereignty or provider-outage independence. Customer-controlled hosting should:

- Mirror pinned model artifacts, tokenizers, images, and dependencies within the approved boundary.
- Keep prompts, retrieved data, outputs, embeddings, logs, and backups inside that boundary.
- Limit egress and privileged access.
- Test recovery while external services are unavailable.

Runtime selection is workload and hardware dependent. Local heterogeneous clients may use a local runtime, while a separately hosted Linux GPU tier may use a different runtime; a client operating system does not constrain the server operating system. Benchmark on the actual deployment hardware with:

- Identical tasks and context lengths.
- Defined quality targets.
- Representative concurrent load and tail-latency measurement.

An OpenAI-compatible inference API is a transport contract, not proof of identical model behavior.

Capacity planning includes:

- Model weights, runtime overhead, attention cache, context length, and concurrent requests.
- Weight size as one input, not a GPU-memory estimate.
- Cold-start delay when using scale-to-zero.
- Survivor capacity, recovery objectives, and independent failure domains before choosing replica count.

A single replica is not high availability, and multiple replicas in one provider do not establish provider-wide outage tolerance.

Operational telemetry, described in [LLM observability quality gates](../verification-and-evals/llm-observability-quality-gates.md), should distinguish:

- User-visible success, time to first token, token delivery speed, queue delay, and request state.
- Cache pressure or preemption, GPU health, replica readiness, and restart frequency.
- Task quality, with retrieval traced separately from inference.

Use non-sensitive synthetic end-to-end probes and alert on sustained objective violations or lost redundancy. Do not routinely log prompts, documents, outputs, credentials, or high-cardinality sensitive data.

## Practice Boundaries

- Treat provider choice, runtime choice, and application authorization as separate decisions.
- Do not treat local-only runtime settings as a substitute for network egress controls or recovery design.
- Keep tenant authorization and data separation in the application and supporting systems; batching is not an authorization boundary.
- Require measured representative-load evidence before accepting capacity, latency, quality, availability, or cost claims.
- Record the outage domains the design survives and the external dependencies it still requires.

## Authoritative Sources

- [small language model production hosting query](../../../raw/processed/query/2026-10-28-small-language-model-production-hosting.md)
- [local model runtime harness](local-model-runtime-harness.md)
- [prototype to cloud promotion gates](../governance-and-risk/prototype-to-cloud-promotion-gates.md)
- [federation boundary](../federation.md)

## Related Code

- Not yet identified.

## Related Tests

- Not yet identified.

## Related Backlog Items

- Not yet identified.

## Related Wiki Pages

- [local model runtime harness](local-model-runtime-harness.md)
- [prototype to cloud promotion gates](../governance-and-risk/prototype-to-cloud-promotion-gates.md)
- [LLM observability quality gates](../verification-and-evals/llm-observability-quality-gates.md)

## Open Questions

- The required model, task quality target, traffic, latency objective, region, data boundary, recovery objective, and budget are not yet identified.

## Maintenance Notes

- Created on 2026-10-28 from a production-hosting query. Recheck vendor contracts, hardware benchmarks, jurisdictional requirements, and availability commitments before treating a deployment choice as accepted.
