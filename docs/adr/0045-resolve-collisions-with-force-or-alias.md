# Resolve collisions with force or alias

Harness v1 will resolve installation collisions only through explicit user choices: `--force` to replace the colliding non-Harness-owned state, or `--alias <name>` to install the selected component under another name. Harness will not silently overwrite, skip, or auto-rename colliding components. `--force` applies only to collisions; drift must be resolved through `repair`. `--alias <name>` applies to the user-facing component name or invocation entry that collided for the selected target; it does not rename the plugin or mutate the catalog manifest.

## Consequences

The v1 resolution model stays small and predictable. Users must make ownership-changing decisions explicitly, and automatic naming surprises are avoided.
