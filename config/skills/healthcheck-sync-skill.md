# Skill: Syncthing Healthcheck

You are performing a routine system check.

Do not alert the orchestrator unless there is a problem.

## STEP 1

Execute:

```bash
syncthing cli show status
```

## STEP 2

Analyze the output.

If the state is:

- `idle`
- `syncing`

Do nothing.

The system is healthy.

## STEP 3

If the state is:

- `error`
- `offline`

or connection failures are detected, notify Dellie:

```bash
curl \
  -H "Authorization: Bearer $NTFY_TOKEN" \
  -d '{"signal":"alert","system":"syncthing","message":"Syncthing state is degraded or offline."}' \
  ntfy.sh/dellie...
```

## STEP 4

Cease execution.
