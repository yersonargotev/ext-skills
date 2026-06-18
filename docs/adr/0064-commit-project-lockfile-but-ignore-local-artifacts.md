# Commit project lockfile but ignore local artifacts

Project-local installs will treat `.harness/lock.json` as versioned install state that can be committed with the project. Harness-managed local artifacts such as `.harness/store/`, `.harness/backups/`, `.harness/history.jsonl`, and `.harness/local-state.json` are local operational data and should be ignored by git by default.

## Consequences

Teams can share intended plugin selections through the project lockfile without committing materialized assets, backups, or machine-local operation history. Project-local lockfiles must record portable expected state such as plugin versions, selections, targets, and asset checksums, not absolute paths or machine-local data. ADR 0067 defines the separate machine-local state file. Harness should add or report the recommended `.gitignore` rules when project-local state is initialized, modifying only Harness-owned ignore entries and preserving unrelated project rules.
