---
name: agent-security-auditor
description: Use when auditing a VPS-based Hermes agent setup for exposed dashboards, weak secret handling, broad keys, Docker risks, or missing backup/security documentation.
---

# Agent Security Auditor

Audit the Agent Control Room and runtime setup for security issues.

Check:

- exposed dashboard/API ports
- SSH hardening notes
- Docker containers and mounted paths
- `.env` files accidentally committed
- raw secrets in docs
- token scope and rotation dates
- per-agent least privilege
- backup repo exclusions

Do not print raw secret values. Report locations and remediation steps.
