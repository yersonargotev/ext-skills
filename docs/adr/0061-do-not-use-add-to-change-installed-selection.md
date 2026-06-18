# Do not use add to change installed selection

When `harness add <plugin>` is run for a plugin that is already installed, Harness will only treat it as a no-op if the requested selection, targets, scope, and installation method match the installed state. If the request differs, Harness will fail and direct the user to an explicit future reconfiguration flow instead of using `add` to change installed selection.

## Consequences

`add` remains an installation command, not an ambiguous reconfiguration command. Changing installed shape becomes an explicit user decision rather than an accidental side effect of repeating add with different flags.
