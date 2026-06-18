# Project-local scope takes precedence over global

When the same plugin or component is installed both globally and project-locally, Harness treats the project-local installation as taking precedence while commands run inside that project. Global installed state remains available outside projects or when no project-local installation overrides it.

## Consequences

Project-specific choices can override a user's global defaults without mutating global state. Harness status and list commands must make scope visible so users can understand which installation is active. When a command such as `remove` runs inside a project without `--scope`, it applies to project-local state by default; touching global state requires `--scope global`.
