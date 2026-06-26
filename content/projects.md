---
title: "Projects"
---

## AI BI Street — Interview Screener

*Sole backend engineer* | Nov 2025 – Apr 2026

Built the whole backend for a live SaaS product — automated video-response interviews with active recruiter and candidate accounts in production. Designed the full interview lifecycle: question sets, timed video recording, token-signed magic-link auth (no passwords stored). Containerised with Docker, wired a GitHub Actions pipeline that builds, tests, and deploys on every merge to main. Instrumented with Prometheus and built a Grafana dashboard tracking latency, error rate, and throughput. Architected a subscription model with middleware-level feature gating.

*Stack: NestJS · Next.js · PostgreSQL · Docker · GitHub Actions · Prometheus · Grafana*

[Live site →](https://dev.screener.scrollverse.site)

---

## Production CI/CD Pipeline — GitHub Actions + Terraform + AWS EKS

[GitHub →](https://github.com/AngadVM/Prodution-CI-CD-pipeline)

Designed an 8-stage GitHub Actions pipeline — lint, SonarCloud SAST, Docker build, Trivy CVE scan, ECR push, Terraform apply, EKS deploy, boto3 smoke test — with hard-fail gates at each security step. Provisioned AWS infra (VPC, EKS, ECR, S3, IAM) via Terraform modules with remote state in S3 + DynamoDB lock; used OIDC auth — zero long-lived AWS keys in CI. Added Checkov and tfsec IaC security gates, resolving 12 real violations. Deployed kube-prometheus-stack via Helm with PromQL alerting rules routed to Slack through Alertmanager.

*Stack: GitHub Actions · Terraform · AWS EKS/ECR · Docker · Helm · Prometheus · Grafana · Trivy · SonarCloud · Checkov · Python boto3*

---

## GitOps Platform — ArgoCD + Vault + Blue-Green Delivery

[GitHub →](https://github.com/AngadVM/GitOps-platform)

Implemented two-repo GitOps: CI updates only the Helm values image tag in a config repo — ArgoCD auto-syncs to EKS within 3 minutes. Zero kubectl in CI pipelines. Configured Argo Rollouts blue-green strategy with a Prometheus analysis template — auto-promotes if error rate < 1%, auto-aborts on breach. Deployed HashiCorp Vault on Kubernetes with Agent Injector — eliminated every hardcoded secret, replaced with dynamic injection at pod start; Sealed Secrets handles git-committed encrypted values that only the cluster can decrypt.

*Stack: ArgoCD · Argo Rollouts · Helm · Kubernetes · Vault · Sealed Secrets · GitHub Actions · AWS EKS*

---

## Go Profiler — CLI Performance Analyzer

[GitHub →](https://github.com/AngadVM)

Parses Go source files using the AST to flag anti-patterns — string concatenation inside loops, deferred calls in hot paths, unnecessary allocations — and prints file-and-line-level fix suggestions to stdout.

*Stack: Go · Static Analysis · CLI*

---

*Something you want to build together?* [Let's talk →](/contact/)
