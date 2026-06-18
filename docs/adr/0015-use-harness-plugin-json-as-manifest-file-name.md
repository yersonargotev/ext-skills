# Use `harness.plugin.json` as the manifest file name

Harness plugin definitions will use `harness.plugin.json` as the manifest file name. The name is explicit to Harness, avoids collisions with generic or agent-specific `plugin.json` files, and keeps JSON Schema validation straightforward.

## Consequences

The manifest file name is longer than `plugin.json`, but clearer and safer in repositories that may contain multiple agent/plugin ecosystems.
