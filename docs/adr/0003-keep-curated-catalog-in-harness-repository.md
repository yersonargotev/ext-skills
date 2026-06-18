# Keep the curated plugin catalog in the Harness repository

The curated Éxito plugin catalog will live in the same repository as `@grupo-exito/harness` and ship inside the published npm package for v1. This keeps the first version simple: one package owns the CLI, manifest schema, adapters, and approved plugin definitions.

## Consequences

Catalog and CLI releases are coupled, which simplifies versioning, review, and offline-ish installation at the beginning. The package may become heavier and catalog updates require a package release; if that becomes painful, the catalog can later move behind a remote registry or separate repository.
