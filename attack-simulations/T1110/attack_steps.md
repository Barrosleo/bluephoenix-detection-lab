# T1110 — Brute Force Simulation

## Objective
Generate authentication-failure telemetry consistent with brute-force behaviour to validate the T1110 detection logic.

## Preconditions
- A local test account exists (e.g., `testuser`)
- Logging is enabled for authentication events (Windows Security log and/or Linux auth.log)

## Steps (Windows)
1. Attempt to log in to `testuser` with an incorrect password repeatedly (e.g., 5–10 attempts within 5 minutes).
2. Confirm failed logon events are recorded in the Windows Security Event Log.

## Steps (Linux)
1. Attempt SSH login to a local Linux host with an incorrect password repeatedly (e.g., 5–10 attempts within 5 minutes).
2. Confirm failed authentication events are recorded in `/var/log/auth.log`.

## Expected Telemetry
- Windows: repeated failed logons (e.g., Event ID 4625)
- Linux: repeated `Failed password` entries in `auth.log`

## Expected Detection Outcome
- The T1110 detection should trigger when the failure threshold is exceeded within the defined time window.
