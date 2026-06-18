# Version catalog plugins separately from schema

Each catalog plugin manifest will declare a plugin `version` using semantic versioning, separate from `schemaVersion`. Harness update compares the plugin version recorded in the Harness Lockfile against the plugin version available in the catalog.

## Consequences

Manifest compatibility and plugin release identity stay separate. Harness can reject unsupported manifest schemas while still comparing plugin versions for normal update decisions.
