# Stage 10 — Capstone Projects & Portfolio 🔴

> **Goal:** Consolidate everything into portfolio projects that map 1:1 to what employers hire for — and publish them.

## Why capstones beat certificates

Every job post in [career/job-profiles.md](../../career/job-profiles.md) asks for *experience operating AI systems*. A public repo + write-up + dashboard screenshots is the closest thing to experience you can create yourself. Do 1–2 deeply, not all of them.

---

## 🏗️ Capstone A — "The Internal AI Platform" (Stages 5+6+9)

**The flagship. If you build one thing, build this.**

Build a self-service internal AI platform for a fictional 3-team company:

- LiteLLM gateway on Kubernetes: multi-provider routing, fallbacks, virtual keys
- Per-team budgets, rate limits, and cost dashboards (Prometheus/Grafana)
- Langfuse tracing on every request; nightly eval suite in CI with regression gates
- PII masking middleware (Presidio) + role-based data rails
- Self-service onboarding docs + Terraform/Helm for the whole thing
- **Deliverable:** repo + architecture diagram + 10-min demo video + "day-2 operations" runbook

*Maps to:* AI Platform Engineer, AI Operations Lead roles.

## 🔭 Capstone B — "AI Reliability Command Center" (Stage 6 focus)

Take any LLM app (your Stage 3 RAG bot is fine) and build world-class operations around it:

- Full OTel GenAI tracing, quality/latency/cost SLOs with burn-rate alerts
- Offline + online eval pipelines; drift detection on inputs and scores
- Incident runbooks + two documented game-day postmortems (model swap, index poisoning)
- **Deliverable:** repo + SLO doc + Grafana dashboard tour + postmortems

*Maps to:* Senior AI Reliability Engineer / AI SRE roles.

## 🤖 Capstone C — "The Governed Ops Agent" (Stages 4+8+9)

An incident-investigation agent your on-call team could actually trust:

- MCP servers for metrics/logs/deploy history; workflow-style agent with LangGraph or Agent SDK
- Implementer/reviewer loop, human approval gate, least-privilege creds, full audit log
- Prompt-injection defenses with a documented red-team exercise
- Cost kill-switch and per-run tracing
- **Deliverable:** repo + demo of a real investigation + security write-up

*Maps to:* AI Operations Lead, agentic platform roles.

## ⚡ Capstone D — "Self-Hosted Inference, Properly" (Stage 7 focus)

- vLLM on GPU Kubernetes (spot instances to keep cost sane), KServe or HPA autoscaling
- Benchmark report: throughput/latency curves, quantization comparison, cost per 1M tokens vs API pricing
- Routed behind a gateway as a "cheap tier" with automatic fallback to a cloud API
- **Deliverable:** repo + benchmark write-up + build-vs-buy recommendation memo

*Maps to:* AI Infrastructure / Enterprise AI Platform roles.

---

## 📣 Publishing checklist (do not skip)

- [ ] Public repo per capstone: clean README, architecture diagram, honest "limitations" section
- [ ] One blog post or LinkedIn write-up per capstone — what broke and what you learned lands better than what worked
- [ ] Dashboards & demos as screenshots/video — ops work is visual
- [ ] Add your capstones to your learning log and link them from your CV
- [ ] Bonus: present at a local meetup (CNCF, DevOpsDays, AI tinkerers) — instant network

## 🎓 After the capstones

- Interview prep: [career/interview-prep.md](../../career/interview-prep.md)
- Give back: you now know where this curriculum has gaps — [contribute](../../CONTRIBUTING.md) and climb the contributor ladder
