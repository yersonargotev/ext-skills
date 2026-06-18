# Use `name` for plugins and `id` for components

Harness manifests will use `name` as the stable plugin identifier and `id` as the stable component identifier inside a plugin. CLI selections combine component type and id, such as `--only skill:code-review`.

## Consequences

Plugin identity and component identity stay distinct. This avoids ambiguous commands and keeps room for different component types to use the same id only if the manifest validation explicitly permits or rejects that case.
