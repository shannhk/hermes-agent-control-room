# Orchestrator

The orchestrator is optional.

Add it when you want one front door for delegation and synthesis.

The orchestrator should:

- read the Agent Control Room
- know which agents exist
- know what each agent is allowed to do
- write clear task briefs
- route tasks through the task bus
- review specialist results
- synthesize the final response

The orchestrator should not:

- hold every specialist credential
- bypass specialist tools when the specialist is the source of truth
- publish, delete, rotate keys, or deploy without explicit approval
