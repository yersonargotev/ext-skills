# Add invocation metadata for invocable components

Harness components may declare optional invocation metadata with `invocation.userInvocable` and `invocation.modelInvocable`. Target adapters translate this intent into agent-specific fields when supported, such as Claude Code `user-invocable: false` or `disable-model-invocation: true`.

## Consequences

Plugin authors can express invocation intent explicitly instead of relying on adapter guesses. If metadata is absent and a target adapter detects a user-facing collision, Harness should warn or apply a conservative target-specific default rather than silently exposing duplicate direct actions.
