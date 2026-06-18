# Default installation method to symlink

Harness will default file installation to symlink and allow copy as an explicit alternative. Symlink keeps one source of truth for installed plugin assets and makes updates easier to reason about.

## Consequences

Symlink behavior must be tested across project and global scopes. Copy remains necessary for environments where symlinks are unsupported, undesirable, or confusing to users.
