# Stage 4 — AI-Assisted Ops (AI *for* Ops) 🟡

> **Goal:** Use AI as a force multiplier in daily ops work: agentic coding tools, MCP, AI inside CI/CD, incident triage, and documentation automation.

## Why it matters

> *"Operating and scaling our central agentic coding pipeline… with a focus on system throughput and code quality"* — AI Operations Lead
> *"Driving their integration and automated documentation"* — AI Operations Lead

Companies now run *agentic coding pipelines* as production infrastructure. Someone has to operate them — that's this track. But first you must be a power user yourself: you can't govern what you haven't mastered.

## Core topics

1. **Agentic coding tools** — Claude Code, GitHub Copilot, Cursor, Gemini CLI, OpenAI Codex: capabilities, failure modes, when to trust output
2. **Model Context Protocol (MCP)** — the USB-C of AI tooling: servers, clients, tools/resources/prompts; building and running MCP servers for internal systems
3. **AI in CI/CD** — AI code review bots, PR summarization, test generation, automated changelog/docs, implementer/reviewer agent loops
4. **AI for troubleshooting** — log analysis, error explanation, K8s troubleshooting assistants (e.g. k8sgpt, HolmesGPT)
5. **Workflow automation** — n8n / temporal-style flows that mix deterministic steps with LLM steps
6. **Skills, rules & context engineering** — CLAUDE.md / rules files, prompts-as-artifacts, versioning and reviewing them like code
7. **The quality question** — how to measure whether AI assistance *actually* improves throughput and code quality (DORA metrics + AI-committed code ratio)

## Resources

- 📖 [MCP official docs](https://modelcontextprotocol.io/) (free) — read Concepts end-to-end, then build a server
- 🎓 [Claude Code docs & best practices](https://docs.claude.com/en/docs/claude-code/overview) + [Anthropic's agentic coding guide](https://www.anthropic.com/engineering/claude-code-best-practices) (free)
- 📖 [k8sgpt](https://k8sgpt.ai/) — AI-powered Kubernetes diagnostics; read the analyzers source
- 📖 [HolmesGPT](https://github.com/robusta-dev/holmesgpt) — open-source AI agent for alert investigation
- 🎓 [n8n docs & AI workflow templates](https://docs.n8n.io/) (free)
- 📖 [DORA — Impact of AI on software delivery](https://dora.dev/research/ai/) (free) — the measurement lens leadership will ask you about
- 📖 [Awesome DevOps AI](https://github.com/hammadhaqqani/awesome-devops-ai) — now actually explore it: pick 5 tools, trial 2

## Hands-on

1. **Live with an agentic coding tool for two weeks** on real tasks. Keep a log: where it excelled, where it hallucinated, where it was slower than doing it yourself.
2. **Build an MCP server** exposing something operational — e.g. "query Prometheus" or "tail this service's logs" — and use it from your AI tool to debug a real issue.
3. **AI-augment a pipeline:** add an LLM step to your Stage 2 CI pipeline that reviews PR diffs against your team's conventions and posts comments. Then add a *deterministic* gate (lint/tests) that overrides it — feel the "AI proposes, gates dispose" pattern.
4. Deploy k8sgpt or HolmesGPT on your cluster, break a deployment, and compare its diagnosis to your own.
5. Automate one piece of documentation end-to-end (e.g. service catalog entry generated from repo metadata + LLM summarization, refreshed by CI).

## ✅ You're ready for the next stages when

- [ ] You ship real work through an agentic tool and can articulate its failure modes
- [ ] You've built and debugged an MCP server
- [ ] Your CI runs at least one useful AI step behind a deterministic quality gate
- [ ] You can argue *with data* whether AI assistance helped a workflow
