# Run non-interactively by default with dry run support

Harness commands will execute directly by default instead of asking for confirmation before writing files or configuration. Users can pass `--dry-run` to preview the resolved plan without modifying anything.

## Consequences

The CLI is fast and script-friendly. Harness must make `--dry-run` accurate and clear because it is the primary safety preview mechanism instead of an interactive confirmation step. A valid dry run exits with `0` even when it reports changes that would be applied; pending changes are information, not an error.
