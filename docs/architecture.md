# Architecture

The Agent Control Room is a side control plane for Hermes agents.

It documents and governs the system, but it is not the default conversation path.

You can:

- Open the control room to manage the system.
- Talk directly to one specialist agent.
- Talk to an orchestrator that delegates to specialists.

## Control Plane vs Runtime

Control room:

```text
./
  agents/
  shared/
  docs/
```

Runtime data:

```text
/srv/<agent-name>/data
```

The control room should contain docs and templates. Runtime folders contain live Hermes state, credentials, memory, sessions, crons, and logs.

## Access Paths

Control path:

```text
You -> Agent Control Room
```

Direct path:

```text
You -> Specialist Agent
```

Orchestrated path:

```text
You -> Orchestrator -> Task Bus -> Specialist Agent -> Orchestrator -> You
```

## Recommended Container Pattern

Use one Docker container per long-running Hermes agent.

Each agent gets:

- its own `/opt/data`
- its own `.env`
- its own memory, skills, sessions, crons, and logs
- its own messaging tokens
- its own backup plan

Do not run two gateway processes against the same data directory.
