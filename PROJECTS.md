# DevOps career simulator — full project breakdown

Twelve companies. Each has phases; the **shift** phases are where the scenario changes and you re-architect what you already built. The `concept` tag under each task is what you're actually learning.

Progress marker: update the line below as you go.

> **Currently on:** 01 Milk & Bean · phase_1 · task 1

---

## 01 — Milk & Bean
`static HTML · café website`
The owner has a site on a USB stick and no idea what hosting means. Get it online.

**phase_1 — Get it online**
- [ ] Explain, in your own words, what a server actually is and why the café needs one — `client-server model`
- [ ] Launch your first EC2 instance and SSH into it — `EC2 · SSH`
- [ ] Install nginx, deploy the static site, load it in a browser — `Linux · nginx`
- [ ] Point a domain at it; explain what happens between typing the URL and the page loading — `DNS · Route 53`

**phase_2 (shift) — "It's slow abroad and the bill is scary"**
- [ ] Move static assets to S3; explain why that's cheaper than an always-on EC2 — `S3 · static hosting`
- [ ] Put a CDN in front; test load time before and after — `CDN · CloudFront`
- [ ] You've been using the root user this whole time. Fix that — and say why it mattered — `IAM basics`
- [ ] Right-size the instance; show before/after monthly cost — `cost awareness`

**submit** — README (what you built, why each piece exists, what breaks without it) → review → blind-spot summary

---

## 02 — Northwind Design Studio
`Node.js · creative agency`
Three designers, one dev, deploys done by dragging files over FTP. Something breaks weekly.

**phase_1 — Stop the manual deploys**
- [ ] Set up a branching model; explain trunk-based vs git-flow for a team this size — `git branching`
- [ ] First GitHub Actions workflow: install deps, run tests, on every push — `GitHub Actions`
- [ ] Extend it to auto-deploy to EC2 on merge to main — `CI/CD`
- [ ] Get credentials out of the workflow file and into GitHub secrets — `secrets in CI`

**phase_2 (shift) — "A bad deploy took us down for 3 hours"**
- [ ] Add a staging environment mirroring production — `environments`
- [ ] Design and implement a rollback path; prove it works — `rollback`
- [ ] Require passing checks before merge; nobody pushes to main — `branch protection`
- [ ] The lead dev wants to bypass staging "just for hotfixes." Write your response — `collaboration`

**submit** — README + pipeline diagram → review → blind-spot summary

---

## 03 — Roadrunner Logistics
`Python/Flask · delivery startup`
Everything sits in one public subnet, database included. Their auditor noticed.

**phase_1 — Build a real network**
- [ ] Subnet 10.0.0.0/16 by hand on paper before touching AWS; show your math — `CIDR · subnetting`
- [ ] Build the VPC: two public subnets, two private, across two AZs — `VPC`
- [ ] Wire route tables, IGW, NAT gateway; explain the traffic path for each — `routing · IGW · NAT`
- [ ] ALB in public, app servers in private; confirm the app is unreachable directly — `ALB`

**phase_2 (shift) — "Depot staff need access from the warehouse"**
- [ ] Security groups vs NACLs — explain the difference, implement the right one — `security groups · NACLs`
- [ ] Give ops secure admin access without exposing SSH to the internet — `bastion · VPN`
- [ ] I break the routing; you diagnose it with commands, not guesses — `troubleshooting`

**submit** — README + network diagram → review → blind-spot summary

---

## 04 — CrateBox
`Go · shipping platform`
"Works on my machine" is now a company-wide crisis. Two environments, three Go versions.

**phase_1 — Containerize it**
- [ ] Explain images vs containers vs layers before writing a Dockerfile — `docker fundamentals`
- [ ] Write a working Dockerfile for the Go app; run it locally — `Dockerfile`
- [ ] Push to ECR and pull it onto a server — `ECR`

**phase_2 (shift) — "Images are 1.2GB and security found a CVE"**
- [ ] Get the image under 50MB; explain what you removed and why it was there — `multi-stage builds`
- [ ] Scan it; fix what's fixable, document what isn't — `Trivy · image scanning`
- [ ] Stop running as root inside the container; explain the attack this prevents — `container hardening`
- [ ] I give you an AI-generated Dockerfile with real flaws. Find them — `AI validation`

