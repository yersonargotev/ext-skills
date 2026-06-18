# Default installation scope to project-local

Harness will default installations to project-local scope. Global installation must be explicit with a global flag.

## Consequences

The default is safer because plugin effects stay inside the current project unless the user deliberately opts into cross-project behavior. Harness must still support global installation for reusable personal or team setups.
