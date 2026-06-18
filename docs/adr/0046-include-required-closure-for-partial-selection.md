# Include required closure for partial selection

When a user installs a partial selection with `--only`, Harness will include any required components needed for the selected components to function. Required components remain mandatory even when they were not explicitly listed in the user's `--only` filter.

## Consequences

Partial selection is a filter over optionality, not permission to create a broken install. Harness must explain required additions in dry-run and install output so users can see why more components were installed than they named.
