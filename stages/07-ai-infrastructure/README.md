# Stage 7 — AI Infrastructure & Model Serving 🔴

> **Goal:** Run models yourself: GPUs, inference servers, Kubernetes scheduling for AI workloads, and the MLOps/LLMOps pipeline landscape.

## Why it matters

> *"Du betreibst containerisierte Trainings-, Inferenz- und MCP-Server-Workloads auf Kubernetes- oder Cloud-nativen Plattformen"* — Enterprise AI Platform Architect
> *"Solid experience with AWS, Bedrock, AgentCore, ML Flow, Databricks"* — Senior AI Reliability Engineer

Not every org self-hosts models — but the ones that do pay a premium for people who can, and even API-only shops want engineers who understand what's behind the endpoint (latency, batching, quantization, GPU economics).

## Core topics

1. **GPU fundamentals for operators** — VRAM math (weights + KV cache), quantization (GGUF, AWQ, FP8), MIG/time-slicing, why GPUs sit idle and what it costs
2. **Local serving** — Ollama for laptops; understand the OpenAI-compatible surface again
3. **Production inference** — **vLLM** (continuous batching, PagedAttention — operator's view), TGI, SGLang; throughput vs latency tuning
4. **Kubernetes for AI workloads** — NVIDIA GPU Operator & device plugin, node pools/taints for GPUs, **Kueue** for job queueing, **KServe** for model serving CRDs, autoscaling on GPU/queue metrics
5. **Cloud managed options** — AWS Bedrock & SageMaker, Azure AI Foundry / OpenAI Service, GCP Vertex AI: when managed beats self-hosted (usually: start managed)
6. **MLOps/LLMOps pipelines** — MLflow (tracking/registry), Databricks basics, workflow orchestration (Airflow/Dagster/Argo Workflows), data & model versioning, fine-tuning ops (LoRA) at a conceptual level
7. **AI FinOps, infra edition** — GPU utilization dashboards, spot strategies, right-sizing, serverless GPU (Modal, RunPod, Cloud Run GPU)

## Resources

- 📖 [vLLM docs](https://docs.vllm.ai/) (free) — deployment, metrics, and the "serving" section
- 📖 [KServe docs](https://kserve.github.io/website/) + [Kueue docs](https://kueue.sigs.k8s.io/docs/) (free)
- 📖 [NVIDIA GPU Operator docs](https://docs.nvidia.com/datacenter/cloud-native/gpu-operator/latest/) (free)
- 🎓 [DataTalksClub MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp) (free) — the best free MLOps course; do it in parallel with this stage
- 📖 [MLflow docs](https://mlflow.org/docs/latest/) (free) — tracking, registry, and its GenAI/LLM features
- 📖 [Hugging Face — Ultra-Scale Playbook](https://huggingface.co/spaces/nanotron/ultrascale-playbook) (free) — training-side infra, conceptual depth
- 📖 [AWS Bedrock docs](https://docs.aws.amazon.com/bedrock/) / [Azure AI Foundry docs](https://learn.microsoft.com/azure/ai-foundry/) / [Vertex AI docs](https://cloud.google.com/vertex-ai/docs) — learn your cloud's managed stack
- 📖 [SemiAnalysis](https://semianalysis.com/) + [Latent Space](https://www.latent.space/) (free tiers) — stay current on inference economics

## Hands-on

1. **VRAM math on paper first:** compute what fits on a 24 GB GPU for a 7B model at FP16 vs 4-bit, with KV cache for 8k context × N concurrent users. Then verify empirically.
2. Serve a small model with **vLLM** (cloud GPU spot instance or local): benchmark throughput vs latency at increasing concurrency with `vllm bench` or k6; plot the curve; find the saturation point.
3. Put it on Kubernetes: GPU node pool, GPU Operator, vLLM behind KServe (or a plain Deployment + HPA on custom metrics). Route it behind your Stage 5 gateway as the "local tier."
4. Set up **Kueue** and run competing fine-tuning jobs (LoRA on a tiny model) with quotas — watch preemption work.
5. Track the fine-tune in **MLflow**; register model versions; wire "promote to serving" as a pipeline.
6. Build a **GPU cost dashboard**: utilization vs spend; write a one-pager: "should this workload be self-hosted or API?" with numbers.

## ✅ You're ready when

- [ ] You can size a GPU for a model + workload on paper, then prove it
- [ ] You can explain continuous batching and why it changes throughput economics
- [ ] Your gateway routes to a model *you* serve on *your* cluster
- [ ] You can defend a build-vs-buy (self-host vs API) decision with data
