# George Dawson-Kesson

**DevOps Engineer** — AWS SAA-C03 · Terraform · Kubernetes/EKS · ArgoCD · Kyverno · Istio

I came into infrastructure through enterprise sales and Linux administration. That background means I think about reliability and cost in terms real businesses care about, not just uptime numbers.

Currently based in Cincinnati, OH. Open to DevOps, Platform Engineering, and SRE roles — US remote or hybrid.

---

## What I Build

I build production-grade platforms, not tutorials. Everything below has been deployed live on AWS, verified, and documented honestly — including what broke and why.

---

## Featured Projects

### [eks-infra-automation](https://github.com/gdawsonkesson/eks-infra-automation) — Platform Layer
> Production-grade EKS platform · v2.0.0

Full Kubernetes platform on AWS built with Terraform. Deployed, verified live, and torn down cleanly via automated pipeline.

- EKS 1.33 · VPC · KMS encryption · OIDC-based IAM · zero stored credentials
- Istio 1.26.2 service mesh · VirtualService routing · fault injection runbooks
- ArgoCD v3.1.0 · GitOps delivery · Online Boutique synced Healthy
- Kyverno 3.2.6 · 5 ClusterPolicies enforcing pod security at admission time
- kube-prometheus-stack · Prometheus · Grafana · AlertManager · Slack routing
- External Secrets Operator · AWS Secrets Manager via IRSA
- GitHub Actions CI/CD · tfsec + Trivy · three-phase apply · OIDC auth

**Verified live:** 3 nodes Ready · 11 microservices Running · ArgoCD Synced + Healthy · all green in 3m 41s

---

### [online-boutique-gitops](https://github.com/gdawsonkesson/online-boutique-gitops) — Delivery Layer
> Kustomize overlays · ArgoCD · dev/staging/prod

GitOps repository for the Online Boutique microservices application. ArgoCD watches this repo and syncs changes to the cluster automatically. Separate from the platform repo by design — application teams own deployments, platform teams own the cluster.

- Kustomize base + overlays for dev, staging, and prod environments
- HPA and PodDisruptionBudgets per service
- Default-deny NetworkPolicies with explicit allow rules
- ExternalSecret pulling Stripe API key from AWS Secrets Manager at runtime

---

### [online-boutique-application](https://github.com/gdawsonkesson/online-boutique-application) — Build Layer
> Source code · Dockerfiles · CI pipelines · Docker Hub

Source code and CI pipelines for 11 microservices written in Go, Python, Node.js, Java, and C#. Images built, scanned with Trivy, and pushed to Docker Hub. The productcatalogservice pipeline fires a repository_dispatch to the GitOps repo on every merge — updating the Kustomize image tag automatically.

- Bulk build workflow for 9 services on every push
- Dedicated pipeline for productcatalogservice: build, test, lint, scan, dispatch
- No latest tags ever — Kyverno enforces this on the cluster

---

### [aws-serverless-platform](https://github.com/gdawsonkesson/aws-serverless-platform) — Live Serverless Platform
> Live at [gdawsonkesson.com](https://gdawsonkesson.com)

Production serverless platform provisioned entirely with Terraform. Running live with zero infrastructure cost.

- AWS Lambda · API Gateway · DynamoDB · CloudFront · S3 · Route 53 · ACM
- GitHub Actions CI/CD · automated deployment on every push to main
- $0/month infrastructure cost

---

## Core Stack

![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Terraform](https://img.shields.io/badge/terraform-%235835CC.svg?style=for-the-badge&logo=terraform&logoColor=white)
![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=Prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/grafana-%23F46800.svg?style=for-the-badge&logo=grafana&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Shell Script](https://img.shields.io/badge/shell_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)

---

## GitHub Stats

![](https://github-readme-stats.vercel.app/api?username=gdawsonkesson&theme=dark&hide_border=false&include_all_commits=true&count_private=false)
![](https://github-readme-streak-stats.herokuapp.com/?user=gdawsonkesson&theme=dark&hide_border=false)

---

## Connect

[![Portfolio](https://img.shields.io/badge/Portfolio-gdawsonkesson.com-blue?style=flat-square)](https://gdawsonkesson.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-gdawsonkesson-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/gdawsonkesson)
[![AWS Certified](https://img.shields.io/badge/AWS-Certified%20Solutions%20Architect%20Associate-FF9900?style=flat-square&logo=amazon-aws)](https://aws.amazon.com/certification/)
