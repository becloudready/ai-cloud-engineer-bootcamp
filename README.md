# DevOps Launchpad

A curated list of the best **official, free** training I point my students to — AWS, Kubernetes, Terraform, Docker, CI/CD, SRE, and LLMOps. Plus the hands-on tutorial repos I maintain at beCloudReady.

There's a lot of AI-generated DevOps content out there now. The point of this list is the opposite: a short, opinionated set of links to material from the people who actually build the tools — Linux Foundation, AWS, CNCF, HashiCorp, Google, Anthropic, NVIDIA — and the order I'd read them in.

If it helps, ⭐ the repo so others can find it.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## Contents

- [Linux, Networking & Shell](#linux-networking--shell)
- [Git & GitHub](#git--github)
- [Cloud (AWS, Azure, GCP)](#cloud-aws-azure-gcp)
- [Docker & Containers](#docker--containers)
- [Kubernetes & EKS](#kubernetes--eks)
- [Terraform, Pulumi & Ansible (IaC)](#terraform-pulumi--ansible-iac)
- [CI/CD — GitHub Actions & Jenkins](#cicd--github-actions--jenkins)
- [SRE & Observability](#sre--observability)
- [Data Engineering](#data-engineering)
- [AI Platform Engineering & LLMOps](#ai-platform-engineering--llmops)
- [Interview Prep](#interview-prep)
- [Bootcamp & Webinar](#bootcamp--webinar)

---

## Linux, Networking & Shell

Linux fluency is the floor for any DevOps role.

**Official / free:**
- [Introduction to Linux (LFS101)](https://training.linuxfoundation.org/training/introduction-to-linux/) — Linux Foundation, free on edX
- [Red Hat Enterprise Linux Technical Overview (RH024)](https://www.redhat.com/en/services/training/rh024-red-hat-linux-technical-overview) — free, vendor-authoritative
- [Linux man-pages (HTML)](https://man7.org/linux/man-pages/) — Michael Kerrisk's maintained reference
- [GNU Bash Reference Manual](https://www.gnu.org/software/bash/manual/bash.html)
- [Advanced Bash-Scripting Guide (TLDP)](https://tldp.org/LDP/abs/html/)
- [Cisco Networking Basics](https://www.netacad.com/courses/networking-basics) — free with Packet Tracer simulator
- [Stanford CS144 — Computer Networking](https://cs144.github.io/) · [YT lectures](https://www.youtube.com/playlist?list=PLvFG2xYBrYAQCyz4Wx3NPoYJOFjvU7g2Z)
- [systemd documentation](https://systemd.io/)
- [OpenSSH manuals](https://www.openssh.org/manual.html)

**My tutorials:**
- [bash-tutorials](https://github.com/becloudready/bash-tutorials)
- [ansible-tutorials](https://github.com/becloudready/ansible-tutorials)

---

## Git & GitHub

**Official / free:**
- [Pro Git book (2nd ed.)](https://git-scm.com/book/en/v2) — Chacon & Straub, free online
- [Git reference docs](https://git-scm.com/docs)
- [GitHub Skills](https://skills.github.com/) — interactive in-repo courses
- [GitHub Docs — Get Started](https://docs.github.com/en/get-started)
- [GitHub Actions documentation](https://docs.github.com/en/actions)
- [Atlassian Git tutorials](https://www.atlassian.com/git/tutorials) — best diagrams for workflows
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [Semantic Versioning](https://semver.org/)

**My tutorials:**
- [git-tutorials](https://github.com/becloudready/git-tutorials)
- [python-tutorials](https://github.com/becloudready/python-tutorials)
- [php-tutorials](https://github.com/becloudready/php-tutorials)
- Project examples: [tldr-today](https://github.com/becloudready/tldr-today) · [my_yelp_reviews](https://github.com/becloudready/my_yelp_reviews) · [cloud-sentiment-analysis](https://github.com/becloudready/cloud-sentiment-analysis)

---

## Cloud (AWS, Azure, GCP)

I teach AWS-first because that's where the jobs are. Pick up Azure/GCP after.

### AWS

- [AWS Cloud Practitioner Essentials](https://skillbuilder.aws/learn/94T2BEN85A/aws-cloud-practitioner-essentials/9SSAGGQQ12) — free on Skill Builder, the starting point
- [AWS Technical Essentials](https://skillbuilder.aws/learn/A8RGTRTGE2/aws-technical-essentials/JGW7HKGGUM) — deeper EC2 / VPC / IAM / RDS / S3 / Lambda intro
- [Getting Started with DevOps on AWS](https://skillbuilder.aws) — search the title
- [AWS Cloud Quest: Cloud Practitioner](https://skillbuilder.aws/learn/FU5WCYVGKY/aws-cloud-quest-cloud-practitioner/JF9TKU68GT) — free hands-on labs (gamified)
- [Solutions Architect Knowledge Badge Readiness Path](https://skillbuilder.aws) — free SA-Associate-depth path
- [AWS Hands-On Tutorials](https://aws.amazon.com/getting-started/hands-on/) — short, service-by-service
- [AWS Workshops (Builder Center)](https://builder.aws.com/build/workshops) — multi-hour scenario labs
- [EKS Terraform Workshop](https://tf-eks-workshop.workshop.aws/)
- [Well-Architected Labs](https://www.wellarchitectedlabs.com/)
- Core docs: [EC2](https://docs.aws.amazon.com/ec2/) · [VPC](https://docs.aws.amazon.com/vpc/) · [IAM](https://docs.aws.amazon.com/iam/) · [S3](https://docs.aws.amazon.com/s3/)
- [AWS Events YouTube](https://www.youtube.com/@AWSEventsChannel) — re:Invent DevOps sessions (DOP201, DOP202, DOP324)

### Azure

- [AZ-400 — Designing & Implementing Microsoft DevOps Solutions](https://learn.microsoft.com/en-us/credentials/certifications/devops-engineer/) · [study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-400)
- [Introduction to Kubernetes on Azure](https://learn.microsoft.com/en-us/training/paths/intro-to-kubernetes-on-azure/) · [Deploy with AKS (AZ-1001)](https://learn.microsoft.com/en-us/training/paths/deploy-manage-containers-azure-kubernetes-service/)

### GCP

- [Google Cloud Fundamentals: Core Infrastructure](https://www.skills.google/course_templates/60)
- [Professional Cloud DevOps Engineer Learning Path](https://www.skills.google/paths/20)

**My tutorials:**
- [quick-labs](https://github.com/becloudready/quick-labs) — fast cloud instance launchers

---

## Docker & Containers

**Official / free:**
- [Docker — Get Started](https://docs.docker.com/get-started/)
- [Docker reference docs](https://docs.docker.com/reference/)
- [Multi-stage builds](https://docs.docker.com/build/building/multi-stage/)
- [BuildKit](https://docs.docker.com/build/buildkit/)
- [Docker Engine security](https://docs.docker.com/engine/security/)
- [NIST SP 800-190 — Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
- [OWASP Docker Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Docker_Security_Cheat_Sheet.html)
- [Docker YouTube](https://www.youtube.com/@DockerIo)

> Note: Play with Docker shuts down March 1, 2026 — use Docker Desktop or Codespaces.

**My tutorials:**
- [docker-tutorials](https://github.com/becloudready/docker-tutorials)

---

## Kubernetes & EKS

**Official / free:**
- [Learn Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/) — interactive, runs Minikube in browser
- [Kubernetes Tutorials hub](https://kubernetes.io/docs/tutorials/)
- [Introduction to Kubernetes (LFS158)](https://www.edx.org/learn/kubernetes/the-linux-foundation-introduction-to-kubernetes) — CNCF-authored, free audit on edX
- [Kubernetes The Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way) — Kelsey Hightower; still the best way to understand internals
- [Killercoda](https://killercoda.com/playgrounds/scenario/kubernetes) · [Killer Shell CKA](https://killercoda.com/killer-shell-cka)
- [EKS Workshop](https://www.eksworkshop.com/)
- [Helm docs](https://helm.sh/docs/intro/quickstart/)
- [Argo CD — Getting Started](https://argo-cd.readthedocs.io/en/stable/getting_started/)
- [CNCF certification curricula (CKA/CKAD/CKS/KCNA)](https://github.com/cncf/curriculum)
- [CNCF YouTube — KubeCon recordings](https://www.youtube.com/@cncf)

**My tutorials:**
- [kubernetes-tutorials](https://github.com/becloudready/kubernetes-tutorials)

---

## Terraform, Pulumi & Ansible (IaC)

### Terraform

- [HashiCorp Developer — Terraform tutorials](https://developer.hashicorp.com/terraform/tutorials)
- [Terraform Get Started — AWS](https://developer.hashicorp.com/terraform/tutorials/aws-get-started)
- [Terraform Associate (004) prep](https://developer.hashicorp.com/terraform/tutorials/certification-associate-tutorials) — current exam version
- [Terraform Registry](https://registry.terraform.io/)
- [Checkov](https://www.checkov.io/) — IaC security scanner
- [Trivy](https://trivy.dev/) — `tfsec` was merged into Trivy in 2024, use this

### Pulumi

- [Pulumi Learn](https://www.pulumi.com/learn/) · [Tutorials](https://www.pulumi.com/tutorials/)
- [Pulumi vs Terraform](https://www.pulumi.com/docs/iac/concepts/vs/terraform/)

### Ansible

- [Ansible — Getting Started](https://docs.ansible.com/ansible/latest/getting_started/index.html)
- [Ansible documentation](https://docs.ansible.com/)
- [Red Hat Learning Subscription free trial](https://www.redhat.com/en/services/training/learning-subscription) — includes Ansible Basics
- [AWX](https://github.com/ansible/awx) — open-source upstream of Ansible Automation Platform

**My tutorials:**
- [terraform-tutorials](https://github.com/becloudready/terraform-tutorials)
- [pulumi-tutorials](https://github.com/becloudready/pulumi-tutorials)
- [ansible-tutorials](https://github.com/becloudready/ansible-tutorials)

---

## CI/CD — GitHub Actions & Jenkins

- [GitHub Actions documentation](https://docs.github.com/en/actions) · [Quickstart](https://docs.github.com/en/actions/get-started/quickstart)
- [GitHub Skills](https://github.com/skills) — interactive courses
- [GitHub Actions Marketplace](https://github.com/marketplace?type=actions)
- [Jenkins tutorials](https://www.jenkins.io/doc/tutorials/) · [Pipeline — Getting Started](https://www.jenkins.io/doc/book/pipeline/getting-started/)
- [GitLab CI/CD Quick Start](https://docs.gitlab.com/ee/ci/quick_start/)
- [CircleCI Quickstart](https://circleci.com/docs/getting-started/)
- [OWASP DevSecOps Guideline](https://owasp.org/www-project-devsecops-guideline/)
- [Snyk Learn](https://learn.snyk.io/) — free security lessons
- [DORA — DevOps Research & Assessment](https://dora.dev/) — the four key metrics + Quick Check

---

## SRE & Observability

- [Site Reliability Engineering (Google SRE book)](https://sre.google/sre-book/table-of-contents/) — free online
- [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) — free
- [Building Secure & Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html) — free
- [Google Cloud DevOps Engineer Professional Certificate (Coursera)](https://www.coursera.org/professional-certificates/sre-devops-engineer-google-cloud) — audit free
- [LFS162 — Intro to DevOps and SRE](https://training.linuxfoundation.org/training/introduction-to-devops-and-site-reliability-engineering-lfs162/) — free, Linux Foundation
- [Prometheus — First Steps](https://prometheus.io/docs/introduction/first_steps/)
- [Grafana Labs tutorials](https://grafana.com/tutorials/)
- [OpenTelemetry documentation](https://opentelemetry.io/docs/) — the vendor-neutral standard worth learning
- [Datadog Learning Center](https://learn.datadoghq.com/)
- [Observability Engineering (Honeycomb, free O'Reilly PDF)](https://info.honeycomb.io/observability-engineering-oreilly-book-2022)
- [PagerDuty Incident Response](https://response.pagerduty.com/) — open-sourced internal runbook

---

## Data Engineering

- [Databricks Lakehouse Fundamentals](https://www.databricks.com/learn/training/lakehouse-fundamentals) — free + badge
- [Databricks Spark Associate Developer — Exam Guide](https://www.databricks.com/learn/certification/apache-spark-developer-associate)
- [Apache Spark programming guides](https://spark.apache.org/docs/latest/)
- [Snowflake University — Hands-On Essentials](https://learn.snowflake.com/en/pages/hands-on-essentials-track/)
- [PostgreSQL Tutorial](https://www.postgresql.org/docs/current/tutorial.html)
- [Elastic free training](https://www.elastic.co/training/free) · [Elasticsearch reference](https://www.elastic.co/guide/en/elasticsearch/reference/current/)
- [Confluent Developer — Kafka courses](https://developer.confluent.io/courses/)
- [Apache Airflow tutorials](https://airflow.apache.org/docs/apache-airflow/stable/tutorial/index.html)
- [dbt Learn](https://learn.getdbt.com/catalog)

**My tutorials:**
- [snowflake-tutorials](https://github.com/becloudready/snowflake-tutorials)
- [azure-databricks-terraform](https://github.com/kchandan/azure-databricks-terraform)
- [es-tutorials](https://github.com/becloudready/es-tutorials)
- [datascience-tutorials](https://github.com/becloudready/datascience-tutorials)
- [pgsql-tutorials](https://github.com/becloudready/pgsql-tutorials)

---

## AI Platform Engineering & LLMOps

Where DevOps is heading.

- [NVIDIA DLI — Building RAG Agents with LLMs](https://learn.nvidia.com/courses/course-detail?course_id=course-v1%3ADLI+S-FX-15+V1) · [DLI catalog](https://courses.nvidia.com/)
- [Hugging Face Learn](https://huggingface.co/learn) — LLM, Agents, Deep RL, Audio, Diffusion courses
- [DeepLearning.AI short courses](https://learn.deeplearning.ai/) — co-built with Anthropic, OpenAI, LangChain
- [Anthropic Claude docs](https://docs.claude.com/) · [Prompt engineering](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview)
- [OpenAI Cookbook](https://cookbook.openai.com/) · [GitHub](https://github.com/openai/openai-cookbook)
- [LangChain (Python) docs](https://docs.langchain.com/oss/python/langchain/overview)
- [LlamaIndex docs](https://developers.llamaindex.ai/python/framework/)
- [Weights & Biases free courses](https://wandb.ai/site/courses/)
- [Made With ML — Goku Mohandas](https://madewithml.com/)
- K8s-native serving: [Kubeflow](https://www.kubeflow.org/docs/) · [KServe](https://kserve.github.io/website/) · [vLLM](https://docs.vllm.ai/en/latest/) · [NVIDIA Triton](https://docs.nvidia.com/deeplearning/triton-inference-server/user-guide/docs/index.html)

---

## Interview Prep

- [k8s-interview-action](https://github.com/becloudready/k8s-interview-action) — Kubernetes scenarios as GitHub Action challenges
- [interview-challenges](https://github.com/becloudready/interview-challenges) — general DevOps/cloud interview practice

---

## Bootcamp & Webinar

Working through this list on your own is doable. If you'd rather have someone walk you through it live, fix your mistakes in real time, and review your capstone — that's what I run the bootcamp for.

- **Free webinar — "Become a Cloud & DevOps Engineer"** · June 10, 2026 · 5:30 PM EDT → [becloudready.com/webinar/devops](https://becloudready.com/webinar/devops)
- **Cloud & DevOps Bootcamp** · 5 days live · starts June 15, 2026 · CAD $299 → [becloudready.com/programs/cloud-devops-bootcamp](https://becloudready.com/programs/cloud-devops-bootcamp)

Webinar attendees get $50 off the bootcamp.

---

## Contributing

If a link is broken or you know a better official resource for one of the topics, open a PR. I'm intentionally keeping this short, so the bar for a new link is "better than what's already here," not "another decent option."

— Chandan Kumar, [beCloudReady](https://becloudready.com)
