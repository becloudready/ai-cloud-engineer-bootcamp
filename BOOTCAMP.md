# AI Cloud Engineer Bootcamp — Syllabus

The day-by-day topics, labs, and reference resources I use to run my live bootcamp.

For the current cohort dates, format, price, and registration, see the course page:
→ [becloudready.com/programs/ai-cloud-engineer-bootcamp](https://becloudready.com/programs/ai-cloud-engineer-bootcamp)

For the broader self-study list of official resources, see [README.md](./README.md).

**Prerequisites:** basic Linux CLI, comfort with Bash or Python, an AWS Free Tier account.

---

## Day 0 — Before You Show Up

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

## Day 1 — Cloud Foundations & AWS Core

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

## Day 2 — Containers & Orchestration

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

## Day 3 — Infrastructure as Code (Terraform)

**Topics**
- Terraform modules & workspaces
- Remote state with S3 + DynamoDB locking
- Drift detection and remediation

**Lab**
Rewrite Day 1's manually-built VPC + EC2 as Terraform modules with a `dev` and `prod` workspace, store state remotely with locking, and demo `terraform plan` catching a drift.

**References**
- [Terraform — Get Started on AWS](https://developer.hashicorp.com/terraform/tutorials/aws-get-started)
- [HashiCorp Developer — Terraform tutorials](https://developer.hashicorp.com/terraform/tutorials)
- [Terraform Registry](https://registry.terraform.io/)
- [EKS Terraform Workshop](https://tf-eks-workshop.workshop.aws/)
- [terraform-tutorials](https://github.com/becloudready/terraform-tutorials)

---

## Day 4 — CI/CD & Delivery Pipelines

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

## Day 5 — SRE, Production Readiness & RAG Capstone

**Topics**
- SLOs and error budgets
- Alerting with Grafana / Datadog
- Log aggregation and distributed tracing (OpenTelemetry)
- Incident response playbooks
- Small RAG pipeline architecture — vector DB, embedding service, retrieval API, LLM endpoint
- Capstone demo

**Lab / Capstone**
Build out the production reference stack: AWS + EKS (Terraform-managed) + a multi-service app (Kafka, PostgreSQL, Redis) + CI/CD from Day 4 + Prometheus/Grafana dashboards + an OpenTelemetry-instrumented service + a one-page runbook for a simulated incident — then layer a small RAG pipeline on top (pgvector or Pinecone as the vector store, an embedding worker, a FastAPI retrieval service, and an OpenAI-compatible LLM endpoint via vLLM or a hosted model). Demo the full AI Cloud Engineer reference stack on Day 5 evening.

**References**
- [Google SRE Book](https://sre.google/sre-book/table-of-contents/) · [Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)
- [Prometheus — First Steps](https://prometheus.io/docs/introduction/first_steps/)
- [Grafana Labs tutorials](https://grafana.com/tutorials/)
- [OpenTelemetry documentation](https://opentelemetry.io/docs/)

---

## After the Bootcamp

Mentoring, capstone review, resume and LinkedIn review, hiring-partner intros, and lifetime community access are all included with the current cohort — full details on the [course page](https://becloudready.com/programs/ai-cloud-engineer-bootcamp).

Also useful:
- Interview prep: [k8s-interview-action](https://github.com/becloudready/k8s-interview-action) · [interview-challenges](https://github.com/becloudready/interview-challenges)
- Broader self-study list: [README.md](./README.md)

— Chandan Kumar, [beCloudReady](https://becloudready.com)
