# Create config backups per operation

Harness will create a config backup for each operation that modifies target-agent configuration, even when a previous backup already exists for the same file. Each backup is associated with the operation ID that caused the change.

## Consequences

Backups consume more disk space, but rollback and audit become precise. Harness can explain exactly which config snapshot belongs to which install, update, remove, repair, or rollback transaction.
