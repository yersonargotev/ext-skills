# Skip target-incompatible components

When resolving an install plan, Harness will omit components that are incompatible with the selected installation target and report those omissions in dry-run and install output. Target incompatibility is not an installation failure when at least one selected target and component combination remains valid.

## Consequences

Full plugin installs can work across mixed-target plugins without forcing every component to support every agent. Harness must make skipped components visible so users understand why the installed result differs from the plugin's full component list. If all selected components are skipped and the resolved install plan is empty, Harness must fail the plan instead of reporting success.
