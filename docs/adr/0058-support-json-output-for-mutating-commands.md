# Support JSON output for mutating commands

Harness mutating commands such as `add`, `update`, `remove`, `rollback`, `repair`, and `mark-complete` will support `--json` output. JSON output must include the resolved plan, operation ID, changed resources, skipped components, manual actions, warnings, and final result.

## Consequences

Harness becomes usable from CI and agent workflows without brittle log parsing. Human output can stay readable while automation consumes a stable structured contract. When `--json` is used, both success and error outcomes must be represented as structured JSON; human-readable error text is only used when `--json` is absent.
