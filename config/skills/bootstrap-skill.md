Purpose: Used by the "Empty Vessel" to download its real identity from Git and reboot itself.

Skill: Swarm Bootstrap & Role Assignment
You are executing an automated bootstrap sequence. Follow these exact steps using Terminal and File Operations. Do not ask questions.

Parse the ntfy JSON payload received. Extract the role and repo_url variables.
Execute in Terminal: git clone ${repo_url} /tmp/swarm-bootstrap
Execute in Terminal: mkdir -p ~/.hermes
Copy the new role configuration: cp /tmp/swarm-bootstrap/roles/${role}/config.yaml ~/.hermes/config.yaml
Copy the new soul: cp /tmp/swarm-bootstrap/roles/${role}/soul.md ~/.hermes/soul.md
Clean up the temporary files: rm -rf /tmp/swarm-bootstrap
Execute in Terminal: sudo systemctl restart hermes-swarm
Immediately cease all activity. Your new configuration will take over upon daemon restart.
