# Hermes Agent Control Room

A public template for setting up an **Agent Control Room** first, then scaling from one Hermes agent to direct specialists, orchestrated teams, and automated workflows.

The Agent Control Room is a sidecar repo/folder that documents and governs your Hermes agents. It is not an agent itself. It is the system map, operating manual, registry, and recovery notebook for the agents you run.

## Positioning

```text
Control Room first.
One agent second.
Specialists third.
Orchestrator fourth.
Automation last.
```

## Mental Model

```text
Agent Control Room = side control plane
Orchestrator       = optional manager/front-door agent
Specialists        = focused Hermes agents with role-specific tools
Task Bus           = handoff desk between orchestrator and specialists
You                = owner/operator with direct access to everything
```

## Full System Shape

```text
                                      You
                    +------------------+------------------+
                    |                  |                  |
                    v                  v                  v
        +----------------------+ +--------------+ +----------------+
        | Agent Control Room   | | Orchestrator | | Direct Agent    |
        | ./                   | | optional     | | Access          |
        |                      | +------+-------+ +--------+-------+
        | docs, rules, map,    |        |                  |
        | registry, runbooks   |        v                  v
        +----------+-----------+ +--------------+ +----------------+
                   |             | Task Bus     | | Specialist     |
                   |             | /srv/agent-  | | Agent          |
                   |             | bus          | +----------------+
                   |             +------+-------+
                   |                    |
                   |                    v
                   |          +---------+----------+
                   |          |                    |
                   |          v                    v
                   |   +-------------+      +-------------+
                   |   | SEO Agent   |      | Dev Agent   |
                   |   +-------------+      +-------------+
                   |
                   v
        Defines / documents / governs all agents
```

## Architecture Levels

### Level 1: Agent Control Room + One Agent

Set up the control room and register one Hermes agent.

Best for:

- One personal Hermes agent
- VPS setup documentation
- Docker migration planning
- Keeping runbooks and secret maps organized

### Level 2: Direct Specialist Agents

Add multiple role-specific Hermes agents and talk to them directly.

Examples:

- `hermes-life`
- `hermes-seo`
- `hermes-dev`
- `hermes-cmo`
- `hermes-ops`

### Level 3: Orchestrator + Specialists

Add `hermes-orchestrator` as an optional front door. You can still talk directly to specialists, but the orchestrator can route and synthesize work.

### Level 4: Automated Agent Team

Add recurring workflows, audits, backup checks, task routing, result review, and optional direct gateway/API calls.

## Suggested Folder Structure

```text
agent-control-room/
  README.md
  docs/
    architecture.md
    levels.md
    naming.md
    security.md
    task-bus.md
    orchestrator.md
  templates/
    agent/
      inventory.md
      docker.md
      env-map.md
      runbook.md
      backup.md
    docker/
      docker-compose.agent.yml
      docker-compose.orchestrator.yml
    task-bus/
      agents.yaml
      task-template.md
      result-template.md
  skills/
    agent-control-room/
    agent-task-router/
    agent-registry-manager/
    agent-result-reviewer/
    agent-backup-manager/
    agent-security-auditor/
    agent-team-cron-planner/
  examples/
    level-1-control-room-one-agent/
    level-2-direct-specialists/
    level-3-orchestrator-specialists/
    level-4-automated-team/
```

## Quick Start

1. Clone or use this repo as a template.
2. Copy `templates/agent/` into `agents/<your-agent-name>/`.
3. Fill in `inventory.md`, `docker.md`, `env-map.md`, `runbook.md`, and `backup.md`.
4. Keep raw secrets out of the control room.
5. Store live Hermes data in `/srv/<agent-name>/data` or your preferred runtime path.
6. Add specialist agents only when roles become clear.
7. Add an orchestrator only when direct specialist usage becomes annoying.

## Security Rule

Never commit raw secrets.

The control room may record:

- secret names
- provider
- scope
- location
- rotation date

It must not record:

- API key values
- OAuth refresh tokens
- passwords
- private keys

## License

MIT. See `LICENSE`.
