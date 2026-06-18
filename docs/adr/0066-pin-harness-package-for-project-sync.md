# Pin Harness package for project sync

Projects that commit `.harness/lock.json` should also pin `@grupo-exito/harness` as a project development dependency. The pinned package version provides the curated catalog used by `harness sync` to materialize the lockfile.

## Consequences

Project sync becomes reproducible because both desired plugin state and the catalog package that can provide it are versioned with the project. Floating `npx` usage remains useful for ad-hoc commands, but project-local synchronized installs should use the pinned package.
