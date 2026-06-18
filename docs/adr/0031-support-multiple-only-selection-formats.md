# Support multiple `--only` selection formats

Harness will support multiple `--only` formats for partial installs: repeated flags such as `--only skill:review --only mcp:jira` and comma-separated values such as `--only skill:review,mcp:jira`. The canonical documented form is repeated flags.

## Consequences

When `--only` is present, Harness installs only the selected component keys and their related files/configuration. This mirrors the multi-value behavior of `--target` and keeps scripted installs deterministic.
