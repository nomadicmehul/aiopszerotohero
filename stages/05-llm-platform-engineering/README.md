# Stage 5 — LLM Platform Engineering (Ops *for* AI, part 1) 🟡→🔴

> **Goal:** Build and run the central platform layer that gives an organization safe, observable, cost-controlled access to LLMs: gateways, routing, keys, budgets, and self-service.

## Why it matters

> *"Develop and maintain an internal AI provisioning platform to streamline access to various LLMs & MCP Servers (e.g., via LiteLLM)"* — AI Platform Engineer
> *"Enforce model governance, ensuring security, data privacy, rate limiting, and strict LLM API cost management"* — AI Platform Engineer
> *"Self-Service ermöglichen: standardisierte Laufzeitumgebungen und Schnittstellen"* — Enterprise AI Platform Architect

This is the highest-demand, most concrete skill cluster in the track — and almost nobody teaches it.

## Core topics

1. **The LLM gateway pattern** — one internal endpoint, many providers behind it; virtual keys; OpenAI-compatible proxying
2. **LiteLLM (or equivalents)** — deploy the proxy: model list, routing, fallbacks, retries, load balancing across providers/regions
3. **Cost management (AI FinOps)** — budgets per team/key, token accounting, caching (prompt & response), model-tiering ("right-size the model"), showback/chargeback dashboards
4. **Rate limiting & quotas** — RPM/TPM limits, priority tiers, graceful degradation
5. **Key & secret management** — provider key rotation, virtual keys per squad, Vault/cloud secret stores
6. **Multi-tenancy & environment routing** — dev/stage/prod separation, per-domain isolation, data residency routing
7. **Self-service** — templates, golden paths, an internal developer portal entry ("get an AI key in 5 minutes without a ticket")
8. **Model lifecycle at platform level** — evaluating a new model version, canarying it behind the gateway, deprecation comms

## Resources

- 📖 [LiteLLM docs](https://docs.litellm.ai/) (free) — the gateway you'll most likely be asked about; read Proxy section fully
- 📖 [Chip Huyen — Building A Generative AI Platform](https://huyenchip.com/2024/07/25/genai-platform.html) (free) — re-read now; it will land differently
- 📖 [Envoy AI Gateway](https://aigateway.envoyproxy.io/) / [Kong AI Gateway](https://docs.konghq.com/gateway/latest/ai-gateway/) — cloud-native alternatives; know the landscape
- 📖 [OpenRouter docs](https://openrouter.ai/docs) — study its routing/fallback semantics as a design reference
- 📖 [FinOps Foundation — FinOps for AI](https://www.finops.org/topic/finops-for-ai/) (free) — the cost-management framing enterprises use
- 📖 [Platform engineering golden paths (CNCF blog)](https://tag-app-delivery.cncf.io/whitepapers/platforms/) — the self-service philosophy
- 🎥 Talks: search "LLM gateway" at [AI Engineer conference talks](https://www.youtube.com/@aiDotEngineer) (free) — practitioners describing exactly these systems

## Hands-on — **build the mini-platform** (this is the track's signature project)

1. Deploy **LiteLLM proxy** on your Stage 2 Kubernetes cluster via Helm/Terraform.
2. Configure **two providers + one local model** (e.g. any two cloud LLM APIs + Ollama/vLLM) behind one OpenAI-compatible endpoint with fallback + retries.
3. Issue **virtual keys** for three imaginary teams with different budgets and rate limits. Prove a team gets 429s at its limit and the platform survives.
4. Add **cost dashboards**: per-team tokens & spend in Grafana (LiteLLM exposes Prometheus metrics).
5. Add **prompt caching** and measure the cost delta on a repeated-workload benchmark.
6. **Canary a model swap:** route 10% of one team's traffic to a different model, compare quality (your Stage 3 golden dataset!) and cost, then promote or roll back.
7. Write the **self-service doc**: how a new team onboards in 5 minutes. Golden path or it didn't happen.

## ✅ You're ready for Stage 6 when

- [ ] Any app in your cluster can reach any model through one endpoint you control
- [ ] You can show per-team spend and enforce a budget without code changes in the apps
- [ ] You can swap or canary a model behind the gateway with zero client changes
- [ ] A stranger could onboard using only your docs
