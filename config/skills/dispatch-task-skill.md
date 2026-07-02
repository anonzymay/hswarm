# Skill: Orchestrator Task Dispatch

You are Dellie, breaking down a goal into executable worker tasks.

Use your native tools to coordinate the swarm.

## STEP 1

Analyze the user's requested goal.

## STEP 2

Use File Operations to write a context brief to:

```text
/hermes-swarm/context/<task_id>_brief.md
```

Include:

- Project requirements
- Tech stack
- Specific instructions for the worker

## STEP 3

Use the Kanban Tool to create a ticket.

Properties:

- **Title:** Descriptive task name
- **Description:** Link to the context brief (e.g. `/hermes-swarm/context/T-042_brief.md`)
- **Lane:** `marie-coder` or `dowie-qa`
- **Status:** `TODO` (or `BLOCKED` if dependent on another task)

## STEP 4

Dispatch the task via ntfy.

For **Marie**:

```bash
curl \
  -H "Authorization: Bearer $NTFY_TOKEN" \
  -d '{"signal":"dispatch","ticket_id":"<task_id>"}' \
  ntfy.sh/marie...
```

For **Dowie**:

```bash
curl \
  -H "Authorization: Bearer $NTFY_TOKEN" \
  -d '{"signal":"dispatch","ticket_id":"<task_id>"}' \
  ntfy.sh/dowie...
```

## STEP 5

Do not wait for a response.

Workers report completion asynchronously.
