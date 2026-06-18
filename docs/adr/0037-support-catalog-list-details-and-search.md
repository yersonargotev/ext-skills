# Support catalog list, details, and search in v1

Harness v1 will include catalog discovery commands. `harness catalog` lists available curated plugins, `harness catalog <plugin>` shows plugin details, and `harness catalog search <query>` searches the curated catalog.

## Consequences

Catalog discovery is first-class instead of hidden inside `add`. This improves usability as the curated plugin catalog grows, while keeping installed-state listing separate through `harness list`.
