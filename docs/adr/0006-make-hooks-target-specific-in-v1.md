# Make hooks target-specific in v1

Harness v1 will model hook components as target-specific. Codex and Claude Code expose different hook/configuration surfaces, so the Éxito Plugin Manifest should not pretend hooks are portable before the adapter behavior proves it.

## Consequences

Hook components must declare their supported targets. A plugin can still include hooks for multiple agents, but each hook is validated and installed through the corresponding target adapter.
