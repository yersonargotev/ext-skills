# Distinguish update, drift, and collision

Harness will treat update, drift, and collision as separate states. If an existing entry is owned by Harness, appears in the Harness Lockfile, and matches recorded integrity metadata, Harness may update it transactionally. If an entry is Harness-owned but no longer matches recorded state, Harness treats it as drift and blocks until explicit repair. If an entry is not Harness-owned or is missing from the lockfile, Harness treats it as a collision and blocks until explicit resolution.

## Consequences

Harness updates only what it owns, refuses to overwrite manual state by default, and avoids mistaking user changes for normal upgrades.
