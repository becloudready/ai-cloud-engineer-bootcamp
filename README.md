# AI Cloud Engineer Bootcamp — Syllabus

The week-by-week topics, labs, and reference resources I use to run my live bootcamp.

For the current cohort dates, format, price, and registration, see the course page:
→ [becloudready.com/programs/ai-cloud-engineer-bootcamp](https://becloudready.com/programs/ai-cloud-engineer-bootcamp)

**Format note (updated):** Earlier cohorts ran as a 5-day Mon–Fri intensive. Based on feedback that the pace was overwhelming, the program now runs across **6 weeks, every Monday, 6:00–8:00 PM EST**. The total instructional time (~12 hours live) is the same — just spread out so you can actually finish the labs between sessions. Ongoing Slack support across all 6 weeks, plus a 1-hour interview prep session after completion.

**Prerequisites:** basic Linux CLI, comfort with Bash or Python, an AWS Free Tier account.

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

## Week 1 — Cloud Foundations

**Topics**
- VPC, IAM, EC2, S3, RDS — deep dive
- Networking, Security Groups, NACLs
- Cost optimisation & billing
- AWS CLI & SDK fundamentals

**Lab (this week)**
Stand up a 3-tier VPC (public/private subnets, NAT, IGW), launch an EC2 instance into the private subnet, attach a bastion, query S3 via CLI from the instance, and write a least-privilege IAM policy that scopes access to a single bucket. Lab support runs in Slack all week.

**References**
- [AWS Technical Essentials](https://skillbuilder.aws/learn/A8RGTRTGE2/aws-technical-essentials/JGW7HKGGUM)
- [VPC docs](https://docs.aws.amazon.com/vpc/) · [IAM docs](https://docs.aws.amazon.com/iam/) · [EC2 docs](https://docs.aws.amazon.com/ec2/) · [S3 docs](https://docs.aws.amazon.com/s3/)
- [Well-Architected Labs](https://www.wellarchitectedlabs.com/)
- [quick-labs](https://github.com/becloudready/quick-labs) — my repo for fast instance launchers

---

## Week 2 — Containers

**Topics**
- Docker — images, layers, networking, volumes, multi-stage builds
- Kubernetes architecture — pods, deployments, services, ingress
- EKS cluster setup on AWS
- Helm charts and GitOps with Argo CD

**Lab (this week)**
Containerise a Python/FastAPI app with a multi-stage Dockerfile (<50 MB final image), push to ECR, deploy to an EKS cluster via a Helm chart, then wire Argo CD to auto-sync the deployment from a Git repo.

**References**
- [Docker — Get Started](https://docs.docker.com/get-started/) · [Multi-stage builds](https://docs.docker.com/build/building/multi-stage/)
- [Learn Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [EKS Workshop](https://www.eksworkshop.com/)
- [Helm — Quickstart](https://helm.sh/docs/intro/quickstart/)
- [Argo CD — Getting Started](https://argo-cd.readthedocs.io/en/stable/getting_started/)
- [docker-tutorials](https://github.com/becloudready/docker-tutorials) · [kubernetes-tutorials](https://github.com/becloudready/kubernetes-tutorials)

---

## Week 3 — Terraform

**Topics**
- Terraform modules & workspaces
- Remote state with S3 + DynamoDB locking
- Drift detection and remediation
- Security scanning with tfsec

**Lab (this week)**
Rewrite Week 1's manually-built VPC + EC2 as Terraform modules with a `dev` and `prod` workspace, store state remotely with locking, and demo `terraform plan` catching a drift.

**References**
- [Terraform — Get Started on AWS](https://developer.hashicorp.com/terraform/tutorials/aws-get-started)
- [HashiCorp Developer — Terraform tutorials](https://developer.hashicorp.com/terraform/tutorials)
- [Terraform Registry](https://registry.terraform.io/)
- [EKS Terraform Workshop](https://tf-eks-workshop.workshop.aws/)
- [terraform-tutorials](https://github.com/becloudready/terraform-tutorials)

---

## Week 4 — DevOps / SRE

**Topics**
- GitHub Actions — build, test, deploy workflows
- Blue-green and canary deployment strategies
- Container registry workflows + image scanning
- Secrets management (AWS Secrets Manager / Vault)
- SLOs, error budgets, alerting with Grafana / Datadog
- Log aggregation and distributed tracing (OpenTelemetry)
- Incident response playbooks

**Lab (this week)**
Wire a GitHub Actions workflow that, on push to `main`: runs tests → builds + scans a container → pushes to ECR (via OIDC, no static keys) → triggers Argo CD to roll out a blue-green deploy to EKS. Add Prometheus/Grafana dashboards and an OpenTelemetry-instrumented service, define one SLO with an error budget, and write a one-page runbook for a simulated incident.

**References**
- [GitHub Actions docs](https://docs.github.com/en/actions) · [Quickstart](https://docs.github.com/en/actions/get-started/quickstart)
- [Google SRE Book](https://sre.google/sre-book/table-of-contents/) · [Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)
- [Prometheus — First Steps](https://prometheus.io/docs/introduction/first_steps/)
- [Grafana Labs tutorials](https://grafana.com/tutorials/)
- [OpenTelemetry documentation](https://opentelemetry.io/docs/)
- [DORA — DevOps Research & Assessment](https://dora.dev/) — the four key metrics
- [OWASP DevSecOps Guideline](https://owasp.org/www-project-devsecops-guideline/)
- [Snyk Learn](https://learn.snyk.io/)

---

## Week 5 — AI, RAG, and AgentOps

**Topics**
- Why every production AI agent is a distributed system, not a notebook
- LLM serving — hosted endpoints vs. self-hosted (vLLM, TGI) on GPU nodes
- Vector databases — pgvector, Pinecone; embedding workers; index lifecycle
- RAG pipeline architecture — retrieval API, reranking, evals
- AgentOps — agent orchestration, tool registries, observability for LLM calls, cost guardrails, prompt versioning
- SQL-safety patterns for agents that touch real data (read-only roles, query budgets, schema allow-lists)

**Lab (this week)**
Layer a small RAG service on top of the EKS cluster from earlier weeks: pgvector as the vector store, a small embedding worker, a FastAPI retrieval service, and an OpenAI-compatible LLM endpoint (vLLM or a hosted model). Instrument the LLM calls with OpenTelemetry, set a per-request token budget, and add a Grafana panel for cost-per-request.

**References**
- [LangChain docs](https://python.langchain.com/docs/get_started/introduction)
- [LlamaIndex docs](https://docs.llamaindex.ai/)
- [pgvector](https://github.com/pgvector/pgvector) · [Pinecone docs](https://docs.pinecone.io/)
- [vLLM](https://docs.vllm.ai/) · [Text Generation Inference (TGI)](https://huggingface.co/docs/text-generation-inference/index)
- [OpenTelemetry for LLMs (Traceloop / OpenLLMetry)](https://github.com/traceloop/openllmetry)
- [db-agent](https://github.com/db-agent/db-agent) — my open-source reference for the SQL-safety + agent pattern

---

## Week 6 — Project: End-to-End Agentic AI Data Engineering (db-agent)

**The capstone.** You take everything from Weeks 1–5 and ship one working system: an agentic text-to-SQL data engineering pipeline, deployed on the cloud you've been building all along.

**What you'll build**
- A working clone of the open-source [db-agent](https://github.com/db-agent/db-agent) pattern on your own AWS account
- Backend: FastAPI retrieval service + LLM endpoint (Week 5) running on the EKS cluster (Week 2), provisioned by Terraform (Week 3), deployed via the GitHub Actions + Argo CD pipeline (Week 4)
- Read-only SQL execution path with query budgets and a schema allow-list (the safety pattern that keeps agents out of production data)
- Observability — traces, token-cost dashboards, an SLO on retrieval latency
- A one-page architecture diagram, a runbook, and a short demo video

This is the project you point recruiters at. End-to-end, real cloud, real AI infra, your code.

**References**
- [db-agent repo](https://github.com/db-agent/db-agent) — the pattern, three deployment variants, five progressive modules
- [AAAI-25 workshop materials](https://github.com/db-agent/db-agent) — context on the SQL-safety design

---

## After the Bootcamp

- **1-hour interview prep session** the week after Week 6 — resume review, LinkedIn audit, technical-interview question patterns for Cloud / DevOps / AI Cloud Engineer roles.
- Lifetime access to the beCloudReady Slack community.
- Eligible to re-attend future cohorts at no extra cost as the curriculum evolves.

Also useful:
- Interview prep practice repos: [k8s-interview-action](https://github.com/becloudready/k8s-interview-action) · [interview-challenges](https://github.com/becloudready/interview-challenges)

— Chandan Kumar, [beCloudReady](https://becloudready.com)
