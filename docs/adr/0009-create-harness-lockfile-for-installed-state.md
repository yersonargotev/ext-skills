# Create a Harness lockfile for installed state

Harness will write a lockfile that records installed plugins and selected components, including version, target, scope, installation method, source, and integrity metadata. Project installations use `.harness/lock.json`; global installations use `~/.config/harness/lock.json`.

## Consequences

Installations become more traceable and reversible, while `.harness/` leaves room for future Harness state such as cache, backups, install plans, and audit reports. The CLI must carefully update the lockfile transactionally so failed installs do not leave misleading state.
