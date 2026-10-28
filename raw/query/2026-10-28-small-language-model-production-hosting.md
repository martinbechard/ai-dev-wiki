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

## Clarification: Sovereignty And Provider Outage Independence

The user clarified that this is live production and the objective is sovereign AI to address confidentiality and vendor outages. This changes the recommendation: generic managed hosting is not sufficient evidence of operational sovereignty.

Official Hugging Face documentation checked 2026-10-28:

- https://huggingface.co/docs/inference-endpoints/security states payloads/tokens are not stored, logs are retained for 30 days, TLS is used, and private network access is supported. Log content and privileged operator access need explicit review; absence of payload retention does not establish absence of operator access.
- https://huggingface.co/docs/inference-endpoints/faq states customers cannot access the hosting instance; PrivateLink exposes an interface in the customer VPC rather than placing the hosting instance in the customer's account. It recommends at least two replicas to mitigate interruptions.
- https://huggingface.co/docs/inference-endpoints/main/guides/access describes an Enterprise endpoint plan with dedicated support, SLAs, and uptime guarantees. The reviewed page does not specify a numerical availability commitment or failure-domain placement guarantee.
- https://huggingface.co/docs/inference-endpoints/about explains that Hugging Face manages container lifecycle and obtains model artifacts from the Hub.

Engineering recommendation: use reviewed open-weight models and an inference runtime such as vLLM on infrastructure under the required administrative and jurisdictional control. Mirror pinned model artifacts, tokenizers, container images, and dependencies internally so serving, restart, and recovery do not require the public Hub. Keep prompts, retrieved data, outputs, logs, embeddings, and backups inside the approved boundary. Limit outbound connections and privileged access. Maintain sufficient serving capacity in independent failure domains and test failover with external services unavailable. Provider-wide outage tolerance requires a second independent provider or customer-operated site; multiple replicas alone do not establish this.

Self-hosting transfers operational responsibility and is not automatically more reliable or confidential. Sovereignty requirements must specify jurisdiction, acceptable cloud/operator access, and whether a customer-controlled hyperscaler account qualifies. Availability targets must specify tolerated downtime, recovery time, and surviving capacity. No vendor contract or architecture was audited in this conversation.

## Mixed Windows And Mac Runtime Selection

The user clarified that target machines include Windows and Macs. vLLM is not universally preferable for this fleet. Engineering recommendation: evaluate Ollama for convenient local deployment, llama.cpp's server for explicit runtime configuration and heterogeneous hardware, and vLLM for a centralized GPU serving tier. This is a workload-dependent recommendation, not a benchmark result. Client operating systems do not constrain a separately hosted inference server's operating system.

Sources checked 2026-10-28:

- https://docs.ollama.com/faq documents per-model parallel requests via OLLAMA_NUM_PARALLEL, memory-dependent concurrency, and local-only mode via OLLAMA_NO_CLOUD=1. Local-only application settings do not replace network egress controls.
- https://github.com/ggml-org/llama.cpp documents Apple Metal, CUDA, CPU inference, quantization, and hybrid CPU/GPU execution.
- https://github.com/ggml-org/llama.cpp/blob/master/tools/server/README.md documents parallel serving slots and continuous batching.
- https://docs.vllm.ai/en/stable/getting_started/installation/gpu/ documents Windows through WSL and Apple acceleration through vLLM-Metal.
- https://github.com/vllm-project/vllm-metal describes the community-maintained Apple Silicon plugin; feature/model parity must be checked rather than assumed.

All three can support concurrent inference with appropriate model/backend configuration. Sovereignty depends on local artifacts, network boundaries, operations, and recovery design rather than the runtime name. Compare identical tasks, context lengths, quality targets, and concurrent load on the actual hardware before selecting.
