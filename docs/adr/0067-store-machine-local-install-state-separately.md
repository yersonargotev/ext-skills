# Store machine-local install state separately

Harness will keep portable project install state in `.harness/lock.json` and machine-local runtime state in `.harness/local-state.json`. Project-local state uses `.harness/lock.json`, `.harness/local-state.json`, `.harness/history.jsonl`, `.harness/store/`, and `.harness/backups/`. Global installs keep the same conceptual separation under `~/.config/harness/`, using `lock.json`, `local-state.json`, `history.jsonl`, `store/`, and `backups/`, even though all global files are machine-local. Manual action completion is local state, not committed project truth.

## Consequences

Project lockfiles stay portable across machines, while each checkout can track local facts such as completed manual runtime steps. ADR 0064 defines which project-local files are committed or ignored. Global installs use the same installed-state versus local-runtime-state model, reducing special cases. `harness sync` can recreate pending manual actions from the lockfile and local state can mark them completed for that machine.
