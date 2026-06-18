# Block plugin downgrades by default

Harness will block update plans that would replace an installed plugin with an older plugin version than the one recorded in the Harness Lockfile. Downgrades require an explicit user choice such as `--allow-downgrade`.

## Consequences

Harness avoids accidental regression when catalog contents or package versions move backward. Users can still intentionally downgrade, but the operation is visible and explicit. Rollback is not treated as an update downgrade; rollback follows its own recovery semantics and may restore an older version when targeting a recorded operation.
