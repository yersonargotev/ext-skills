# Use `--target` for installation targets

Harness CLI will use `--target` to select installation targets such as `codex` and `claude-code`. This matches the domain language of target adapters and avoids overloading “agent” with scope or runtime concepts.

## Consequences

The CLI is slightly more technical than `--agent`, but more precise and consistent with the adapter architecture.
