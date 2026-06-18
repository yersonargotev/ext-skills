# Update installed plugins while preserving lockfile selection

`harness update` will update plugins that are already installed, using the Harness Lockfile to preserve the user's previous component and target selection while using the curated package catalog to find available plugin versions. It may add newly required components when a newer plugin version requires them, but it will not automatically install optional components or unrelated plugins; catalog updates happen by updating the `@grupo-exito/harness` package.

## Consequences

Update behavior is predictable and avoids silently widening the user's installation. This makes the lockfile the source of installed-state truth, while package versioning remains the source of catalog freshness.
