# Agent Task Bus

The task bus is a shared handoff folder for orchestrated workflows.

Suggested path on a VPS:

```text
/srv/agent-bus
```

Suggested layout:

```text
/srv/agent-bus/
  registry/
    agents.yaml
  tasks/
    seo/
      inbox/
      working/
      outbox/
      archive/
    dev/
      inbox/
      working/
      outbox/
      archive/
```

The orchestrator writes task files to specialist inboxes. Specialists write result files to outboxes. The orchestrator reads results and archives completed work.
