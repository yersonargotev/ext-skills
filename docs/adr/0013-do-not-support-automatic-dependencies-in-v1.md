# Do not support automatic dependencies in v1

Harness v1 will not resolve or install plugin/component dependencies automatically. Manifests may include recommendations or manual setup guidance, but `add` will not perform transitive installs.

## Consequences

V1 avoids package-manager complexity such as version solving, dependency cycles, conflict resolution, and safe removal of shared dependencies. Plugin authors must keep v1 plugins self-contained or document manual setup clearly. Required closure inside a single selected plugin is not automatic dependency resolution; it is validation of the selected plugin's own required components.
