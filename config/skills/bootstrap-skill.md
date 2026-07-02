# Skill: Swarm Bootstrap & Role Assignment

You are executing an automated bootstrap sequence. Follow these exact steps using Terminal and File Operations. Do not ask questions.

## STEP 1

Parse the ntfy JSON payload received.

Extract the following variables:

- `role`
- `repo_url`

## STEP 2

Execute in Terminal:

```bash
git clone ${repo_url} /tmp/swarm-bootstrap
```

## STEP 3

Execute in Terminal:

```bash
mkdir -p ~/.hermes
```

## STEP 4

Copy the new role configuration:

```bash
cp /tmp/swarm-bootstrap/roles/${role}/config.yaml ~/.hermes/config.yaml
```

## STEP 5

Copy the new soul:

```bash
cp /tmp/swarm-bootstrap/roles/${role}/soul.md ~/.hermes/soul.md
```

## STEP 6

Clean up temporary files:

```bash
rm -rf /tmp/swarm-bootstrap
```

## STEP 7

Restart the Hermes daemon to load the new identity:

```bash
sudo systemctl restart hermes-swarm
```

## STEP 8

Immediately cease all activity.

Your new configuration will take over upon daemon restart.
