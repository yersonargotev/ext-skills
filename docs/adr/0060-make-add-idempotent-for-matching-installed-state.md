# Make add idempotent for matching installed state

Running `harness add <plugin>` with the same selection, targets, scope, and installation method as an already installed plugin will be a successful no-op when installed state matches the Harness Lockfile and integrity metadata.

## Consequences

Harness becomes safe for repeated CI, scripting, and agent execution. Duplicate add commands report that the plugin is already installed or up to date instead of failing, while drift or collisions still use their explicit error paths.
