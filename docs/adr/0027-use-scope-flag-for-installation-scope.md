# Use `--scope` for installation scope

Harness CLI will use `--scope project` and `--scope global` for installation scope, with project-local as the default. This keeps scope separate from target selection and installation method.

## Consequences

`--scope global` is slightly longer than `--global`, but it is clearer and keeps the CLI vocabulary consistent as Harness grows.
