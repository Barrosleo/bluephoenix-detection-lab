# T1059 — Command Execution Simulation

## Objective
Simulate attacker‑driven command execution using PowerShell to generate
real endpoint telemetry.

## Steps
1. Open PowerShell as a standard user
2. Execute encoded command payload
3. Observe process creation and command‑line logging

## Expected Telemetry
- Sysmon Event ID 1
- PowerShell command‑line logging
- Parent‑child process relationships
