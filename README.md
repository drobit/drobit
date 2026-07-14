# Serhii Drobot
**Founder at [Owlzops](https://owlzops.com) · DevOps & Infrastructure Engineering**
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://linkedin.com/in/serhii-drobot)
[![Email](https://img.shields.io/badge/Email-hello@owlzops.com-red?style=flat&logo=gmail)](mailto:hello@owlzops.com)
[![Telegram](https://img.shields.io/badge/Telegram-@d_serg-blue?style=flat&logo=telegram)](https://t.me/d_serg)

---

I run **[Owlzops](https://owlzops.com)** — a DevOps engineering company. We help startups and scale-ups fix infrastructure problems before they become incidents.

**What we do:**
- Compromise assessment & active threat detection
- Linux server hardening and security auditing
- Kubernetes operations (GKE, EKS, AKS, OCP)
- Infrastructure as Code (Terraform, Ansible)
- Docker and container security

**[Book a free infrastructure review call](https://owlzops.com/contact?utm_source=github&utm_medium=readme&utm_campaign=mapper_table)**

---

## Open Source: owlzops-mapper — a EDR-lite for Linux servers

[![GitHub](https://img.shields.io/badge/OWLZOPS/owlzops--mapper-%23181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/OWLZOPS/owlzops-mapper)
[![CI](https://github.com/OWLZOPS/owlzops-mapper/actions/workflows/ci.yml/badge.svg)](https://github.com/OWLZOPS/owlzops-mapper/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/OWLZOPS/owlzops-mapper?style=flat)](https://github.com/OWLZOPS/owlzops-mapper/releases)

A single Rust binary that detects active threats, Docker escapes, and misconfigurations on any Linux server in under a second — no agents, no eBPF, no open ports.

```bash
sudo ./owlzops-mapper audit
```

**Threat detection (IoC):** fileless malware & memfd implants · reverse shells / C2 connections · library injection & LD_PRELOAD rootkits · hidden PIDs (LKM rootkit) · Docker container runtime cap tampering · kernel-thread masquerading · bind-mount masking

**Hardening & compliance:** SSH config · firewall · pending security updates · SSL expiry · sysctl hardening · sudo NOPASSWD · backups · NTP drift — all mapped to CIS Benchmark refs

**Deep forensics (`--deep`):** reads process memory, resolves pointers, calculates entropy, flags unattributed executable payloads

**Output:** terminal dashboard · JSON (SIEM-ready) · Excel · exit codes for CI/CD (0 clean / 1 findings / 2 incomplete / **3 active compromise**)

Fully air-gapped. No data ever leaves the server.

**[View the repository](https://github.com/OWLZOPS/owlzops-mapper)**

---

*If owlzops-mapper flags an active compromise or a Docker escape — [that's what Owlzops fixes](https://owlzops.com).*
