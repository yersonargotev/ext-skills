# Separate installed list from catalog view

Harness `list` will show installed plugins/components by default, while `catalog` will show available curated plugins and plugin details. This separates installed state from available catalog discovery.

## Consequences

The CLI remains predictable: `list` answers “what is installed?”, and `catalog` answers “what can I install?”. Catalog browsing gets room to grow without making installed-state output noisy.
