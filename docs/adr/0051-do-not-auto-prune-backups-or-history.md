# Do not auto-prune backups or history in v1

Harness v1 will not automatically prune operation history, config backups, or store assets that may be needed for rollback, repair, or audit. Cleanup will require an explicit future maintenance flow such as `harness gc` with user-selected retention rules.

## Consequences

Harness preserves recovery evidence by default, but disk usage can grow over time. Users must opt into cleanup instead of having rollback context removed silently.
