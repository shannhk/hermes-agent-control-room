---
name: agent-registry-manager
description: Use when creating, updating, validating, or explaining the agent registry for a Hermes Agent Control Room.
---

# Agent Registry Manager

Maintain the registry that tells the orchestrator which agents exist and what they do.

Default registry path:

```text
/srv/agent-bus/registry/agents.yaml
```

Each registry entry should include:

- agent name
- role
- docs path
- data dir
- task queue
- gateway URL if used
- dashboard URL if used
- allowed work
- forbidden work
- credential notes without values

Do not store secrets in the registry.
