# Do not support recommended components in v1

Harness v1 will not support `recommended` component metadata. Components are either required, optional, included by full-plugin install, selected with `--only`, or excluded with `--except` when allowed.

## Consequences

The v1 selection model stays simpler and avoids soft semantics that do not affect installation behavior. If authors later need softer guidance, recommended components can be introduced as a separate concept without weakening `required`.
