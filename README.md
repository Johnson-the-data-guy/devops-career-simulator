# DevOps Career Simulator

A 15-project, role-play learning path for going from zero DevOps knowledge to a
senior-level skillset — AWS, Terraform/CloudFormation, CI/CD, Docker/Kubernetes,
security, monitoring, and cost optimization. Each project is a different fictional
company, and each one changes shape mid-build (a growth spike, a pentest finding,
a cost overrun), so it's not just "build once" — it's "build, then adapt what you
already shipped," which is the actual job.

Learning philosophy, hint-ladder rules, and the full charter: see
[`CHARTER.md`](./CHARTER.md).

## How this repo works

This repo is the **hub** — it holds the shared curriculum docs and the progress
tracker. Each individual company gets its own separate repo (real infrastructure,
real code, built from scratch), linked below once work on it has started.

| # | Company | Repo | Live |
|---|---|---|---|
| 01 | Milk & Bean | [milk-and-bean-infra](https://github.com/Johnson-the-data-guy/milk-and-bean-infra) | offline (AWS account closed) |
| 02 | Northwind Design Studio | [northwind](https://github.com/Johnson-the-data-guy/northwind) | [northwind-design.online](https://northwind-design.online) |

All 15 companies and live progress: [tracker](<TRACKER_URL>)

## Progress tracker

A live, read-only tracker is hosted at <TRACKER_URL>. It's served by Cloudflare
Pages from the files in [`tracker/`](./tracker/) and updated daily.

## What you need set up to work through this

- **WSL** (or any Linux-capable terminal) + **VS Code**
- **Claude Code**, connected to your terminal, with GitHub access to your project
  repos — this is the *execution layer*: it runs commands against real
  infrastructure, generates non-graded scaffolding (like placeholder site content),
  and helps navigate the codebase.
- **`CLAUDE.md`** in each project repo — guardrails for Claude Code so it explains
  errors and suggests fixes without silently rewriting whole configs or resource
  blocks. Keeps you in the driver's seat on live infra changes.
- **Hosting** — currently a **$4/month DigitalOcean VPS**, because AWS access is
  paused. An **AWS account** (EC2, VPC, S3, IAM, etc.) comes back in later
  projects.
- This ongoing **Claude.ai conversation** — handles the Socratic teaching, hint
  ladder, code review, and reflection. Distinct role from Claude Code: this is
  where you *think*, Claude Code is where things *run*.


Full detail on all of the above lives in
[`CHARTER.md`](./CHARTER.md).