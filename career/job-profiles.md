# Real Job Profiles, Decoded

Anonymized excerpts from real 2026 job postings, translated into curriculum stages. Use this to sanity-check what the market wants — and PR new postings as you find them (see [CONTRIBUTING](../CONTRIBUTING.md)).

## Profile 1 — AI Operations Lead (scale-up, internal AI platform)

| They say | They mean | Stage |
|---|---|---|
| "Operate and evolve our central agentic coding pipeline… focus on system throughput and code quality" | Run an AI coding fleet as production infra with metrics | 4, 8 |
| "Self-governing AI system — clear guardrails, automated quality and security gates" | Governance enforced by the platform, not by policy docs | 8, 9 |
| "Automated PII masking, role-based keys, secure environment routing" | Data rails as gateway middleware | 5, 9 |
| "Implementer/reviewer loops and agent harnesses" | Multi-agent QA patterns + sandboxing | 8 |
| "Dashboards to track AI-committed code ratios, bug frequencies, cycle times, domain token costs" | AI platform analytics | 6 |
| "Automated compliance scans (SAST/SCA) directly into the pipeline… annual audits" | Security automation + audit evidence | 9 |
| "Enable non-technical vibe coders to safely move prototypes into production" | Change management + golden paths | 5, 8 |

**Takeaway:** Stages 4→6→8→9 are the spine of this role. It's a *platform + governance* job, not a data-science job.

## Profile 2 — Senior AI Reliability Engineer (healthtech, platform org)

| They say | They mean | Stage |
|---|---|---|
| "Evaluation frameworks, benchmarks, automated testing pipelines for AI and agentic workflows" | Eval engineering in CI | 6 |
| "Observability, drift detection, hallucination risk, retrieval quality" | AI-specific monitoring | 6 |
| "SLOs, SLIs, monitoring, alerting, incident response, runbooks, RCA of AI failure modes" | Classic SRE extended to AI | 2, 6 |
| "Orchestration, governance, guardrails for multi-agent systems… human oversight" | Agent operations | 8 |
| "AWS, Bedrock, AgentCore, MLflow, Databricks, CloudWatch, GitLab" | One cloud's managed AI stack + MLOps tooling | 1, 7 |
| "A model may not crash, but it may silently degrade" | The core mental model of this entire track | 0, 6 |

**Takeaway:** the interview will live in Stage 6. Bring eval pipelines and postmortems, not model architectures.

## Profile 3 — Enterprise AI Platform Architect (IT consultancy, DACH)

| They say | They mean | Stage |
|---|---|---|
| "Scalable platform architectures for ML, LLM and agentic workloads" | Platform design | 5, 7 |
| "IaC for reproducible AI environments across stages" | Terraform/Pulumi discipline | 2 |
| "Containerized training, inference and MCP-server workloads on Kubernetes" | K8s for AI + GPU scheduling | 7 |
| "IAM, secrets management, network and multi-tenancy concepts at platform level" | Cloud security fundamentals applied to AI | 1, 5, 9 |
| "Self-service: standardized runtimes and interfaces for data/ML/GenAI teams" | Golden paths, internal developer platform | 5 |
| "German and English" | DACH enterprise market reality | — |

**Takeaway:** strongest classic-platform flavor. CKA + Terraform + Stage 5/7 depth wins here.

## Profile 4 — AI Platform Engineer (fintech, embedded in Data/AI tribe)

| They say | They mean | Stage |
|---|---|---|
| "Internal AI provisioning platform to streamline access to LLMs & MCP servers (e.g., via LiteLLM)" | The LLM gateway pattern, by name | 5 |
| "LLM observability, logging, alerting using Datadog and Langfuse" | Tracing + dashboards | 6 |
| "Model governance: security, data privacy, rate limiting, strict LLM API cost management" | AI FinOps + policy-as-config | 5, 9 |
| "Support cloud-native architectures and agentic workflow integrations" | K8s + agents literacy | 2, 8 |
| "AWS, Terraform, Python/Go, CI/CD, Docker" | The classic platform base | 1, 2 |

**Takeaway:** Stage 5 is so literal here that the tools are named. The mini-platform capstone *is* this job.

---

## Pattern across all profiles

1. **Nobody asks for model training.** They ask for *operating* AI systems.
2. **The base is always classic platform skills** (K8s, Terraform, CI/CD, one cloud, Python).
3. **The differentiators are Stages 5, 6, 8, 9** — gateway, evals/observability, agent governance, compliance.
4. **Communication is load-bearing:** every post wants someone who can explain AI behaviour and tradeoffs to non-experts.
