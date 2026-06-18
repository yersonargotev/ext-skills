# Support multiple target selection formats

Harness will support multiple `--target` formats: repeated flags such as `--target codex --target claude-code`, comma-separated values such as `--target codex,claude-code`, and `--target all`. The canonical documented form is repeated flags; comma-separated values are accepted for convenience.

## Consequences

`all` means all targets compatible with the selected plugin or selected components, not every target Harness knows globally. Harness must resolve target compatibility before writing files so target-specific components are not installed into incompatible agents.
