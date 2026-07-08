---
title: "Projects"
---

## AI BI Street — Interview Screener

*Sole backend engineer* | Nov 2025 – Apr 2026

Sole backend engineer on an AI-powered video interview platform (NestJS, Next.js, PostgreSQL) in production with active recruiter and candidate workflows. Built the full interview lifecycle: WebRTC video recording with chunked uploads, candidate invite flows, and passwordless magic-link auth across three user roles.

Designed an async media pipeline (BullMQ + Redis) for video compression, transcription, and LLM-based evaluation, with retry and job persistence. Built an AI interview-prep generator — ingests PDF resumes and job URLs, runs a 3-pass Groq editorial pipeline (generate, critique, rewrite) into structured PDF prep materials.

Migrated storage from local disk to Cloudflare R2, removing a recurring class of upload failures and enabling presigned-URL streaming. Built the subscription layer — feature gating, usage limits, and the REST contract with JWT auth and a Prisma-backed schema.

*Stack: NestJS · Next.js · PostgreSQL · Prisma · Redis (BullMQ) · Docker · Cloudflare R2 · Groq*

[Live site →](https://dev.screener.scrollverse.site)

---

## Production CI/CD Pipeline — Jenkins, Terraform, AWS EKS

[GitHub →](https://github.com/AngadVM/Prodution-CI-CD-pipeline)

8-stage Jenkins pipeline (lint, SonarCloud SAST, Docker build, Trivy scan, ECR push, Terraform apply, EKS deploy, smoke test) with hard-fail gates at every security step. Terraform-provisioned AWS infra (VPC, EKS, ECR, S3, IAM) with OIDC auth — zero long-lived keys in CI — and Checkov/tfsec gates that caught 12 real misconfigurations.

*Stack: Jenkins · Terraform · AWS EKS/ECR · Docker · Trivy · SonarCloud · Checkov · Python boto3*

---

## Reddit App Deployment on Amazon EKS

[GitHub →](https://github.com/AngadVM/Reddit-App-Deployment-on-Amazon-EKS)

Jenkins pipeline provisioning EKS via Terraform and gating every image build with SonarQube, OWASP Dependency-Check, and Trivy before push. ArgoCD GitOps sync (auto-prune, self-heal) with Prometheus/Grafana monitoring exposed via LoadBalancer.

*Stack: Jenkins · Terraform · ArgoCD · EKS · Docker · SonarQube · Trivy · Prometheus · Grafana*

---

## Go Profiler — CLI Performance Analyzer

[GitHub →](https://github.com/AngadVM/goprofiler)

Static analysis CLI that parses Go source via AST to flag performance anti-patterns with file-and-line-level fix suggestions.

*Stack: Go · Static Analysis · CLI*

---

*Something you want to build together?* [Let's talk →](/contact/)