**submit** — README + before/after size and scan results → review → blind-spot summary

---

## 05 — Scriptly
`Python · Bash · ops-heavy SaaS`
Four engineers spend their mornings doing the same manual checks. You're here to delete that work.

**phase_1 — Automate the morning routine**
- [ ] Bash script: clean old logs, report disk usage — `bash scripting`
- [ ] Python: inventory every EC2 instance with state, type, tags — `boto3 · sessions`
- [ ] Make it survive an API failure gracefully instead of crashing halfway — `error handling`

**phase_2 (shift) — "We're paying for resources nobody owns"**
- [ ] Find and report every untagged or idle resource — `automation · tagging`
- [ ] Run it automatically — cron or Lambda; justify your pick — `scheduled jobs`
- [ ] Add a dry-run mode; explain why a deleting script needs one — `safe automation`
- [ ] I hand you an AI-written cleanup script with a destructive bug. Catch it — `AI validation`

**submit** — README + sample output → review → blind-spot summary

---

## 06 — Groundwork Builders
`Java/Spring · construction SaaS`
Everything was built by clicking in the console. The person who built it left. Nobody knows what exists.

**phase_1 — Codify the infrastructure**
- [ ] Providers, resources, state — explain what state actually is before writing HCL — `terraform basics`
- [ ] Reproduce the project 03 network entirely in Terraform — `terraform · VPC/EC2`
- [ ] Add a managed database; explain why not self-hosted MySQL on EC2 — `RDS`
- [ ] Move state to S3 with locking; explain what breaks without the lock — `remote state`

**phase_2 (shift) — "Staging and prod have quietly drifted apart"**
- [ ] Refactor into reusable modules — `terraform modules`
- [ ] One codebase, two environments, different variables, no copy-paste — `environments`
- [ ] A dev changed something in the console. Find it with `terraform plan`, decide what to do — `drift detection`
- [ ] Write the team policy for console changes — something devs will actually follow — `collaboration`

**submit** — README + module structure explanation → review → blind-spot summary

---

## 07 — OrbitalScale Gaming
`Node.js · multiplayer game`
Launch day in three weeks. 10x traffic expected for six hours, then near-silence overnight.

**phase_1 — Get onto Kubernetes**
- [ ] Pods, deployments, services — explain each with an analogy before deploying — `k8s objects`
- [ ] Stand up EKS and deploy the app — `EKS`
- [ ] Expose it properly; explain how this differs from the ALB in project 03 — `ingress`

**phase_2 (shift) — "Launch day — 10x traffic, then dead quiet"**
- [ ] Configure HPA; load-test and watch it scale — `HPA`
- [ ] Set resource requests and limits; explain what happens if you skip them — `requests · limits`
- [ ] Scale the nodes too, not just the pods — `cluster autoscaler`
- [ ] Ship a new version with zero downtime; add liveness and readiness probes — `rolling updates · probes`

**phase_3 (shift) — "A pod keeps crashing in production"**
- [ ] Diagnose CrashLoopBackOff properly — logs, describe, events — `troubleshooting`

**submit** — README + load test results → review → blind-spot summary

---

## 08 — PulseCheck
`Python · health platform`
They find out about outages from angry users on social media. In healthcare.

**phase_1 — See what's happening**
- [ ] Explain metrics vs logs vs traces, and when each is the right tool — `metrics/logs/traces`
- [ ] Deploy Prometheus; scrape metrics from app and nodes — `Prometheus`
- [ ] Build a dashboard answering "is the service healthy right now?" at a glance — `Grafana`

**phase_2 (shift) — "200 alerts a day, the team ignores all of them"**
- [ ] Define real SLIs and SLOs; justify the numbers — `SLI · SLO · error budget`
- [ ] Rewrite alerts so every page is actionable; delete the rest — `alerting`
- [ ] Aggregate logs so you can trace one request across services — `centralized logging`

