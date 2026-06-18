# Install the full plugin by default and use `--only` for partial selection

When the user runs `harness add <plugin>` without `--only`, Harness will install every compatible component in the selected plugin. Partial installation is explicit through selectors such as `--only skill:review` or `--only mcp:jira`.

## Consequences

The default install path is simple and predictable: adding a plugin means installing the plugin. Users who want only part of a plugin must say so explicitly, which keeps scripted installs deterministic and avoids an interactive prompt in the default path.
