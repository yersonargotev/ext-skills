# Allow managed MCP runtimes when needed

Harness MCP components may include the binary, package, or command needed to run the MCP server when configuration alone is not enough. This lets a curated plugin provide a complete MCP setup instead of assuming the user already installed the runtime manually.

## Consequences

Managed MCP runtimes increase supply-chain risk, so manifests must distinguish configuration-only MCPs from MCPs that install or invoke a runtime. Runtime sources, commands, and install behavior need validation before Harness writes them. ADR 0008 defines the v1 safety boundary: Harness prints managed runtime commands for manual execution and does not execute them automatically.
