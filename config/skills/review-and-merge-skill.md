# Skill: Code Review & Merge

A worker has reported a completed task.

Follow these steps to finalize the work.

## STEP 1

Read the ntfy payload and identify `<ticket_id>`.

## STEP 2

Verify using the Kanban Tool that the ticket is marked **DONE**.

## STEP 3

Spawn a local sub-agent using Task Delegation with the following prompt:

> Review the code changes associated with `<ticket_id>` in `/hermes-swarm/workspace/` for quality, security, and alignment with the context brief in `/hermes-swarm/context/`. Output strictly **APPROVED** or **REJECTED** with reasons.

## STEP 4

If the result is **APPROVED**, execute:

```bash
cd /hermes-swarm/workspace/

git add .

git commit -m "Completed <ticket_id>"

# Uncomment if remote push is configured
git push
```

## STEP 5

If the result is **REJECTED**:

- Move the Kanban ticket back to **TODO**
- Notify the appropriate worker via ntfy to address the issues
