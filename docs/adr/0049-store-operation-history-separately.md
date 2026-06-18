# Store operation history separately

Harness will keep current installed state in the Harness Lockfile and record transaction history in a separate append-only operation history file. Project installs use `.harness/history.jsonl`; global installs use `~/.config/harness/history.jsonl`.

## Consequences

The lockfile stays focused on current state, while operation history remains audit-oriented and suitable for rollback, repair, and troubleshooting. Harness must keep lockfile and history writes coordinated inside install transactions.