**phase_3 (shift) — "Auditor: prove who accessed patient data"**
- [ ] Set up audit logging and retention; produce the evidence — `CloudTrail · audit`

**submit** — README + dashboard screenshots + SLO doc → review → blind-spot summary

---

## 09 — Juicyway
`multi-service · fintech payments`
Money moves through this system. Security review before launch, and you own the outcome.

**phase_1 — Lock it down**
- [ ] Design roles and policies. No wildcards. Defend every permission — `IAM least privilege`
- [ ] Remove every hardcoded credential from codebase and pipeline — `Secrets Manager`
- [ ] Encrypt at rest and in transit; explain KMS key management plainly — `encryption`
- [ ] Draw the line: what AWS secures vs what you secure, specific to this stack — `shared responsibility`

**phase_2 (shift) — "Pentest came back with findings"**
- [ ] Add SAST, SCA, and secret scanning; explain what each catches the others miss — `SAST · SCA · secrets`
- [ ] Fail the build on HIGH/CRITICAL only; justify the tradeoff to a nervous CTO — `severity tuning`
- [ ] Segment services so a breach in one doesn't reach the ledger — `network segmentation`

**phase_3 (shift) — "Who can touch production?"**
- [ ] Run an access audit; enforce MFA and role assumption; document it — `access review · MFA`

**submit** — README + threat model + security decisions log → review → blind-spot summary

---

## 10 — Larkspur Retail
`PHP · legacy monolith`
A 12-year-old app in a dying data centre. Leadership wants it in AWS and the bill lower.

**phase_1 — Migrate it**
- [ ] Pick from the 6 Rs and defend your choice for this specific app — `migration strategy`
- [ ] Do this one in CloudFormation, not Terraform; then say which you prefer and why — `CloudFormation`
- [ ] Get the monolith running without rewriting it; document your workarounds — `legacy constraints`

**phase_2 (shift) — "The AWS bill tripled"**
- [ ] Find where the money goes — Cost Explorer, tags, the lot — `cost analysis`
- [ ] Cut the bill 40% without hurting performance; show your working — `right-sizing · spot`
- [ ] Move old data to cheaper storage tiers automatically — `S3 lifecycle`
- [ ] Present savings to non-technical leadership. One page, no jargon — `communication`

**submit** — README + cost before/after → review → blind-spot summary

---

## 11 — Vantage Analytics
`Python/Spark · data platform`
Single AZ, single database, single point of failure. A competitor just lost a region for nine hours.

**phase_1 — Remove the single points of failure**
- [ ] Redesign for multi-AZ; list every remaining SPOF — `multi-AZ`
- [ ] Make the DB survive an AZ loss; explain replica lag and its cost — `RDS Multi-AZ · replicas`
- [ ] Health checks that detect a *sick* instance, not just a dead one — `health checks`

**phase_2 (shift) — "What if we lose the whole region?"**
- [ ] Define RTO and RPO with the business; explain the cost of tighter targets — `RTO · RPO`
- [ ] Compare backup/restore, pilot light, warm standby; recommend one — `DR strategies`
- [ ] Actually run the failover. Time it. Document what went wrong — `failover drill`

**submit** — README + DR runbook + drill results → review → blind-spot summary

---

## 12 — Meridian Cloud
`everything · capstone`
You own the whole platform now. No safety net. This is the interview you're training for.

**phase_1 — Own it**
- [ ] Runbooks for the five most likely failures; assume the reader is half asleep — `runbooks`
- [ ] Design the on-call rotation and escalation path — `on-call`

**phase_2 (shift) — Chaos day**
- [ ] Design three chaos experiments, each with a clear hypothesis — `chaos engineering`
- [ ] Execute them; time how long your own monitoring takes to notice — `MTTD`

**phase_3 (shift) — The incident**
- [ ] A real multi-layer failure: detect, mitigate, communicate, resolve — `incident response`
- [ ] Write the blameless postmortem. Root cause, not symptom — `5 whys · postmortem`

**final review**
- [ ] Assemble all 12 projects into one portfolio — `portfolio`
- [ ] Interview against the job spec. No notes — `interview prep`
