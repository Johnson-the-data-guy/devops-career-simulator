# DevOps career simulator

Twelve companies. Twelve different stacks. One engineer.

This repo documents a self-directed DevOps program built backwards from a senior AWS DevOps job specification. Each folder is a role-play: I act as the DevOps engineer for a fictional company, build their infrastructure, then handle a **phase shift** — a mid-project scenario change (traffic growth, a security audit, a cost overrun, a production incident) that forces me to re-architect what I just built.

The phase shift is the point. Greenfield builds are the easy half of the job.

## The companies

| # | Company | Stack | Focus |
|---|---|---|---|
| 01 | Milk & Bean | static HTML | Linux, EC2, S3, DNS, IAM |
| 02 | Northwind Design Studio | Node.js | Git, GitHub Actions, CI/CD, rollback |
| 03 | Roadrunner Logistics | Python/Flask | VPC, subnetting, routing, ALB |
| 04 | CrateBox | Go | Docker, ECR, image hardening |
| 05 | Scriptly | Python · Bash | automation, boto3 |
| 06 | Groundwork Builders | Java/Spring | Terraform, modules, RDS |
| 07 | OrbitalScale Gaming | Node.js | EKS, autoscaling |
| 08 | PulseCheck | Python | Prometheus, Grafana, SLOs |
| 09 | Juicyway | multi-service fintech | IAM, secrets, encryption, DevSecOps |
| 10 | Larkspur Retail | PHP legacy | migration, CloudFormation, cost |
| 11 | Vantage Analytics | Python/Spark | multi-AZ, HA, DR |
| 12 | Meridian Cloud | everything | incident response, chaos, postmortems |

## Skills covered

**Cloud** — EC2, S3, RDS, VPC, ELB/ALB, EKS, IAM, CloudTrail, CloudFront
**IaC** — Terraform (modules, remote state, drift detection) and CloudFormation
**CI/CD** — GitHub Actions, staging environments, rollback strategies, branch protection
**Containers** — Docker, multi-stage builds, ECR, Kubernetes/EKS, autoscaling
**Security** — IAM least privilege, Secrets Manager, encryption, network segmentation, SAST/SCA/secret scanning, Shared Responsibility Model
**Observability** — Prometheus, Grafana, SLIs/SLOs, error budgets, centralized logging
**Reliability** — multi-AZ, disaster recovery, RTO/RPO, chaos engineering, incident response, blameless postmortems
**Scripting** — Python (boto3), Bash
**Networking** — subnetting, CIDR, routing, NAT, load balancing, firewall rules, bastion hosts

Two threads run through every project: collaborating with (and pushing back on) developers, and validating AI-generated infrastructure code for security and correctness.

## Structure

Each company folder contains the working infrastructure code and a README covering the brief, what was built, key decisions, what breaks without it, the phase shift, and the blind spot that cleared.

Full task breakdown and current progress: [PROJECTS.md](./PROJECTS.md)
