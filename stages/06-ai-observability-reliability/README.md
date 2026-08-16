# Stage 6 — AI Observability & Reliability Engineering 🔴

> **Goal:** Make AI systems trustworthy in production: tracing, evaluation pipelines, drift detection, SLOs/SLIs for AI, alerting, incident response, and root-cause analysis of AI failure modes.

## Why it matters

> *"A model may not crash, but it may silently degrade, become less accurate, respond inconsistently, produce poor outputs, or create business risk in ways that are hard to detect"* — Senior AI Reliability Engineer
> *"Implement comprehensive LLM observability, logging, and alerting systems using tools like Datadog and Langfuse"* — AI Platform Engineer
> *"Design, build, and continuously improve evaluation frameworks, benchmarks, and automated testing pipelines for AI, LLM-powered, and agentic workflows"* — Senior AI Reliability Engineer

This is the defining skill of the **AI Reliability Engineer** — classic SRE thinking extended to systems that fail *silently*.

## Core topics

1. **LLM tracing & logging** — spans for prompts/completions/tool-calls; OpenTelemetry GenAI semantic conventions; PII-aware logging
2. **Observability platforms** — Langfuse (open source, self-hostable — learn it deeply), plus the landscape: Datadog LLM Observability, Arize Phoenix, W&B Weave, Helicone
3. **Evaluation in production** — offline evals (golden datasets, CI regression gates) vs online evals (LLM-as-judge on live traffic samples, user feedback signals)
4. **Metrics for AI systems** — quality scores, hallucination/groundedness, retrieval quality (precision/recall of chunks), latency (TTFT, tokens/sec), cost per request, refusal rates
5. **Drift detection** — input drift (user behavior changes), model drift (provider silently updates), embedding-space monitoring
6. **SLOs/SLIs for AI** — what "reliability" means when correctness is fuzzy: availability + latency + quality-score SLOs; error budgets for quality
7. **AI incident response** — runbooks for bad-output incidents, rollback levers (prompt version, model version, retrieval index), postmortems for silent degradation
8. **Root-cause analysis of AI failures** — the debugging tree: prompt change? model change? retrieval? tool failure? upstream data?

## Resources

- 📖 [Langfuse docs](https://langfuse.com/docs) (free, self-hostable) — your primary training ground; do the full tracing + evals + prompt-management loop
- 📖 [OpenTelemetry GenAI semantic conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/) (free) — the emerging standard; knowing it is a differentiator
- 📖 [Arize Phoenix docs](https://arize.com/docs/phoenix) (free) — strong on evals & retrieval analysis
- 🎓 [Hamel Husain — Your AI Product Needs Evals](https://hamel.dev/blog/posts/evals/) (free) — the essay that defined how practitioners think about evals
- 🎓 [DeepLearning.AI — Evaluating and Debugging Generative AI](https://www.deeplearning.ai/short-courses/) (free short courses; also see their LLMOps course)
- 📖 [Google SRE Workbook — SLO chapters](https://sre.google/workbook/implementing-slos/) (free) — then do the thought work of mapping it to quality metrics
- 📖 [Ragas](https://docs.ragas.io/) + [DeepEval](https://docs.confident-ai.com/) (free) — eval frameworks to wire into CI
- 📖 [Evidently AI blog & docs](https://www.evidentlyai.com/) (free) — drift detection, ML monitoring fundamentals

## Hands-on — instrument everything you built in Stage 5

1. **Wire Langfuse into your gateway**: every request through LiteLLM lands as a trace in Langfuse (both self-hosted on your cluster).
2. Build the **eval pipeline**: golden dataset → nightly CI run against the live gateway → scores tracked over time → **CI fails on regression**. This single artifact impresses interviewers more than any certificate.
3. Add **online evaluation**: sample 5% of live traffic, score with LLM-as-judge for groundedness, alert when the 24h rolling score drops.
4. Define and implement **three SLOs** for your RAG service: availability, p95 TTFT, and mean quality score. Build the burn-rate alerts.
5. **Run an AI incident game day**: secretly swap the model (or poison the retrieval index) and practice detecting, diagnosing (which layer?), rolling back, and writing the postmortem.
6. Build the **platform analytics dashboard** from the job posts: AI-committed code ratio (if using Stage 4 pipelines), quality trends, cycle times, per-domain token costs.

## ✅ You're ready for Stages 7–9 when

- [ ] Every LLM call in your stack is traced, costed, and attributable
- [ ] A quality regression in a prompt/model change is caught by CI before humans notice
- [ ] You have SLOs with alerts for a system whose failures are silent
- [ ] You can walk someone through a structured RCA of a bad-output incident
