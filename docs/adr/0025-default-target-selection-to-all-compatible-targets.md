# Default target selection to all compatible targets

When the user does not pass `--target`, Harness will default to all targets compatible with the selected plugin or selected components. This gives the simplest install path while still respecting component target constraints.

## Consequences

Harness must resolve compatibility before installation and clearly report which targets will be affected. The default is convenient, but target adapters must avoid writing incompatible target-specific components.
