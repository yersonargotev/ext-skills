# Use a flat typed component list in the manifest

The Éxito Plugin Manifest will represent components as a flat `components` array where each component declares `type` and `id`. This maps directly to CLI selections such as `--only skill:code-review` and makes each component a first-class installable unit.

## Considered Options

- Group components by type under `components.skills`, `components.mcps`, `components.agents`, and `components.hooks`.
- Use a flat list with `type` and `id` on every component.

## Consequences

A flat list is slightly less visually grouped, but it is more extensible and better suited to discriminated-union validation. Future component types can be added without changing the overall manifest shape.
