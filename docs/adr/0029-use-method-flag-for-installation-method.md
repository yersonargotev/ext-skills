# Use `--method` for installation method

Harness CLI will use `--method symlink` and `--method copy` for installation method, with symlink as the default. This keeps method explicit and aligned with the `--target` and `--scope` option style.

## Consequences

`--method copy` is longer than a boolean `--copy`, but it is clearer and leaves room for future methods if needed.
