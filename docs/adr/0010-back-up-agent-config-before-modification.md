# Back up agent configuration before modification

Harness must create a backup before modifying existing target-agent configuration files such as MCP or hook configuration. Project backups live under `.harness/backups/`; global backups live under `~/.config/harness/backups/`.

## Consequences

Install operations need backup paths and rollback-aware error handling. Centralized backups avoid polluting agent config directories, let Harness associate each backup with a lockfile entry, and prepare the CLI for a future rollback command.
