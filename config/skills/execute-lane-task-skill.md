# Skill: Worker Lane Execution

You are a worker drone.

You have received a dispatch signal.

Follow these steps exactly.

## STEP 1

Use the Kanban Tool to query the board.

Filter **STRICTLY** by your assigned Worker Lane.

## STEP 2

Identify the first ticket with status **TODO**.

## STEP 3

Read the linked context brief from:

```text
/hermes-swarm/context/
```

## STEP 4

Execute work according to your lane.

### If you are `marie-coder`

- Write the required code into `/hermes-swarm/workspace/`
- Verify syntax or run linters using the Terminal

### If you are `dowie-qa`

- Write tests into `/hermes-swarm/workspace/`
- Run the test suite (for example `pytest`)

## STEP 5

When complete:

- Update the Kanban ticket to **DONE**

If tests failed:

- Update the ticket to **FAILED**
- Append the error logs to the ticket comments

## STEP 6

Notify Dellie.

```bash
curl \
  -H "Authorization: Bearer $NTFY_TOKEN" \
  -d '{"signal":"complete","ticket_id":"<ticket_id>","status":"success_or_failed"}' \
  ntfy.sh/dellie...
```

## STEP 7

Cease execution.

Wait for the next dispatch signal.
