# Use a stable Harness Store for symlink sources

Harness symlink installs will point target-agent files to a stable Harness-managed store instead of pointing directly at npm package or `npx` cache paths. Project installs use `.harness/store/`; global installs use `~/.config/harness/store/`.

## Consequences

This adds a materialization step before linking, but it prevents installed plugins from breaking when package-manager cache paths are cleaned or replaced. The Harness Store becomes the durable source of installed plugin assets, while the package catalog remains the source for available plugin definitions.
