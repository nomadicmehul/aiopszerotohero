# Stage 9 — Security, Governance & Compliance 🔴

> **Goal:** Secure AI systems and make them auditable: OWASP LLM Top 10, guardrails, PII protection, data rails, and the regulatory landscape (EU AI Act, NIST AI RMF, ISO 42001).

## Why it matters

> *"Implementing and maintaining the platform-level data rails — automated PII masking, role-based keys, and secure environment routing — enforced automatically by the platform rather than manually"* — AI Operations Lead
> *"Integrating automated compliance scans (SAST/SCA) directly into the pipeline, providing the technical groundwork for annual audits"* — AI Operations Lead
> *"Ensuring security, data privacy, rate limiting"* — AI Platform Engineer

Governance is where senior AI-ops roles earn their salary: the goal is *automated* enforcement — "the platform governs itself" — not policy PDFs.

## Core topics

1. **The AI threat model** — prompt injection (direct & indirect), jailbreaks, data exfiltration via tools, supply-chain risks in models/datasets, insecure output handling
2. **OWASP GenAI** — [LLM Top 10](https://genai.owasp.org/llm-top-10/) + the agentic security extensions; map each risk to a control in *your* stack
3. **Guardrails engineering** — input/output filtering, PII detection & masking (e.g. Presidio), content moderation APIs, schema validation on outputs; guardrails as *platform middleware* (in the gateway!), not per-app code
4. **Data governance for AI** — role-based access to data via the AI layer, tenant isolation, data residency routing, retention rules for prompts/completions, "can this model see this data?" as an enforced policy
5. **Identity for agents** — machine identities, short-lived credentials, scoped tool permissions, audit trails (ties to Stage 8)
6. **Pipeline security** — SAST/SCA on AI-generated code (Semgrep, Trivy, dependency scanning), model/artifact signing, SBOM ideas extended to models (model cards, provenance)
7. **Regulatory literacy** — **EU AI Act** (risk classes, GPAI obligations, timelines — you're likely in the EU market), **NIST AI RMF**, **ISO/IEC 42001**; what an auditor will actually ask for
8. **The "Measure · Document · Govern" pattern** — metrics feed documentation feeds automated policy; design governance that developers don't have to think about

## Resources

- 📖 [OWASP GenAI Security Project](https://genai.owasp.org/) (free) — Top 10 for LLMs + agentic AI guidance; the industry baseline
- 📖 [Microsoft Presidio](https://microsoft.github.io/presidio/) (free) — the standard open-source PII detection/masking engine; deploy it
- 📖 [Guardrails AI docs](https://www.guardrailsai.com/docs) + [NVIDIA NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) (free) — two approaches to output control
- 📖 [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) (free) — read the core + generative AI profile
- 📖 [EU AI Act explorer](https://artificialintelligenceact.eu/) (free) — plain-language navigation of the Act
- 📖 [Simon Willison on prompt injection](https://simonwillison.net/series/prompt-injection/) (free) — the clearest thinking on the unsolved problem
- 🎓 [Semgrep docs](https://semgrep.dev/docs/) + [Trivy docs](https://trivy.dev/) (free) — the SAST/SCA you'll wire into pipelines
- 📖 [MITRE ATLAS](https://atlas.mitre.org/) (free) — adversarial threat landscape for AI systems

## Hands-on — harden everything you've built

1. **Attack your own stack**: run through the OWASP LLM Top 10 against your Stage 5/6 platform. Document what works. (Indirect prompt injection via your RAG documents is the fun one.)
2. Add **PII masking middleware**: Presidio in the gateway path so no raw PII reaches external providers. Prove it with test traffic; log masked-entity counts as a metric.
3. Implement **role-based data rails**: two user roles, one RAG index with restricted documents — enforce at retrieval time, test that prompt tricks can't bypass it.
4. Wire **Semgrep + Trivy into the agentic pipeline** from Stage 8 so AI-generated code cannot merge without passing scans.
5. Write a **model governance one-pager** for your platform: which models are approved, for which data classes, in which regions, with what logging — then *enforce* it in gateway config, not in prose.
6. Do a mock **EU AI Act assessment** of your capstone system: risk class, obligations, evidence you'd show an auditor.

## ✅ You're ready for capstones when

- [ ] You can demo an indirect prompt injection and the control that stops it
- [ ] PII masking, role-based data access, and environment routing are *platform-enforced* in your stack
- [ ] AI-generated code in your pipeline passes through automated security gates
- [ ] You can brief a leadership team on EU AI Act / NIST AI RMF implications in 10 minutes
