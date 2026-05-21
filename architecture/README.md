# PayBridge — System Architecture

This folder contains the reference architecture for **PayBridge**, the fictional fintech startup used in the *Mind the GRC* 14-day SOC 2 build-in-public series.

PayBridge is not a real company. The architecture, data flows, and compliance challenges are modelled on real cross-border-payment startups (Skydo, Zerodha, Razorpay) so that everything documented here is realistic — but no real customer data is ever involved.

---

## Files in this folder

| File | Purpose |
|---|---|
| `paybrige-system-architecture.png` | Visual system architecture diagram (the canonical version of the ASCII diagram shown in the Day 2 post) |
| `paybrige-system-architecture.md` | Written companion to the diagram — tech stack, data flows, and SOC 2 control mapping |
| `README.md` | This file — index and series context |

---

## How this folder maps to the Substack series

**Day 1 — *Why I'm Doing This Project, Publicly***
Establishes the goal: implement SOC 2 end-to-end for a fictional fintech, in public, over 14 days. Every diagram and template in this repo is open and free to reuse.
Post: <https://mindthegrc.substack.com/p/why-im-doing-this-project-publicly>

**Day 2 — *Designing PayBridge's Tech Stack — A Fictional Fintech Built for SOC 2***
Introduces the layered architecture this diagram represents: a Next.js frontend, a Node.js + Express API, Postgres / Redis / Mongo for state, AWS for the underlying platform, plus the security, observability, and CI/CD layers. Also lays out which SOC 2 control area each layer maps to.
Post: <https://mindthegrc.substack.com/p/designing-paybridges-tech-stack-a>

---

## The architecture in one sentence

A typical multi-tier SaaS fintech: TLS-terminated browser traffic hits a Next.js frontend, which talks to a Node.js / Express API; the API uses Postgres for transactional data, Redis for sessions, and Mongo for KYC documents; everything runs on AWS (EC2 / RDS / S3 / CloudTrail / KMS / VPC) with CloudWatch + Datadog + PagerDuty for monitoring and GitHub Actions for CI/CD.

The diagram and the markdown companion expand each of those layers and call out the specific SOC 2 Trust Service Criteria they support.

---

## Reusing this

Everything in `architecture/` is free to copy, adapt, and reuse for your own SOC 2 readiness work. If you do, a link back to the Substack series is appreciated but not required.

