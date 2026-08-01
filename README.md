# Serhii Drobot

**Linux infrastructure security · founder of [Owlzops](https://owlzops.com)**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://linkedin.com/in/serhii-drobot)
[![Email](https://img.shields.io/badge/Email-hello@owlzops.com-red?style=flat&logo=gmail)](mailto:hello@owlzops.com)

I've spent my career in Linux infrastructure — Kubernetes across GKE, EKS, AKS and OpenShift, Terraform and Ansible, Docker in production. Now I do one thing: find what's exposed on other people's servers, then close it.

Most of what I find isn't exotic. Root SSH still permitted. A container running privileged with the Docker socket mounted. A firewall nobody ever switched on. Defaults nobody turned off.

---

## owlzops-mapper

[![GitHub](https://img.shields.io/badge/OWLZOPS/owlzops--mapper-%23181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/OWLZOPS/owlzops-mapper)
[![CI](https://github.com/OWLZOPS/owlzops-mapper/actions/workflows/ci.yml/badge.svg)](https://github.com/OWLZOPS/owlzops-mapper/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/OWLZOPS/owlzops-mapper?style=flat)](https://github.com/OWLZOPS/owlzops-mapper/releases)

One static Rust binary. Sub-second Linux + Docker audit. No agents, no Python, no kernel modules, no open ports, nothing left resident.

```bash
sudo ./owlzops-mapper audit
```

It finds reverse shells, fileless implants, library injection, hidden PIDs from LKM rootkits, container escapes, and the usual dangerous defaults — every finding mapped to a CIS reference, with an exit code you can wire into CI (`3` means active compromise).

I wrote it because I was tired of running six tools and still not knowing whether something was already inside. Read-only, `--offline` guarantees zero outbound calls, and the source is public so you can check what runs as root on your box before you run it.

**[→ Repository](https://github.com/OWLZOPS/owlzops-mapper)** · source-available under Apache 2.0 with the Commons Clause — free for your company forever, not for resale.

---

## I ran it on my own production first. It scored 60.

Before asking anyone to run a scanner against their production, I ran it against mine — the host that actually serves my company. Root SSH permitted, password auth on, a user with passwordless sudo to every command, FTP listening on `0.0.0.0`. It finished at **23, not 0**, because two findings couldn't be removed without breaking the machine, so they got `auditd` rules watching them instead.

The part I keep coming back to: I stripped `CAP_SYS_ADMIN` and `CAP_SYS_PTRACE` from Apache and `atd` — a web server running as uid 33 could read the memory of every other process on the box. **The score didn't move. 23 before, 23 after.** The rule is binary and other processes still hold capabilities they legitimately need. I did it anyway, because the point is the infrastructure, not the number on the dashboard.

**[→ Full write-up, with the findings I didn't close and why](https://owlzops.com/#case-study)**

---

## Owlzops

Boutique DevSecOps practice. Fixed price, defined scope, no hourly billing. The person who scopes the work is the one who does it — that's me.

- **Infrastructure Security Audit** — read-only. What's exposed, and whether anyone is already inside.
- **Infrastructure Hardening** — SSH lockdown, default-deny firewall, rootless containers, patch baseline. Staged, reversible, with a before/after diff.
- **Continuous Hardening** — weekly drift scans against your hardened baseline, plus engineering hours.

**Run the scanner first.** If it comes back clean, I'll say so instead of selling you the audit.

**[→ Scan your own server](https://owlzops.com/mapper/?utm_source=github&utm_medium=profile&utm_campaign=profile)** · **[Pricing and scope](https://owlzops.com/?utm_source=github&utm_medium=profile&utm_campaign=profile#services)** · **[Field notes](https://owlzops.com/guides/?utm_source=github&utm_medium=profile&utm_campaign=profile)**

---

*Engagements start on Mondays · current lead time about a week · I take a limited number at a time.*
