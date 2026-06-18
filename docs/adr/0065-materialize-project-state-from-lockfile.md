# Materialize project state from lockfile

When a project contains `.harness/lock.json` but local operational artifacts such as `.harness/store/` are missing, Harness will treat the project as needing materialization. `harness sync` will recreate store assets, links, and target configuration from the versioned lockfile and curated catalog without changing the selected plugins or components.

## Consequences

Cloned projects can reproduce their intended Harness plugin state without committing local artifacts. `harness status` must distinguish missing materialization from drift: missing local artifacts are expected after clone, while mismatched artifacts indicate drift. If the installed `@grupo-exito/harness` package catalog cannot provide the plugin version required by the lockfile, `sync` must fail and ask the user to install a compatible Harness package version instead of silently updating or substituting plugin versions.
