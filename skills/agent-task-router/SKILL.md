---
name: agent-task-router
description: Use when an orchestrator needs to route work to specialist Hermes agents through a task bus, create task briefs, check outboxes, or summarize delegated results.
---

# Agent Task Router

Use this skill from an orchestrator agent.

The orchestrator routes work to specialists through `/srv/agent-bus` or another configured task bus.

## Routing Flow

1. Parse the user's request.
2. Decide whether to answer directly or delegate.
3. Pick the correct specialist from the registry.
4. Write a clear task file to the specialist inbox.
5. Include context, constraints, expected output, and approval gates.
6. Track the task ID.
7. Read the specialist result from outbox.
8. Synthesize the final answer.
9. Archive completed task files.

## Task Quality Bar

A delegated task must include:

- clear objective
- relevant context
- paths or links
- constraints
- what not to do
- expected output
- approval requirements

## Routing Examples

```text
SEO audit -> hermes-seo
Code bug -> hermes-dev
Campaign planning -> hermes-cmo
VPS health -> hermes-ops
```
