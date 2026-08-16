# Stage 2 — Core DevOps 🟢→🟡

> **Goal:** CI/CD, containers, Kubernetes, Infrastructure as Code, and observability — the platform muscles that every AI-ops skill later attaches to.

## Why it matters

> *"Experience with modern cloud and ML infrastructure, including AWS, containers, Kubernetes, CI/CD, data pipelines, workflow orchestration"* — Senior AI Reliability Engineer
> *"Kubernetes, Terraform oder Pulumi, CI/CD-Toolchains"* — Enterprise AI Platform Architect
> *"Experience with CI/CD pipelines and containerization (e.g., Docker)"* — AI Platform Engineer

Every advanced stage (LLM gateways, GPU serving, agent governance) is *this* stage with AI on top.

## Core topics

1. **Containers** — Docker images, layers, registries, multi-stage builds, compose
2. **CI/CD** — GitHub Actions or GitLab CI: build → test → scan → deploy; pipeline-as-code
3. **Kubernetes** — pods, deployments, services, ingress, config/secrets, HPA, RBAC, Helm
4. **Infrastructure as Code** — Terraform (or Pulumi): state, modules, workspaces, CI-driven applies
5. **GitOps** — ArgoCD or Flux: the reconciliation model
6. **Observability** — Prometheus, Grafana, Loki; the three signals (metrics, logs, traces); **OpenTelemetry** — critical: LLM observability in Stage 6 is built on OTel
7. **SRE basics** — SLIs/SLOs, error budgets, incident response, blameless postmortems

## Resources

### Containers & Kubernetes
- 🎓 [Docker's official Getting Started](https://docs.docker.com/get-started/) (free)
- 🎓 [Kubernetes the Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way) (free) — do it once, understand forever
- 🎓 [KodeKloud CKA course](https://kodekloud.com/courses/certified-kubernetes-administrator-cka/) 💰 — best hands-on K8s labs available
- 📖 [Kubernetes docs — Concepts](https://kubernetes.io/docs/concepts/) — the primary source

### CI/CD & GitOps
- 🎓 [GitHub Actions docs](https://docs.github.com/actions) + [GitLab CI docs](https://docs.gitlab.com/ee/ci/)
- 🎓 [ArgoCD getting started](https://argo-cd.readthedocs.io/en/stable/getting_started/)
- 📖 [OpenGitOps principles](https://opengitops.dev/)

### IaC
- 🎓 [Terraform tutorials](https://developer.hashicorp.com/terraform/tutorials) (free, official)
- 📖 [Terraform Best Practices](https://www.terraform-best-practices.com/) (free)

### Observability & SRE
- 🎓 [Prometheus docs](https://prometheus.io/docs/introduction/overview/) + [Grafana fundamentals](https://grafana.com/tutorials/grafana-fundamentals/)
- 🎓 [OpenTelemetry docs](https://opentelemetry.io/docs/) — invest here; it pays off double in Stage 6
- 📖 [Google SRE Book](https://sre.google/sre-book/table-of-contents/) + [SRE Workbook](https://sre.google/workbook/table-of-contents/) (free) — read SLO, alerting, and postmortem chapters

## Hands-on

1. **The classic pipeline:** containerize a small web app → GitHub Actions builds, tests, scans (Trivy), pushes → ArgoCD deploys to a local cluster (kind/k3d) → Prometheus + Grafana dashboards → alert rule that pages you.
2. Write all infra (cluster, registry, DNS) as Terraform. Destroy and recreate from scratch in one command.
3. Instrument the app with OpenTelemetry traces and view them in Grafana Tempo or Jaeger.
4. Run a game day: kill the app in three different ways, write a one-page postmortem each time.

## 📜 Certifications that help here

**CKA** (Kubernetes admin), **KCNA** (cheap, entry), **Terraform Associate**. See [career/certifications.md](../../career/certifications.md).

## ✅ You're ready for Stage 3 when

- [ ] You can build and debug a full CI→CD→monitor loop from scratch
- [ ] You can explain reconciliation (GitOps) vs push deploys
- [ ] `kubectl describe` + `kubectl logs` + events are your reflexes, not lookups
- [ ] You can define an SLO and write the alert for its burn rate
