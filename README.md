# AI Cloud Engineer Learning path — 2026

The week-by-week topics, labs, and reference resources I use to run my live bootcamp. [Learn More](https://becloudready.com/programs/ai-cloud-engineer-bootcamp)


**Prerequisites:** basic Linux CLI, comfort with Bash or Python, an AWS Free Tier account.

---

## The learning path

| Week | Module | Tools | What you build | AI accelerates this |
|---|---|---|---|---|
| 1–2 | AWS Cloud Fundamentals | AWS, Terraform, IAM, EKS, Lambda | Custom VPC + IAM setup | Claude generates the templates, you decide the architecture |
| 2–3 | Docker & Kubernetes | Docker, Helm, ArgoCD | Containerised app on EKS cluster | AI writes the Dockerfile, you own the image hardening |
| 3–4 | Terraform + CI/CD | Terraform, GitHub Actions | Full IaC pipeline with security scanning | AI scaffolds the modules, you own state management |
| 4 | SRE & Observability | Grafana, Prometheus | Live incident simulation with dashboards | AI generates dashboard JSON, you calibrate the thresholds |
| 5 | AI / RAG / AgentOps | pgvector, LLM APIs, Ollama | Text-to-SQL RAG agent deployed to K8s | This IS the AI project — you own the guardrails |

---

## Week 0 — Before You Show Up

Get these out of the way so we don't burn live time on setup.

- AWS Free Tier account, IAM admin user with access keys, AWS CLI installed
- Docker Desktop installed and `docker run hello-world` works
- Terraform CLI installed (`terraform -v`)
- `kubectl` and `helm` installed
- VS Code (or your editor) + Git configured

Light pre-reading if you have time:
- [Understanding of OSI Model by Cloudflare](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi)
- [IP Address/CIDR Tool](https://cidr.xyz/)
- [LFS101 — Intro to Linux](https://training.linuxfoundation.org/training/introduction-to-linux/) Chapters 1–5
- [Introduction to Git & GitHub](https://www.youtube.com/watch?v=AhVUVezcj8g&list=PLc3FmsLyhBtspphc04ABMpmwf_aizn9Sq)

---

## Week 1 — Cloud Foundations & AWS Core

**Modules**

- [AWS Cloud Practitioner Essentials](https://skillbuilder.aws/learn/94T2BEN85A/aws-cloud-practitioner-essentials/9SSAGGQQ12)
- [Virtual Private Cloud - VPC](https://skillbuilder.aws/learn/PH6Z6EVH8Z/introduction-to-amazon-virtual-private-cloud-vpc/PA8H7FUE15)
- [AWS EC2](https://skillbuilder.aws/learn/DMG1BSGQNN/build-with-amazon-ec2/B7FZRSJADX)
- [AWS IAM - Lab builder](https://skillbuilder.aws/learn/XFPX3M7HAQ/introduction-to-aws-identity-and-access-management-iam/DQJ3N5QRRU)
- [AWS RDS - PostgreSQL](https://skillbuilder.aws/learn/AK479CRG5K/fundamentals-of-amazon-rds-for-postgresql/FB4ZR9N2DU)

---

## Week 2 — Containers & Orchestration

**Modules**

- [Enable WSL (Windows Susbsystem for Linux) in Windows](https://youtu.be/uXkhc8lW_3c?si=yUM_vqJ6UeoL5tTv)
- [Docker Desktop Setup - Windows](https://www.youtube.com/watch?v=ompGfhIKIJ0)
- [Docker Introduction](https://www.youtube.com/watch?v=pg19Z8LL06w)
- [Enable Kubernetes in Docker Desktop with WSL](https://www.youtube.com/watch?v=Yc1iCVXVFCI&t=3s)
- [Kubernetes overview](https://www.youtube.com/watch?v=XuSQU5Grv1g)

---

## Week 3 — Infrastructure as Code (Terraform)

**Modules**

- [Terraform Basics with AWS](https://www.youtube.com/watch?v=rsct-JvJmKs)


---

## Week 4 — CI/CD & Delivery Pipelines

**Modules**

- [Git & GitHub](https://www.youtube.com/watch?v=AhVUVezcj8g&list=PLc3FmsLyhBtspphc04ABMpmwf_aizn9Sq)
- [GitHub Actions - Detailed](https://www.youtube.com/watch?v=E2RRxcq_08E)

---

## Week 5 — SRE, Production Readiness & RAG Capstone

**Modules**

- [APM vs Observability](https://www.youtube.com/watch?v=CAQ_a2-9UOI)
- [Introduction to Observability](https://www.youtube.com/watch?v=TQur9GJHIIQ&list=PLDGkOdUX1Ujo27m6qiTPPCpFHVfyKq9jT)


---

### Week 6 - AI, LLM, Agents

- [How I use LLMs by Andrej Karpathy](https://www.youtube.com/watch?v=EWvNQjAaOHw)
- [AI Agent Skills by IBM](https://www.youtube.com/watch?v=Lg-meK5IU8Q)
- [AI Agents MCP](https://www.youtube.com/watch?v=pvxNcQTcIy4)
- [Retrieval-Augmented Generation - RAG](https://www.youtube.com/watch?v=T-D1OfcDW1M)
- [Claude Code Introduction by Anthropics](https://www.youtube.com/watch?v=fl1DSmwQKKY)

## Capstone projects

**[db-agent](https://github.com/db-agent/db-agent)** — text-to-SQL AI agent deployed on Kubernetes
- SQL safety guardrails, full CI/CD pipeline, presented at AAAI-25
- Available as Streamlit, Next.js+FastAPI, and native Databricks App

**[AWS enterprise data lake](https://github.com/becloudready/quick-labs/tree/master/labs/aws-data-lake)** — three-lab sequence for building a production-grade data lake on AWS
- Lab 1: S3 raw/curated zones, Glue PySpark ETL, Parquet, Athena
- Lab 2: event-driven ingestion — S3 triggers, SQS, Lambda, Redshift
- Lab 3: Lake Formation governance — row/column/tag-based access controls, CDC via DMS
- Entire environment provisioned with Terraform, per-student sandboxed IAM

## What AI has and hasn't changed

| AI commoditized this | Engineers still own this |
|---|---|
| Writing Terraform from scratch | State management, multi-account strategy |
| Dockerfile boilerplate | Image hardening, multi-stage builds |
| K8s manifest YAML | CNI, admission webhooks, cluster security |
| Basic alerting rules | Calibrating thresholds, incident command |
| RAG pipeline scaffolding | Chunk strategy, retrieval quality, guardrails |

AI wrote this table. I decided what goes in each column.

## How to use this repo

Option A — Self-paced: Work through the modules on your own. Everything links to the relevant open-source tools. No signup required.

Option B — With the cohort: Weekly live session on Mondays 6–8 PM EDT. Slack support throughout the week. Access to the TorontoAI founder and recruiter network (10,000+ members). $299 CAD one-time. [becloudready.com](https://becloudready.com/programs/ai-cloud-engineer-bootcamp)

Option C — Corporate: Private team workshops for Databricks and cloud engineering teams. [Book a call](https://calendly.com/kchandank/30-mins-meeting)

## Community

[TorontoAI](https://toronto-ai.org) — 10,000+ members across Toronto and US East Coast. Quarterly in-person events. Beehiiv newsletter: 2,400+ subscribers.
