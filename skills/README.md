# 📦 Learn in your terminal — with the AI agent of your choice

This curriculum ships as **Agent Skills** (the open `SKILL.md` format), so
your AI coding agent becomes your tutor, quizmaster, and lab reviewer.
Everything runs **locally**: your plan, progress, and lab code stay on your
machine, and the skills work with Claude Code, Cursor, Codex, and any other
SKILL.md-compatible agent.

## Install (no clone needed)

```bash
npx skills add nomadicmehul/aiopszerotohero
```

Then open your agent anywhere and run:

```
/aiops-start
```

The skills fetch stage content straight from GitHub when the repo isn't
cloned. Prefer having everything local (labs live better in a repo)?

```bash
git clone https://github.com/nomadicmehul/aiopszerotohero.git
cd aiopszerotohero
claude   # skills auto-load from .claude/skills
```

## The commands

| Command | What it does |
|---|---|
| [`/aiops-start`](aiops-start/SKILL.md) | One-time onboarding: 3-question interview + 10-question placement quiz → writes `LEARNING.md`, your persistent study plan |
| [`/aiops-learn`](aiops-learn/SKILL.md) | One focused session per run: teaches the next topic interactively (problem → concept → hands-on → check), or advances your current lab. Records progress |
| [`/aiops-quiz`](aiops-quiz/SKILL.md) | Honest checks + spaced repetition: drains your review queue, tells you when you're ready to move on (and when you're not) |
| [`/aiops-lab-review`](aiops-lab-review/SKILL.md) | Senior-engineer review of your lab work against the stage's checklist — pass / not-yet verdicts, concrete fixes |
| [`/aiops-guide`](aiops-guide/SKILL.md) | "Where do I learn vLLM / RAG / Terraform / guardrails?" — instant pointer into the right stage |

## How progress works

Everything lives in one file the skills maintain for you — `LEARNING.md`:

- **Mission** — your goal, in your words
- **Placement** — where you entered and why
- **Path** — all 11 stages with status: `Skip / Review / Do / Done`
- **Progress log** — every session, quiz, and lab review
- **Review queue** — weak topics, re-tested until they stick

It's gitignored. Delete it (or ask `/aiops-start` to start over — it
archives the old one) any time.

## Your data stays yours

The skills write exactly one file (`LEARNING.md`). Nothing is sent anywhere
except your own conversations with your own agent.

## Contributing skills

Ideas welcome — an interview-prep drill, a capstone planner, a
resource-freshness checker. Open a PR: see [CONTRIBUTING.md](../CONTRIBUTING.md).
