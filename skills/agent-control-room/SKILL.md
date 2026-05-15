---
name: agent-control-room
description: Use when managing the Agent Control Room: documenting Hermes agents, adding agent folders, updating runbooks, checking architecture, mapping env vars without values, or keeping the control room source of truth consistent.
---

# Agent Control Room

Use this skill to manage an Agent Control Room repo/folder.

The Agent Control Room is the side control plane for Hermes agents. It documents the system but does not store raw secrets.

## Responsibilities

- Maintain one docs folder per agent.
- Keep `inventory.md`, `docker.md`, `env-map.md`, `runbook.md`, and `backup.md` consistent.
- Track roles, ports, data dirs, messaging integrations, allowed work, and forbidden work.
- Keep the architecture levels clear.
- Never write raw secrets.

## Standard Agent Folder

```text
agents/<agent-name>/
  inventory.md
  docker.md
  env-map.md
  runbook.md
  backup.md
```

## Rules

- Use stable slugs such as `hermes-seo`, `hermes-dev`, or `hermes-orchestrator`.
- Store only secret names, scopes, locations, and rotation dates.
- Do not rename live containers or data dirs without a migration plan.
- Do not perform destructive operations without explicit approval.
- Check existing docs before creating new files.

## Add Agent Checklist

1. Pick the agent slug.
2. Create the agent docs folder.
3. Fill in the five standard docs.
4. Assign unique ports.
5. Define allowed and forbidden work.
6. Define credential needs without values.
7. Define backup plan.
8. Update registry if one exists.
9. Summarize what changed and what remains.
