# BluePhoenix — Detection Engineering & Automation Lab

BluePhoenix is a GitHub‑first detection‑engineering project designed to demonstrate how attacker behaviour is translated into telemetry, detection logic, and automated response decisions.

This project focuses on:
- MITRE ATT&CK–aligned detections
- Real endpoint telemetry generated locally
- Detection‑as‑code practices
- Security automation design
- Engineering‑grade documentation

No cloud services or paid tooling are required. GitHub acts as the control plane for all detection logic, telemetry samples, and automation workflows.

## Repository Structure

```
bluephoenix-detection-lab/
├── README.md
├── detections/
│   ├── T1059_command_execution.yaml
│   └── T1110_bruteforce.yaml
├── attack-simulations/
│   ├── T1059/
│   │   ├── attack_steps.md
│   │   ├── raw_logs.json
│   │   └── parsed_events.json
│   └── T1110/
│       ├── attack_steps.md
│       ├── raw_logs.json
│       └── parsed_events.json
├── automation/
│   └── response_decision_tree.md
├── docs/
│   ├── architecture.md
│   ├── detection-coverage.md
│   └── telemetry-sources.md
└── LICENSE
```


## Objectives
- Engineer high‑fidelity detections from real telemetry
- Map detections to MITRE ATT&CK techniques
- Document false positives and response strategies
- Design SOAR‑style automation workflows
- Demonstrate detection engineering maturity

## Scope (MVP)
- T1059 — Command Execution
- T1110 — Brute Force

## Telemetry Sources
- Windows Event Logs
- Sysmon
- Linux authentication logs
- Local attack simulations

## Disclaimer
This project is for defensive security research and learning purposes only.
