# Use Éxito Plugin Manifest as the source of truth

We will model installable agent behavior with an Éxito-owned plugin manifest instead of using a Claude, Codex, Skills CLI, or MCP-specific manifest as the central contract. This keeps the curated plugin catalog independent from any one agent ecosystem, while installer adapters translate the manifest into each target agent's expected skills, MCP servers, sub-agents, commands, hooks, and configuration.

## Considered Options

- Reuse the `skills` CLI model directly as the product model.
- Fork or adapt `autoskills` around auto-detected skills.
- Define an Éxito-owned plugin manifest and build agent adapters around it.

## Consequences

The CLI has more upfront design work because it needs a manifest schema and target-agent adapters. In exchange, Éxito owns the domain model and can support plugins that include more than skills.
