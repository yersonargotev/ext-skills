# Block on drift until explicit repair

When Harness detects drift between the Harness Lockfile integrity metadata and the installed files or target-agent configuration, it will stop before applying further mutations. Harness will not silently repair or overwrite drifted state; the user must choose an explicit repair flow.

## Consequences

This protects user changes and preserves evidence of unexpected mutations, but it means update, remove, and rollback commands may refuse to proceed until drift is resolved. In v1, `harness repair` restores Harness-owned store assets and configuration from the catalog, lockfile, and recorded history; it does not attempt to merge manual edits. `--force` is not a drift-resolution mechanism.
