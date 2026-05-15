# <agent-name> - Docker

## Status

- Container running:
- Image:
- Data dir:
- Started:

## Layout

```text
/srv/<agent-name>/
  data/
    .env
    config.yaml
    SOUL.md
    memories/
    skills/
    cron/
    sessions/
    logs/
  docker-compose.yml
```

## Compose

See `templates/docker/docker-compose.agent.yml`.

## Common Operations

```bash
docker logs -f <agent-name>
docker exec -it <agent-name> bash
docker compose -f /srv/<agent-name>/docker-compose.yml restart
docker compose -f /srv/<agent-name>/docker-compose.yml pull
docker compose -f /srv/<agent-name>/docker-compose.yml up -d
```

## Gotchas

- Do not run two gateway processes against the same data directory.
- Do not commit `.env` or token files.
- Keep host ports unique per agent.
- Prefer binding dashboards/API to `127.0.0.1` unless secured.
