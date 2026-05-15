# <agent-name> - Runbook

## Talk To The Agent

- Telegram:
- Slack:
- CLI:
- Dashboard:

## Check Status

```bash
docker ps
docker logs <agent-name> --tail 100
```

## Restart

```bash
docker compose -f /srv/<agent-name>/docker-compose.yml restart
```

## Upgrade

```bash
docker compose -f /srv/<agent-name>/docker-compose.yml pull
docker compose -f /srv/<agent-name>/docker-compose.yml up -d
```

## Rotate A Key

1. Create the new key in the provider dashboard.
2. Update `/srv/<agent-name>/data/.env`.
3. Restart the container if needed.
4. Revoke the old key.
5. Update `env-map.md`.

## Restore From Backup

See `backup.md`.
