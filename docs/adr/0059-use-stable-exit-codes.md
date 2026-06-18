# Use stable exit codes

Harness will use stable exit codes for automation: `0` for success, `1` for generic errors, `2` for validation or plan errors, `3` for drift, `4` for collision, and `5` for lock contention.

## Consequences

CI, scripts, and agents can react to Harness outcomes without parsing human-readable messages. New exit codes must be added deliberately and documented as part of the CLI contract.
