# Back up agent configuration before modification

Harness must create a backup before modifying existing target-agent configuration files such as MCP or hook configuration. Project and global backup locations are defined by the Harness state layout ADRs.

## Consequences

Install operations need backup paths and rollback-aware error handling. Centralized backups avoid polluting agent config directories, and later ADRs define operation IDs/history as the ownership model for associating each backup with the transaction that created it.
