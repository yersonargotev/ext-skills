# Separate installed list from plugin status

Harness `list` will show a summarized view of installed plugins and components. Detailed diagnostics such as drift, pending manual actions, targets, backups, and origin operation IDs belong in `harness status <plugin>`.

## Consequences

The default installed-state view stays readable, while status provides the depth needed for troubleshooting, repair, update, and rollback decisions. `harness status` must verify the current filesystem and configuration against lockfile integrity metadata instead of only echoing lockfile contents.
