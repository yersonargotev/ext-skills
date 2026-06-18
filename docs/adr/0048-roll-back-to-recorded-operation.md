# Roll back to a recorded operation

Harness rollback will restore state relative to a recorded Harness operation, referenced by an operation ID such as `--to-operation <id>`. Rollback will not mean “uninstall the latest plugin” or “undo whatever happened last” without an explicit recorded target.

## Consequences

Harness must record operation history with enough metadata to identify restore points and explain rollback effects before applying them. This keeps rollback recovery-oriented and separate from remove semantics.
