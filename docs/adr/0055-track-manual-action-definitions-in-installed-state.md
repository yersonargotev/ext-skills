# Track manual action definitions in installed state

When a plugin requires a manual runtime command or setup step, Harness will record the manual action definition in installed state and track completion in machine-local state. For project-local installs, completion lives in an ignored local state file such as `.harness/local-state.json`, not in the committed lockfile. Harness still prints the command for the user to run manually and does not execute it.

## Consequences

`list`, `status`, update, repair, and verification flows can explain incomplete manual setup after the original install command exits. Harness will provide an explicit command such as `harness mark-complete <plugin> --action <id>` for users to mark manual actions completed; v1 will not try to detect completion automatically. For project-local sync on a different machine, manual actions are recreated as pending because completion is machine-local/runtime-local state, not portable project state.
