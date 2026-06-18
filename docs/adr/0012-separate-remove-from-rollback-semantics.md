# Separate remove from rollback semantics

Harness will treat `remove` and `rollback` as different operations. `remove` uninstalls selected plugin files and cleans target-agent configuration while preserving backup and history data; `rollback` restores target-agent configuration from a previous Harness-managed backup.

## Consequences

Users get predictable destructive behavior: removal cleans the current installation, while rollback is recovery-oriented. The lockfile/history model must preserve enough metadata after removal to support audit and recovery decisions.
