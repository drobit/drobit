# Serhii Drobot

**Founder at [Owlzops](https://owlzops.com) · DevSecOps & Linux Infrastructure Security**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://linkedin.com/in/serhii-drobot)
[![Email](https://img.shields.io/badge/Email-hello@owlzops.com-red?style=flat&logo=gmail)](mailto:hello@owlzops.com)
[![Telegram](https://img.shields.io/badge/Telegram-@d__serg-blue?style=flat&logo=telegram)](https://t.me/d_serg)

---

I run **[Owlzops](https://owlzops.com)** — a boutique DevSecOps practice. We find what's exposed on your Linux infrastructure, and then we close it.

Most of what we find isn't exotic. It's root SSH still permitted, a container running privileged with the Docker socket mounted, a firewall nobody ever switched on. Defaults nobody turned off.

**What we do:**

| | | |
|---|---|---|
| **Infrastructure Security Audit** | 3 days · up to 10 hosts | **$2,995** — read-only. What's exposed, and is anyone already inside. Run the free scanner first: if it comes back clean, we'll say so instead of selling you the audit. |
| **Infrastructure Hardening** | 5–10 days | **from $5,900** — SSH lockdown, default-deny firewall, rootless containers, patch baseline. Staged, reversible, with before/after proof. |
| **Continuous Hardening** | monthly | **$2,500 / $5,000** — weekly drift scans against your hardened baseline, plus engineering hours. |

Fixed price. Defined scope. No hourly billing.

**[Scan your own server first →](https://owlzops.com/mapper/)** · **[Book an audit](https://owlzops.com/contact?utm_source=github&utm_medium=readme&utm_campaign=profile)**

---

## owlzops-mapper — an EDR-lite for Linux servers

[![GitHub](https://img.shields.io/badge/OWLZOPS/owlzops--mapper-%23181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/OWLZOPS/owlzops-mapper)
[![CI](https://github.com/OWLZOPS/owlzops-mapper/actions/workflows/ci.yml/badge.svg)](https://github.com/OWLZOPS/owlzops-mapper/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/OWLZOPS/owlzops-mapper?style=flat)](https://github.com/OWLZOPS/owlzops-mapper/releases)
[![License](https://img.shields.io/badge/license-Apache--2.0%20%2B%20Commons%20Clause-blue?style=flat)](https://github.com/OWLZOPS/owlzops-mapper/blob/main/LICENSE)

A single Rust binary that detects active threats, Docker escapes, and misconfigurations on any Linux server in under a second — no agents, no eBPF, no open ports, nothing left resident.

```bash
sudo ./owlzops-mapper audit
```

**Threat detection (IoC):** fileless malware & memfd implants · reverse shells / C2 connections · library injection & LD_PRELOAD rootkits · hidden PIDs (LKM rootkit) · Docker runtime capability tampering · kernel-thread masquerading · bind-mount masking

**Hardening & compliance:** SSH config · firewall · pending security updates · SSL expiry · sysctl hardening · sudo NOPASSWD · backups · NTP drift — every finding mapped to a CIS Benchmark reference

**Deep forensics (`--deep`):** reads process memory via `process_vm_readv` (not `ptrace`), resolves pointers, calculates entropy, flags unattributed executable payloads — and suppresses JIT noise instead of burying you in it

**Output:** terminal dashboard · JSON · Excel · exit codes for CI/CD (0 clean / 1 findings / 2 incomplete / **3 active compromise**)

Read-only. Air-gapped with `--offline`. No data ever leaves the server.

**Licence:** Apache 2.0 with the [Commons Clause](https://commonsclause.com/) — free for your company to use forever, including commercial and internal audits. Not open source in the strict sense: the Commons Clause restricts reselling it as a product, which fails the Open Source Definition. Calling it "source-available" is the accurate term.

**[View the repository →](https://github.com/OWLZOPS/owlzops-mapper)**

---

*If the mapper flags an active compromise or a Docker escape — [that's what Owlzops fixes](https://owlzops.com).*
