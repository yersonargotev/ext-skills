# Do not execute managed MCP runtime commands in v1

Harness v1 will not execute MCP runtime installers or binary commands automatically. When an MCP component needs a runtime, Harness validates that the declared command is part of the curated catalog definition, writes the target-agent configuration, and prints the command the user must run manually.

## Consequences

This is safer for supply-chain control and keeps the user in charge of executing binaries. Installation may require one extra manual step, but Harness avoids silently running untrusted or surprising commands. Harness does not resolve, install, or execute transitive runtime packages in v1.
