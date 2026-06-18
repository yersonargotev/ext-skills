# Store each plugin under `catalog/plugins/<plugin-name>/`

Each curated plugin will live in its own directory under `catalog/plugins/<plugin-name>/`, with its manifest at `catalog/plugins/<plugin-name>/harness.plugin.json` and plugin-owned assets below the same directory.

## Consequences

Plugin assets stay isolated and easy to validate: every path declared by a manifest should resolve within that plugin directory. The catalog is slightly more verbose, but safer to package, audit, and evolve.
