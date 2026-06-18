# Version the Éxito Plugin Manifest schema from v1

Every Éxito Plugin Manifest must declare a schema version from v1 onward, such as `schemaVersion: "1.0"`. This separates manifest-format compatibility from plugin package/version semantics.

## Consequences

Harness can validate compatibility before installing and can support future migrations deliberately instead of guessing manifest shape from file contents.
