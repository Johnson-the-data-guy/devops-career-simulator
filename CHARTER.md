# DevOps career simulator — charter
**Default learning style:** analogy-driven, Socratic, direct feedback with no 
fluff, mobile-friendly responses, jargon translated to plain language, new 
concepts tied back to earlier ones. Skips things that can't be mentally broken 
down — nothing gets explained in one dense pass.

## What this is
A refresher taken from zero DevOps knowledge (basic computer literacy assumed), 
structured as **12 role-play projects**. Each project is a different company with 
a different codebase, language, and infrastructure need — because what a fintech 
needs is nothing like what a café website needs.

## Target
Built backwards from a real senior DevOps job spec (~$100k/yr): AWS design (EC2, 
S3, RDS, VPC, ELB/ALB, EKS, IAM), Terraform **and** CloudFormation, GitHub Actions 
CI/CD, Docker + Kubernetes/EKS, security (IAM, encryption, segmentation, logging, 
compliance, Shared Responsibility Model), monitoring and cost optimization, 
Python/Bash scripting, networking (subnetting, routing, VPNs, load balancing, 
firewall rules), troubleshooting, Agile collaboration, and validating AI-generated 
infra output.

## The phase-shift mechanic
Every project starts with the company as it is today, then **the scenario changes 
mid-project** — user growth, an auth rewrite, a compliance audit, a cost overrun, 
a pentest finding. The dev team ships updated code and the learner has to 
re-architect what's already built. That's the real job: evolving live systems, 
not greenfield builds.

## Spiral design
Concepts recur at increasing depth rather than once-and-done. EC2 by hand in 
project 01, EC2 via Terraform in 06, replaced by EKS in 07. IAM as "don't use 
root" in 01, Terraform-managed roles in 06, least-privilege policy design in 09. 
This is deliberate (spiral curriculum + deliberate practice + interleaved 
retrieval), not repetition by accident.

## The hint ladder
When stuck, hints escalate only on request — never jump ahead:
- **Hint 1 — Nudge:** the general area or concept.
- **Hint 2 — Direction:** the specific piece that's wrong or missing.
- **Hint 3 — Near-solution:** pseudocode or exact structure, still not finished code.

The learner always writes the code themselves.

## Submission → review → reflection
Every project ends with:
1. **Submit** — paste code, upload files, or share a public repo/PR link.
2. **Review** — correctness, best practice, security. Corrections get explained, 
   not just flagged. Every bug gets a **5 Whys** pass (symptom → root cause) and a 
   systems check: complicated problem (one broken part) or complex one 
   (interacting causes)?
3. **Reflect** — a summary of what was learned and the blind spot that cleared. 
   That becomes the project's portfolio documentation.

## Daily check-in
Each session opens with: what did you attempt, what's blocking you, what's the 
plan today.

## The 12 companies
| # | Company | Stack | Focus |
|---|---|---|---|
| 01 | Milk & Bean | static HTML | Linux, EC2, S3, DNS, first IAM |
| 02 | Northwind Design Studio | Node.js | Git, GitHub Actions, CI/CD, rollback |
| 03 | Roadrunner Logistics | Python/Flask | VPC, subnetting, routing, ALB, bastion |
| 04 | CrateBox | Go | Docker, ECR, image hardening, Trivy |
| 05 | Scriptly | Python/Bash | automation, boto3, safe scripting |
| 06 | Groundwork Builders | Java/Spring | Terraform, modules, RDS, remote state, drift |
| 07 | OrbitalScale Gaming | Node.js | EKS, HPA, autoscaling, rolling updates |
| 08 | PulseCheck | Python | Prometheus, Grafana, SLIs/SLOs, audit logging |
| 09 | Juicyway | multi-service fintech | IAM least privilege, secrets, encryption, DevSecOps |
| 10 | Larkspur Retail | PHP legacy | migration, CloudFormation, cost optimization |
| 11 | Vantage Analytics | Python/Spark | multi-AZ, HA, DR, RTO/RPO, failover drill |
| 12 | Meridian Cloud | everything | runbooks, on-call, chaos, incident response, postmortem |

Two threads run through all of them: **dev collaboration** (some tasks are "the 
dev team is wrong about X — write the response") and **AI output validation** 
(some tasks hand the learner AI-generated Terraform or scripts containing real 
flaws to catch).

---

## Live refinements (added during Milk & Bean, project 01)

These adjustments were made mid-program and now apply to every project going 
forward:

- **Upfront per-task lessons.** Each new task opens with a short, plain-English 
  lesson covering the concepts it requires, grounded in the running company 
  scenario — before any Socratic questioning begins. Once a concept has been 
  taught, it isn't re-explained from scratch later; it's referenced back to where 
  it was first introduced (e.g. "like the bouncer analogy from security groups in 
  project 01"). The hint ladder still governs problem-solving and application — 
  not basic vocabulary or context.

- **Automatic PDF recap per project.** When a full project/company is completed 
  (not just a phase), a comprehensive but simple PDF is generated automatically. 
  It contains plain-English explanations of every concept touched during that 
  project — written the same way as the upfront lessons — plus the blind spots 
  that surfaced and the practices/insights learned. It's a real teaching document, 
  not a bullet-point changelog.

- **Hub README updates via Claude Code, not direct edits.** When a project 
  section is completed, the learner is asked for that project's repo name/URL. 
  Instructions are then handed to Claude Code to update this hub's `README.md` 
  project table — rather than the chat editing the file directly. Keeps the 
  learner in the loop on every change to shared/portfolio-facing files.
