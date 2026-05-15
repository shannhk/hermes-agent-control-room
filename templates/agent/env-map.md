# <agent-name> - Env / Secret Map

This file records where secrets live, not their values.

## Container `.env`

- Inside container: `/opt/data/.env`
- On host: `/srv/<agent-name>/data/.env`

## Keys

| Key | Purpose | Provider | Scope | Stored where | Last rotated |
|---|---|---|---|---|---|
| `EXAMPLE_API_KEY` | Example | Example | Read-only | `/opt/data/.env` | TBD |

## Rules

- Do not paste raw secret values in this file.
- Use per-agent key names in provider dashboards.
- Prefer least privilege.
- Rotate any key pasted into chat.
