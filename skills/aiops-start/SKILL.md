---
name: aiops-start
description: One-time onboarding for the AIOps Zero to Hero curriculum (11 stages, DevOps/SRE/Platform + AI). Interviews the learner, runs a placement quiz, and writes LEARNING.md — the persistent study plan that /aiops-learn drives. Use for "start learning", "set up the course", "onboard me", "where should I start", "create my learning plan".
---

# AIOps Start — placement & study plan

You onboard a learner into **AIOps Zero to Hero** and produce `LEARNING.md`
in the current directory. Keep the whole flow under 10 minutes.

## Content resolution (all aiops-* skills follow this)

1. **Local first:** if a `stages/` directory exists here (repo is cloned),
   read stage files from `stages/<NN-name>/README.md`.
2. **Remote fallback:** otherwise fetch
   `https://raw.githubusercontent.com/nomadicmehul/aiopszerotohero/main/stages/<NN-name>/README.md`
   (same paths as local). Never invent content you couldn't fetch.

## If LEARNING.md already exists

Offer three choices before doing anything:
1. **Resume** — hand off to `/aiops-learn` behavior; touch nothing.
2. **Re-run placement** — update only the Placement section and Path
   statuses; keep the progress log and review queue.
3. **Start over** — archive the file as `LEARNING-<YYYY-MM-DD>.md`, then
   proceed fresh.

## The interview (3 questions, verbatim answers into Mission)

1. Why this track? What role are you aiming for?
2. Hours per week you can realistically commit?
3. What do you want to have *built* by the end? (a portfolio capstone goal)

## The placement quiz (10 questions, or self-select)

Offer to skip: an experienced learner may self-select an entry stage
(validate it against the "Who this is for" table; record `self-selected`).

Otherwise ask 10 short questions, 2 per area, one at a time:
- **Linux/Git** — e.g. what does `chmod +x` do; what's a merge conflict
- **Python** — read a 5-line script and predict output; what's a virtualenv
- **Cloud & Kubernetes** — what is a pod; IAM role vs user
- **CI/CD, IaC & observability** — what does `terraform plan` show; what's a
  p95 latency
- **LLM fundamentals** — why are LLM outputs non-deterministic; what is RAG

Score each area 0–2. Map to entry stage:
- Weak everywhere → **Stage 0**
- Code OK, ops weak → **Stage 1**
- Some ops, shaky K8s/IaC → **Stage 2**
- Solid ops, weak LLM → **Stage 3** (the classic DevOps→AI entry)
- Solid ops + LLM basics → **Stage 4 or 5** (ask which interest pulls more)

Stages before the entry point get status `Skip` (or `Review` if an area
scored 1/2 — partial knowledge deserves a skim, not a skip).

## Write LEARNING.md

```markdown
# 🛰️ My AIOps Zero to Hero Plan

## Mission
<their words: why, target role, capstone goal>

## Placement
- Date: <YYYY-MM-DD> · Result: <N>/10 (or self-selected)
- Entry stage: <N — title> · Weekly pace: <N> hrs/week
- Estimated finish: <date, from remaining hours ÷ weekly pace>

## Path
| Stage | Status | Est. hours |
|---|---|---|
| 0 — Orientation & Career Map | Do | 5 |
| 1 — Foundations | Do | 60 |
| 2 — Core DevOps | Do | 100 |
| 3 — AI Fundamentals | Do | 40 |
| 4 — AI-Assisted Ops | Do | 30 |
| 5 — LLM Platform Engineering | Do | 40 |
| 6 — AI Observability & Reliability | Do | 40 |
| 7 — AI Infrastructure | Do | 50 |
| 8 — Agentic Operations | Do | 30 |
| 9 — Security, Governance & Compliance | Do | 30 |
| 10 — Capstones & Portfolio | Do | 60 |

Status legend: Skip · Review · Do · Done

## Progress log
| Date | Stage · Topic | Activity | Result | Notes |
|---|---|---|---|---|

## Review queue
<!-- weak quiz topics land here; /aiops-quiz drains it -->
```

Adjust the Status column per placement, compute the finish estimate, then
close with: their entry stage, why, and the exact next command —
**"Run `/aiops-learn` to start your first session."**
