# Allow partial remove with required closure validation

Harness v1 will allow removing selected components from an installed plugin, such as `harness remove <plugin> --only skill:x`, when doing so leaves the remaining installed state valid. If partial removal would break the required closure of the remaining installed components, Harness will fail the plan.

## Consequences

Users can trim installed plugins without removing everything, but Harness preserves functional integrity. Partial remove must use the same transaction, lockfile, integrity, and config ownership rules as full remove. If a partial remove removes every installed component for the plugin, Harness treats the result as a full remove and clears the plugin's current-state lockfile entry while preserving operation history.
