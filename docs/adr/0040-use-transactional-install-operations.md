# Use transactional install operations

Harness install, update, remove, and rollback operations must behave as recoverable transactions. If an operation fails after writing assets, links, lockfile state, or target-agent configuration, Harness will roll back every change made by that operation before returning failure.

## Consequences

This makes failures safer and easier to reason about, but requires Harness to track each planned mutation and its inverse before applying changes. Dry runs should report the same ordered mutation plan that a real transaction would execute.
