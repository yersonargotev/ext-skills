# Lock installation scope during transactions

Harness will use a file-based scope lock to prevent concurrent transactions from mutating the same project or global installation scope. Project operations lock `.harness`; global operations lock `~/.config/harness`.

## Consequences

Concurrent commands such as update and remove cannot corrupt lockfile, history, backups, or store state by writing at the same time. Commands that cannot acquire the scope lock fail fast by default and may wait only when the user explicitly passes a flag such as `--wait`.
