# Telemetry Sources

This document describes the telemetry sources used in the BluePhoenix Detection Lab, the rationale behind their selection, and the limitations of the collected data.

The goal of this project is to demonstrate detection engineering principles using real, observable signals without relying on cloud services or paid security tooling.

---

## Telemetry Overview

Telemetry in BluePhoenix is generated locally through controlled attack simulations and collected from native operating system logging mechanisms.

All logs are exported and stored as static JSON files to support offline analysis, detection engineering, and reproducibility.

---

## Windows Telemetry Sources

### Windows Security Event Log
Used to capture:
- Authentication successes and failures
- Account lockouts
- Logon types and sources

Relevant to:
- T1110 — Brute Force
- Identity‑based detections

### Sysmon
Used to capture:
- Process creation events
- Command‑line arguments
- Parent‑child process relationships

Relevant to:
- T1059 — Command Execution
- Behavioural endpoint detections

Sysmon was selected due to its widespread use in enterprise environments and its ability to provide high‑fidelity endpoint telemetry.

---

## Linux Telemetry Sources

### Authentication Logs (`auth.log`)
Used to capture:
- Failed login attempts
- SSH authentication activity
- User account access patterns

Relevant to:
- T1110 — Brute Force
- Cross‑platform identity abuse scenarios

---

## Telemetry Collection Method

Telemetry is collected by:
1. Executing controlled attack simulations locally
2. Capturing relevant log entries
3. Exporting logs to JSON format
4. Normalising and parsing events for analysis

This approach ensures:
- Full visibility into raw signals
- No dependency on external platforms
- Transparent data provenance

---

## Limitations

This project intentionally does not include:
- Real‑time log ingestion
- Cloud‑native telemetry (e.g., Defender XDR, Sentinel)
- Network‑level telemetry
- Large‑scale enterprise noise

As a result:
- Detections are evaluated against representative samples
- False‑positive rates are reasoned analytically rather than statistically
- Automation workflows are designed, not executed

These trade‑offs are deliberate and align with the project’s focus on detection engineering fundamentals rather than operational deployment.

---

## Design Rationale

The selected telemetry sources were chosen to:
- Reflect common enterprise logging configurations
- Support MITRE ATT&CK–aligned detection logic
- Enable clear attacker‑to‑signal reasoning
- Remain accessible in a zero‑budget environment

This mirrors how detection engineers often prototype and validate detections before production deployment.
