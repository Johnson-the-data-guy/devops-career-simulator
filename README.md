# DevOps Career Simulator

A 12-project, role-play learning path for going from zero DevOps knowledge to a
senior-level skillset — AWS, Terraform/CloudFormation, CI/CD, Docker/Kubernetes,
security, monitoring, and cost optimization. Each project is a different fictional
company, and each one changes shape mid-build (a growth spike, a pentest finding,
a cost overrun), so it's not just "build once" — it's "build, then adapt what you
already shipped," which is the actual job.

Full breakdown of all 12 companies and their tasks: see
[`PROJECTS.md`](./PROJECTS.md).

Learning philosophy, hint-ladder rules, and the full charter: see
[`CHARTER.md`](./CHARTER.md).

## How this repo works

This repo is the **hub** — it holds the shared curriculum docs and the progress
tracker. Each individual company gets its own separate repo (real infrastructure,
real code, built from scratch), linked below as each one is completed.

| # | Company | Repo |
|---|---|---|
| 01 | Milk & Bean | [`milk-and-bean-infra`](https://github.com/Johnson-the-data-guy/milk-and-bean-infra) |
| 02 | Northwind Design Studio | _not started_ |
| 03 | Roadrunner Logistics | _not started_ |
| 04 | CrateBox | _not started_ |
| 05 | Scriptly | _not started_ |
| 06 | Groundwork Builders | _not started_ |
| 07 | OrbitalScale Gaming | _not started_ |
| 08 | PulseCheck | _not started_ |
| 09 | Juicyway | _not started_ |
| 10 | Larkspur Retail | _not started_ |
| 11 | Vantage Analytics | _not started_ |
| 12 | Meridian Cloud | _not started_ |

## Progress tracker

[`progress-tracker.html`](./progress-tracker.html) is an interactive
checklist covering all 12 projects and every task inside them.

**Important — how to actually use it:** this file uses browser-based storage to
remember which boxes you've checked. That storage only works when the file is
opened as a **live Claude artifact inside a chat conversation** — not when it's
opened directly as a local file (e.g. double-clicked from Downloads, or opened via
`file://` in a browser). Opening it locally will still let you *click* the boxes,
but nothing will be saved once you close the tab.

**To use it properly:**
1. Open a Claude.ai conversation (ideally the ongoing simulator conversation).
2. Have Claude load `progress-tracker.html` from this repo/project files.
3. It renders as an interactive artifact in the chat — check boxes there, and
   progress persists across that conversation.

Treat the raw `.html` file in this repo as the source of truth for the *content*
(tasks, phases, structure) — not as a personal tracker you open standalone.

## What you need set up to work through this

- **WSL** (or any Linux-capable terminal) + **VS Code**
- **Claude Code**, connected to your terminal, with GitHub access to your project
  repos — this is the *execution layer*: it runs commands against real
  infrastructure, generates non-graded scaffolding (like placeholder site content),
  and helps navigate the codebase.
- **`CLAUDE.md`** in each project repo — guardrails for Claude Code so it explains
  errors and suggests fixes without silently rewriting whole configs or resource
  blocks. Keeps you in the driver's seat on live infra changes.
- An **AWS account** (free tier covers almost everything here) for EC2, VPC, S3,
  IAM, etc.
- This ongoing **Claude.ai conversation** — handles the Socratic teaching, hint
  ladder, code review, and reflection. Distinct role from Claude Code: this is
  where you *think*, Claude Code is where things *run*.

## The rules, briefly

- **Hint ladder** — stuck? Ask for a hint, it escalates (nudge → direction →
  near-solution). Code is always written by you, never handed to you.
- **No skipping hands-on steps.** Terminal commands against live infrastructure
  aren't something Claude Code does *for* you — that's the actual skill being
  trained.
- **Submit → review → reflect** closes every project: README, review, and a
  written blind-spot summary become that project's portfolio documentation.

Full detail on all of the above lives in
[`CHARTER.md`](./CHARTER.md).