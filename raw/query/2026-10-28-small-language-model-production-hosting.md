# Query Fragment: Small Language Model Production Hosting

## Query Asked

What software, cloud infrastructure, and vendor would be used to run a small language model in production?

## Answer Summary

Separate model weights, inference runtime, hosting, and application operations. For teams choosing an existing supported model, a hosted API avoids operating inference. For custom or explicitly selected weights, managed endpoints reduce infrastructure work. A self-operated vLLM container on rented GPUs offers runtime control with greater operational responsibility. Recommend managed endpoints as an initial evaluation path, not as a measured best or cheapest solution.

Hugging Face Inference Endpoints provides managed dedicated autoscaling deployments. Modal supports code-defined GPU inference deployments and vLLM. SageMaker AI JumpStart deploys models to hosted inference endpoints. Together offers serverless and dedicated model endpoints. Runpod offers GPU infrastructure on which vLLM can run. vLLM exposes OpenAI-compatible HTTP APIs; compatibility does not establish identical model behavior.

Capacity planning must include weights, runtime overhead, attention cache, context length, and concurrent requests. Approximate dense-model weight storage is parameter count multiplied by bytes per parameter; this is not a total GPU-memory estimate. Benchmark task quality and tail latency under representative load before committing capacity. Scale-to-zero trades idle cost for cold-start delay. Continuously warm replicas incur ongoing capacity costs. A single replica is not high availability.

## Wiki Pages Consulted

- docs/wiki/application-patterns/local-model-runtime-harness.md
- docs/wiki/governance-and-risk/prototype-to-cloud-promotion-gates.md
- docs/wiki/federation.md
- docs/wiki/topic-index.md
- upstream-ai-wiki/topic-index.md (searched for inference and hosting coverage)

## Authoritative Sources Consulted

Official documentation, accessed 2026-10-28; mutable pages, publication dates not established:

- https://huggingface.co/docs/huggingface_hub/v1.26.0/en/guides/inference_endpoints — managed endpoint infrastructure.
- https://huggingface.co/docs/inference-endpoints/guides/autoscaling — autoscaling and scale-to-zero.
- https://modal.com/docs/guide/high-performance-llm-inference — GPU inference serving.
- https://docs.vllm.ai/en/stable/serving/online_serving/openai_compatible_server/ — inference HTTP API.
- https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-deploy.html — hosted model endpoint deployment.
- https://support.together.ai/articles/2226355974-dedicated-vs-serverless-models — endpoint choices.
- https://docs.vllm.ai/en/latest/deployment/frameworks/runpod/ — vLLM deployment on rented GPU infrastructure.

## Durable Concepts Detected

Deployment responsibility boundaries; representative inference capacity testing; idle cost versus cold starts; model/runtime compatibility; production availability and rollback.

## Candidate Wiki Destinations

Extend the local-model runtime harness leaf or create a focused production inference deployment practice leaf if useful for AI-assisted development applications. Broad vendor and model catalogs belong upstream.

## Existing Pages To Link

- docs/wiki/application-patterns/local-model-runtime-harness.md
- docs/wiki/governance-and-risk/prototype-to-cloud-promotion-gates.md

## Open Questions

Model, task, fine-tuning needs, traffic, latency objectives, region, data requirements, and budget are unspecified. No hardware benchmark or vendor price comparison was performed. Recommendations are engineering judgment, not verified workload results.

## Privacy And Sensitivity Notes

Public information only; no private workload or data assumed.

## Ingest Rationale

Existing coverage discusses local runtime operations but does not cleanly explain the practical responsibility split between hosted APIs, managed model endpoints, and self-operated GPU inference. Preserve this decision guidance for later synthesis; leave vendor encyclopedia coverage upstream.
