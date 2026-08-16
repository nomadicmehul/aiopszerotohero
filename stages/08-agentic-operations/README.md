# Stage 8 — Agentic Systems Operations 🔴

> **Goal:** Operate and govern agent systems in production: orchestration, state, harnesses, quality gates, human-in-the-loop, and the agentic SDLC.

## Why it matters

> *"Design orchestration, governance, and guardrails for multi-agent AI systems, including agent coordination, permissions, auditability, human oversight, and secure deployment patterns"* — Senior AI Reliability Engineer
> *"Build and optimize automated quality gates, implementer/reviewer loops, and agent harnesses"* — AI Operations Lead
> *"Selecting the appropriate level of AI autonomy for a given problem"* — Senior AI Reliability Engineer

Agents are where AI stops being a chat window and starts *doing things* — which makes them an operations problem. This stage is the frontier of the track and the core of "AI Operations Lead" roles.

## Core topics

1. **Agent architectures** — ReAct loops, tool calling, planning; single agent vs multi-agent; workflow-style (deterministic control flow + LLM steps) vs autonomous-style
2. **Frameworks (operator's literacy)** — LangGraph, OpenAI Agents SDK, CrewAI, Claude Agent SDK; you don't need all of them — you need to see the common shapes: state, tools, checkpoints, handoffs
3. **State & durability** — checkpointing, resumability, idempotent tools, long-running agents surviving restarts (temporal-style durable execution)
4. **Harnesses & quality gates** — sandboxing agent actions, allowlisted tools, implementer/reviewer loops, deterministic gates (tests, linters, SAST) that agents cannot bypass
5. **Permissions & auditability** — least-privilege credentials per agent, action logs, approval workflows, "who did what" when the "who" is an agent
6. **Human-in-the-loop design** — approval points, escalation, autonomy levels ("suggest → draft → act with approval → act")
7. **The agentic SDLC** — running AI coding fleets as a platform: task intake, agent execution, review gates, merge policies, measuring throughput & code quality (ties back to Stage 4 & 6 metrics)
8. **Agent reliability** — failure taxonomies (looping, tool misuse, context poisoning, goal drift), retries & timeouts, cost blowout protection

## Resources

- 📖 [Anthropic — Building Effective Agents](https://www.anthropic.com/research/building-effective-agents) (free) — the canonical "workflows vs agents" essay; read first
- 📖 [LangGraph docs](https://langchain-ai.github.io/langgraph/) (free) — best expression of state/checkpoint concepts
- 📖 [OpenAI — A Practical Guide to Building Agents](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf) (free)
- 🎓 [Hugging Face Agents Course](https://huggingface.co/learn/agents-course) (free) — hands-on, framework-diverse
- 📖 [MCP specification](https://modelcontextprotocol.io/specification) — now read it as a *governance* surface: tool allowlists, auth, audit
- 📖 [Claude Agent SDK docs](https://docs.claude.com/en/api/agent-sdk/overview) (free) — harness design in practice
- 🎥 [AI Engineer conference — agents tracks](https://www.youtube.com/@aiDotEngineer) (free) — production war stories
- 📖 [Temporal docs — durable execution](https://docs.temporal.io/) (free) — the reliability substrate pattern for long-running agents

## Hands-on

1. Build a **workflow-style agent** for an ops task: "investigate this alert" → pull metrics (your MCP server from Stage 4!) → correlate logs → draft an incident summary → **human approves** before it posts. LangGraph or Agent SDK.
2. Add a **reviewer loop**: a second agent (different model) critiques the summary against a rubric; only passing outputs reach the human.
3. Build the **harness**: run the agent in a container with least-privilege creds, log every tool call as a structured audit event into your observability stack, alert on cost per run > threshold.
4. **Break it on purpose**: give it a poisoned log line ("ignore previous instructions…"), watch what happens, then add defenses (tool allowlists, output validation). Write up the exercise.
5. Design (on paper) an **agentic SDLC rollout** for a 5-squad org: autonomy levels per task type, gates, metrics, escalation. This is an interview question for AI Operations Lead roles — practice it.

## ✅ You're ready when

- [ ] You can argue when *not* to use an agent (and win)
- [ ] Your agents run with least privilege, full audit trails, and cost kill-switches
- [ ] You've implemented an implementer/reviewer loop with a deterministic final gate
- [ ] You can design autonomy levels and approval flows for a real org
