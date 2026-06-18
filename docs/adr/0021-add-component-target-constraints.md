# Add component target constraints

Harness components may declare target constraints with a `targets` array, such as `targets: ["claude-code"]`. This lets the manifest state when a component is only valid for specific supported agents.

## Consequences

Adapters do less guessing, and Harness can reject or skip incompatible selections before writing files. Components without target constraints may be treated as target-portable only when the component type and adapter support that behavior.
