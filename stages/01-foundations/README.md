# Stage 1 — Foundations 🟢

> **Goal:** Linux, networking, Git, Python/Bash, and one hyperscaler cloud — the non-negotiables every job post assumes.

## Why it matters

> *"Strong Python skills and experience building production-quality systems"* — Senior AI Reliability Engineer
> *"Proficiency in at least one programming language (e.g., Python, Go)"* — AI Platform Engineer
> *"Mindestens eine Hyperscaler-Cloud wie AWS, Azure oder GCP"* — Enterprise AI Platform Architect

No AI-ops role hires without these. If you already have 1–2 years of DevOps/cloud experience, skim the checklist and move on.

## Core topics

1. **Linux** — shell, processes, filesystems, permissions, systemd, ssh, package managers
2. **Networking** — DNS, HTTP(S), TLS, load balancing, proxies, VPCs, firewalls
3. **Git & GitHub/GitLab** — branching, PRs, code review flow, GitHub Actions basics
4. **Python** — the lingua franca of AI ops: scripting, virtualenvs, `requests`, typing, testing with pytest. Add **Bash** for glue. (Go is a strong second language for platform roles — later.)
5. **One cloud, properly** — pick AWS or Azure or GCP: compute, storage, IAM, VPC, managed databases. IAM especially — every AI governance topic later builds on it.
6. **How computers run code** — enough OS and hardware understanding to later reason about GPUs, memory, and throughput.

## Resources

### Linux & shell
- 🎓 [The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) (MIT, free) — shell, editors, git, debugging in ~12 lectures
- 🎓 [Linux Journey](https://linuxjourney.com/) (free) — gentle, complete
- 📖 [Julia Evans' zines](https://wizardzines.com/) 💰 (some free) — the fastest way to *actually* understand networking, containers, strace

### Git
- 🎓 [Pro Git book](https://git-scm.com/book/en/v2) (free) — chapters 1–3 + 5 suffice
- 🧪 [Oh My Git!](https://ohmygit.org/) (free) — learn git as a game

### Python
- 🎓 [Python for Everybody](https://www.py4e.com/) (free) — if new to programming
- 📖 [Automate the Boring Stuff](https://automatetheboringstuff.com/) (free) — scripting mindset
- 🎓 [Real Python](https://realpython.com/) — reference for everything intermediate

### Cloud
- 🎓 [AWS Skill Builder](https://skillbuilder.aws/) / [Microsoft Learn](https://learn.microsoft.com/training/) / [Google Cloud Skills Boost](https://www.cloudskillsboost.google/) — official free training paths
- 🎓 [KodeKloud free courses](https://kodekloud.com/free-courses) — hands-on labs in browser
- 📖 [Open Guide to AWS](https://github.com/open-guides/og-aws) — practitioner wisdom

## Hands-on

1. **Daily-drive Linux** for the whole stage (VM, WSL2, or old laptop).
2. Write a Python CLI that calls a public REST API, retries with backoff, logs properly, and ships with tests — your first "production-quality" habit.
3. Deploy a static site + a small API on your chosen cloud using only the CLI (no console clicking). Tear it down with a script.
4. Break something on purpose (kill a process, fill a disk, block a port) and debug it with `journalctl`, `ss`, `df`, `htop`.

## ✅ You're ready for Stage 2 when

- [ ] You live in a terminal without discomfort
- [ ] You can explain what happens end-to-end when you `curl https://example.com`
- [ ] You can write, test, and package a 200-line Python tool
- [ ] You can provision compute + storage + IAM on one cloud from the CLI
