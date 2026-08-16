# Stage 3 — AI Fundamentals 🟡

> **Goal:** Understand LLMs well enough to operate them: APIs, prompting, embeddings, RAG, structured outputs, and your first evaluations.

**Experienced DevOps/cloud engineers start here.**

## Why it matters

> *"Familiarity in LLMs, RAG, AI agents, prompt evaluation, and model behaviour"* — Senior AI Reliability Engineer
> *"KI-Tools souverän einsetzen, die Ergebnisse kritisch bewerten"* — Enterprise AI Platform Architect

You can't set SLOs for a system you don't understand. This stage is *working knowledge*, not research: you need to know what a token, a context window, and a temperature are — not how to derive backpropagation.

## Core topics

1. **How LLMs work (operator's view)** — tokens, context windows, sampling/temperature, why outputs are non-deterministic, what "model behaviour" means
2. **LLM APIs** — chat completions, streaming, function/tool calling, structured outputs (JSON mode), system prompts; OpenAI-compatible API as the de-facto standard
3. **Prompt engineering** — few-shot, chain-of-thought, prompt templates, versioning prompts like code
4. **Embeddings & vector search** — similarity, chunking, vector databases (pgvector, Qdrant, etc.)
5. **RAG** — retrieval pipelines, why they fail (retrieval quality!), when to use vs fine-tuning
6. **First evals** — golden datasets, exact-match vs LLM-as-judge, why "it looks good" isn't a test
7. **The cost model** — input/output token pricing, caching, why cost is an ops concern from day one

## Resources

### LLM mechanics
- 🎥 [Andrej Karpathy — Deep Dive into LLMs like ChatGPT](https://www.youtube.com/watch?v=7xTGNNLPyMI) (free) — the best 3.5 hours you'll spend
- 🎥 [3Blue1Brown — Neural networks / Transformers series](https://www.3blue1brown.com/topics/neural-networks) (free) — visual intuition
- 🎓 [Hugging Face LLM Course](https://huggingface.co/learn/llm-course) (free)

### Working with APIs & prompting
- 📖 [OpenAI docs](https://platform.openai.com/docs) + [OpenAI Cookbook](https://cookbook.openai.com/) (free)
- 📖 [Anthropic docs & prompt engineering guide](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview) (free)
- 🎓 [Anthropic Academy courses](https://anthropic.skilljar.com/) (free)
- 🎓 [DeepLearning.AI short courses](https://www.deeplearning.ai/short-courses/) (free) — pick: ChatGPT Prompt Engineering, Building Systems with LLMs, LangChain, RAG

### Embeddings, RAG, evals
- 📖 [Chip Huyen — AI Engineering](https://www.oreilly.com/library/view/ai-engineering/9781098166298/) 💰 — *the* book for this whole track; buy it
- 📖 [Eugene Yan — Patterns for Building LLM-based Systems](https://eugeneyan.com/writing/llm-patterns/) (free)
- 🎓 [DataTalksClub LLM Zoomcamp](https://github.com/DataTalksClub/llm-zoomcamp) (free) — hands-on RAG + evals + monitoring, cohort-based

## Hands-on

1. Build a CLI chatbot against any LLM API with streaming, a system prompt, and conversation memory. Then swap providers by changing only the base URL — feel the OpenAI-compatible standard.
2. Build a **RAG over your own runbooks/docs**: chunk → embed → store in pgvector → retrieve → answer with citations. (This becomes a capstone building block.)
3. Create a 30-question golden dataset for your RAG bot. Score it with exact-match + LLM-as-judge. Change the chunk size and *measure* the difference — congratulations, you've done your first eval.
4. Add a cost counter: log tokens and € per request. Plot a week of usage.

## ✅ You're ready for Stage 4/5 when

- [ ] You can explain why the same prompt gives different answers, and how to constrain that
- [ ] You can build a working RAG pipeline from scratch (no framework) in Python
- [ ] You have a golden dataset and can measure a quality regression
- [ ] You can estimate the monthly cost of an LLM feature before building it
