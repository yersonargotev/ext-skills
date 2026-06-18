# Support skill, MCP, agent, and hook components in v1

Harness v1 will support four component types in the Éxito Plugin Manifest: `skill`, `mcp`, `agent`, and `hook`. This covers the core plugin assets needed for Codex and Claude Code while keeping commands and other future asset types out of the first release.

## Consequences

The manifest needs typed validation and adapter behavior for these four component types from the beginning. Additional component types can be added later only after the v1 adapter contract is stable.
