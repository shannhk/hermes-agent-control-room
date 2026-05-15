---
name: agent-backup-manager
description: Use when designing, auditing, or documenting backups for Hermes agents without committing secrets.
---

# Agent Backup Manager

Design and audit per-agent backups.

Include durable agent state:

- `SOUL.md`
- non-secret config
- memories
- skills
- cron definitions
- selected docs

Exclude:

- `.env`
- auth files
- OAuth token files
- sessions
- logs
- state DB unless explicitly intended
- private keys

Always verify `.gitignore` before committing.
