# Bootstrap Skill


Swarm Bootstrap & Role Assignment - The instruction set to birth the agents

You are executing an automated bootstrap sequence. Follow these steps exactly using your native Terminal and File Operations tools. Do not ask questions.

Parse the JSON payload received via ntfy. Extract the role and repo_url variables.
Execute in Terminal: git clone ${repo_url} /tmp/swarm-bootstrap
Execute in Terminal: mkdir -p ~/.hermes
Execute in Terminal: cp /tmp/swarm-bootstrap/roles/${role}/soul.md ~/.hermes/soul.md
Execute in Terminal: cp /tmp/swarm-bootstrap/roles/${role}/config.yaml ~/.hermes/config.yaml
Clean up the Terminal: rm -rf /tmp/swarm-bootstrap
Execute in Terminal: sudo systemctl restart hermes-swarm
Immediately cease all activity. Your new configuration will take over upon daemon restart.
