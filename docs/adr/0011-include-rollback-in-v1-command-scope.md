# Include rollback in v1 command scope

Harness v1 will include `add`, `list`, `remove`, `update`, and `rollback`. Rollback is included because Harness modifies target-agent configuration and already creates centralized backups before those modifications.

## Consequences

V1 implementation is larger, but safer: users get an explicit recovery command instead of manually restoring backups. Rollback should restore configuration from Harness-managed backups and must not be treated as the same operation as removing an installed plugin.
