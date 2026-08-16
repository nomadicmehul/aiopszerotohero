# 📦 Agent Skills — learn with the AI agent of your choice

This curriculum doesn't just sit in markdown files — it ships as **Agent
Skills**, so your AI coding agent becomes your mentor, lab reviewer, and
quizmaster. Everything runs **locally against this repo**: your progress, your
lab code, and your learning log stay on your machine.

Skills use the open [Agent Skills format](https://code.claude.com/docs/en/skills)
(a folder with a `SKILL.md`), supported by Claude Code and a growing list of
agents. Any agent that can read files can use them — worst case, paste the
`SKILL.md` as a system prompt.

## The skills

| Skill | What it does |
|---|---|
| [`aiops-mentor`](aiops-mentor/SKILL.md) | Places you on the roadmap, teaches each stage, tracks your progress in `my-learning-log.md` |
| [`aiops-lab-reviewer`](aiops-lab-reviewer/SKILL.md) | Reviews your hands-on lab work against the stage's checklist, like a senior engineer |
| [`aiops-quiz`](aiops-quiz/SKILL.md) | Spaced-repetition quizzes on stages you've studied — scenario questions, honest grading |

## Use with Claude Code

The repo's `.claude/skills/` already points at this folder, so it just works:

```bash
git clone https://github.com/YOUR_USERNAME/aiopszerotohero.git
cd aiopszerotohero
claude
```

Then say things like:

- *"Start me on the AIOps curriculum"* → mentor places you and builds your plan
- *"Teach me stage 3"* / *"What's next?"*
- *"Review my lab"* (with your lab code in or linked from the repo)
- *"Quiz me on stage 2"* / *"Am I ready for stage 4?"*

> **Windows note:** `.claude/skills` is a symlink. If your clone doesn't
> support symlinks, copy the folders instead: `cp -r skills/* .claude/skills/`.

## Use with other agents

- **Any SKILL.md-compatible agent** (Cursor, Codex CLI, opencode, …): point it
  at this repo's `skills/` directory per your agent's skills documentation.
- **Any agent at all:** open the skill's `SKILL.md` and paste it as your
  system prompt / custom instructions, then work inside the cloned repo.

## Your data stays yours

The skills write exactly one file: `my-learning-log.md` in the repo root
(gitignored). Delete it to start over. Nothing is sent anywhere except your
own conversations with your own agent.

## Contributing skills

Ideas welcome — an interview-prep drill skill, a capstone project planner, a
resource-freshness checker. Same rules as the rest of the repo: open a PR, see
[CONTRIBUTING.md](../CONTRIBUTING.md).
