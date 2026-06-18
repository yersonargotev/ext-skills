# Use `type:id` as component identity

Harness component identity will be the pair of `type` and `id`, not `id` alone. A plugin may contain components such as `skill:review` and `agent:review` at the same time, while duplicate pairs like two `skill:review` components are invalid.

## Consequences

CLI selections map directly to the component key, for example `--only skill:review`. Target adapters may still apply target-specific invocation policies when a target exposes multiple component types through overlapping user-facing surfaces. For Claude Code, if a skill shares an id with another component that should own the direct user workflow, the Claude adapter should emit the skill as not user-invocable instead of exposing duplicate direct actions.
