# AI Cloud Engineer Bootcamp — Syllabus

The week-by-week topics, labs, and reference resources I use to run my live bootcamp.


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
- [LFS101 — Intro to Linux](https://training.linuxfoundation.org/training/introduction-to-linux/) Chapters 1–5
- [Git & GitHub — my YouTube playlist](https://www.youtube.com/watch?v=AhVUVezcj8g&list=PLc3FmsLyhBtspphc04ABMpmwf_aizn9Sq)
- [AWS Cloud Practitioner Essentials](https://skillbuilder.aws/learn/94T2BEN85A/aws-cloud-practitioner-essentials/9SSAGGQQ12) — first 2 modules

---

## Week 1 — Cloud Foundations & AWS Core

**Topics**
- VPC, IAM, EC2, S3, RDS — deep dive
- Networking, Security Groups, NACLs
- Cost optimisation & billing
- AWS CLI & SDK fundamentals

**Lab**
Stand up a 3-tier VPC (public/private subnets, NAT, IGW), launch an EC2 instance into the private subnet, attach a bastion, query S3 via CLI from the instance, and write a least-privilege IAM policy that scopes access to a single bucket.

**References**
- [AWS Technical Essentials](https://skillbuilder.aws/learn/A8RGTRTGE2/aws-technical-essentials/JGW7HKGGUM)
- [VPC docs](https://docs.aws.amazon.com/vpc/) · [IAM docs](https://docs.aws.amazon.com/iam/) · [EC2 docs](https://docs.aws.amazon.com/ec2/) · [S3 docs](https://docs.aws.amazon.com/s3/)
- [Well-Architected Labs](https://www.wellarchitectedlabs.com/)
- [quick-labs](https://github.com/becloudready/quick-labs) — my repo for fast instance launchers

---

## Week 2 — Containers & Orchestration

**Topics**
- Docker — images, layers, networking, volumes, multi-stage builds
- Kubernetes architecture — pods, deployments, services, ingress
- EKS cluster setup on AWS
- Helm charts and GitOps with Argo CD

**Lab**
Containerise a Python/FastAPI app with a multi-stage Dockerfile (<50 MB final image), push to ECR, deploy to an EKS cluster via a Helm chart, then wire Argo CD to auto-sync the deployment from a Git repo.

**References**
- [Docker — Get Started](https://docs.docker.com/get-started/) · [Multi-stage builds](https://docs.docker.com/build/building/multi-stage/)
- [Learn Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [EKS Workshop](https://www.eksworkshop.com/)
- [Helm — Quickstart](https://helm.sh/docs/intro/quickstart/)
- [Argo CD — Getting Started](https://argo-cd.readthedocs.io/en/stable/getting_started/)
- [docker-tutorials](https://github.com/becloudready/docker-tutorials) · [kubernetes-tutorials](https://github.com/becloudready/kubernetes-tutorials)

---

## Week 3 — Infrastructure as Code (Terraform)

**Topics**
- Terraform modules & workspaces
- Remote state with S3 + DynamoDB locking
- Drift detection and remediation

**Lab**
Rewrite Week 1's manually-built VPC + EC2 as Terraform modules with a `dev` and `prod` workspace, store state remotely with locking, and demo `terraform plan` catching a drift.

**References**
- [Terraform — Get Started on AWS](https://developer.hashicorp.com/terraform/tutorials/aws-get-started)
- [HashiCorp Developer — Terraform tutorials](https://developer.hashicorp.com/terraform/tutorials)
- [Terraform Registry](https://registry.terraform.io/)
- [EKS Terraform Workshop](https://tf-eks-workshop.workshop.aws/)
- [terraform-tutorials](https://github.com/becloudready/terraform-tutorials)

---

## Week 4 — CI/CD & Delivery Pipelines

**Topics**
- GitHub Actions — build, test, deploy workflows
- Blue-green and canary deployment strategies
- Container registry workflows + image scanning
- Secrets management (AWS Secrets Manager / Vault)

**Lab**
Wire a GitHub Actions workflow that, on push to `main`: runs tests → builds + scans a container → pushes to ECR (via OIDC, no static keys) → triggers Argo CD to roll out a blue-green deploy to EKS. Demo the rollback path.

**References**
- [GitHub Actions docs](https://docs.github.com/en/actions) · [Quickstart](https://docs.github.com/en/actions/get-started/quickstart)
- [GitHub Skills](https://github.com/skills)
- [OWASP DevSecOps Guideline](https://owasp.org/www-project-devsecops-guideline/)
- [DORA — DevOps Research & Assessment](https://dora.dev/) — the four key metrics
- [Snyk Learn](https://learn.snyk.io/)

---

## Week 5 — SRE, Production Readiness & RAG Capstone

**Topics**
- SLOs and error budgets
- Alerting with Grafana / Datadog
- Log aggregation and distributed tracing (OpenTelemetry)
- Incident response playbooks
- Small RAG pipeline architecture — vector DB, embedding service, retrieval API, LLM endpoint
- Capstone demo

**Lab / Capstone**
Build out the production reference stack: AWS + EKS (Terraform-managed) + a multi-service app (Kafka, PostgreSQL, Redis) + CI/CD from Week 4 + Prometheus/Grafana dashboards + an OpenTelemetry-instrumented service + a one-page runbook for a simulated incident — then layer a small RAG pipeline on top (pgvector or Pinecone as the vector store, an embedding worker, a FastAPI retrieval service, and an OpenAI-compatible LLM endpoint via vLLM or a hosted model).

**References**
- [Google SRE Book](https://sre.google/sre-book/table-of-contents/) · [Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)
- [Prometheus — First Steps](https://prometheus.io/docs/introduction/first_steps/)
- [Grafana Labs tutorials](https://grafana.com/tutorials/)
- [OpenTelemetry documentation](https://opentelemetry.io/docs/)

---

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
