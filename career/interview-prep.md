# Interview Prep for AI-Ops Roles

Themes that come up repeatedly in interviews for AI Platform / AI Reliability / AI Operations roles, with practice questions. Community-sourced — add questions you were actually asked via [PR](../CONTRIBUTING.md) (anonymize the company).

## 1. System design (the core round)

Practice designing out loud, whiteboard-style, 30–45 min each:

- **Design an internal LLM gateway** for a 50-team org: routing, keys, budgets, observability, failure handling. (Stage 5 — the most common design question in this track.)
- **Design the evaluation & monitoring stack** for a customer-facing RAG product: offline vs online evals, SLOs, drift, alerting, rollback levers. (Stage 6)
- **Design a safe agentic coding pipeline**: autonomy levels, review loops, quality/security gates, metrics for leadership. (Stage 8)
- **Self-host vs API**: given a workload (X req/day, Y tokens each, latency target Z), argue the infrastructure decision with numbers. (Stage 7)
- **Design platform-level PII protection** so no team can accidentally send customer data to an external model. (Stage 9)

**Rubric interviewers use:** do you ask about scale/constraints first, do you name tradeoffs, do you cover day-2 operations (upgrades, incidents, cost), and do you know where humans stay in the loop.

## 2. Incident & reliability scenarios

- "Users say the AI assistant got dumber this week. Nothing crashed. Walk me through your investigation." *(The classic. Structure: recent changes → prompt/model/index versions → traces → eval scores → provider status → drift.)*
- "An agent with production access did something wrong. What do you wish you had in place, and what do you do in the first hour?"
- "Your LLM bill tripled this month. Go."
- "The provider deprecated your main model with 30 days' notice. Plan the migration."

## 3. Conceptual depth checks

- Why do LLM systems need different observability than microservices? (silent failure, non-determinism, quality as a metric)
- Explain continuous batching and why GPU serving economics differ from CPU autoscaling.
- LLM-as-judge: strengths, biases, and how you'd validate the judge itself.
- Prompt injection vs jailbreak — difference, and which one your gateway can/can't stop.
- When is a workflow better than an agent?

## 4. Behavioural / change-management (senior roles)

AI Operations Lead roles are half change management:

- "Engineers resist the AI tooling you rolled out. What do you do?"
- "A non-technical team built a prototype automation that leadership loves and security hates. Path to production?"
- "How do you measure whether AI adoption is actually working?" *(Have DORA + token cost + quality metrics ready.)*

## 5. Hands-on rounds

Expect: debugging a broken K8s deployment, writing a Python script against an LLM API with retries/cost caps, reading a trace and finding the slow/expensive span, or reviewing an AI-generated PR for subtle bugs.

## Preparation strategy

1. Do the capstones — every design question above is a capstone you've built.
2. Rehearse the **"silently degraded" investigation** until it's muscle memory; it appears in some form in nearly every loop.
3. Prepare 3 stories: an incident you handled, a system you made cheaper, a human you unblocked.
4. Read the company's engineering blog for their stack; map it to stages and speak their tool names.
