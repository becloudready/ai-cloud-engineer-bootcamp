# AI Cloud Engineer Bootcamp

A free, self-paced learning path for cloud and AI engineering — built for career changers.

## Who this is for

If you're a sysadmin, Windows admin, DBA, desktop support tech, someone returning from a career break, or a new immigrant to Canada or the US trying to break into tech — this is for you. You have more transferable skills than you think. Knowing how to manage production systems, troubleshoot under pressure, or keep a database running through a deployment window is a foundation, not a liability. This path gives you the vocabulary and the portfolio to make that case.

## Why this exists

Every three years or so, a new technology wave hits and reshuffles the deck. The engineers who survive are the ones who adapt — not because they're geniuses, but because they've done it before. I've been doing this for 20 years: started in C/C++, pivoted to Python, then DevOps, then Big Data, and now I design AI platforms for a living. This repo is the roadmap I wish I had each time I made one of those transitions. — Chandan Kumar

## The learning path

| Week | Module | Tools | What you build | AI accelerates this |
|---|---|---|---|---|
| 1–2 | AWS Cloud Fundamentals | AWS, Terraform, IAM, EKS, Lambda | Custom VPC + IAM setup | Claude generates the templates, you decide the architecture |
| 2–3 | Docker & Kubernetes | Docker, Helm, ArgoCD | Containerised app on EKS cluster | AI writes the Dockerfile, you own the image hardening |
| 3–4 | Terraform + CI/CD | Terraform, GitHub Actions | Full IaC pipeline with security scanning | AI scaffolds the modules, you own state management |
| 4 | SRE & Observability | Grafana, Prometheus | Live incident simulation with dashboards | AI generates dashboard JSON, you calibrate the thresholds |
| 5 | AI / RAG / AgentOps | pgvector, LLM APIs, Ollama | Text-to-SQL RAG agent deployed to K8s | This IS the AI project — you own the guardrails |

## Capstone projects

**db-agent** — [db-agent](https://github.com/db-agent/db-agent) is a text-to-SQL AI agent with SQL safety guardrails, deployed on Kubernetes and Databricks using a full CI/CD pipeline. It was presented at AAAI-25 and is available as Streamlit and a native Databricks App. This is what a production AI project looks like — not a notebook, not a demo, but an actual system with observability, access controls, and a deployment pipeline.

**AWS enterprise data lake** — [aws-data-lake](https://github.com/becloudready/quick-labs/tree/main/labs/aws-data-lake) is a three-lab sequence for building a production-grade data lake on AWS. Lab 1 builds the core pipeline: S3 raw and curated zones, a Glue PySpark ETL job converting CSV to partitioned Parquet, and Athena for querying. Lab 2 adds event-driven ingestion — S3 triggers, SQS fan-out, and Lambda handlers that feed both S3 and Redshift for a lakehouse pattern. Lab 3 covers governance with AWS Lake Formation: row-level, column-level, and tag-based access controls, with a CDC pipeline from RDS PostgreSQL via DMS. The entire environment is provisioned with Terraform using per-student sandboxed IAM. AI can generate Glue scripts and Terraform modules in seconds; owning the partition strategy, the Lake Formation tag taxonomy, and the access model is still the job.

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

Option C — Corporate: Private team workshops for Databricks and cloud engineering teams. [Book a Meeting](https://calendly.com/kchandank/30-mins-meeting)

## Community

[TorontoAI](https://toronto-ai.org) — 10,000+ members across Toronto and US East Coast. Quarterly in-person events. Beehiiv newsletter: 2,400+ subscribers.
