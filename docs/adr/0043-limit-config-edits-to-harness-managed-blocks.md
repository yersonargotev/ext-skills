# Limit config edits to Harness-managed blocks

Harness will only modify marked Harness-managed sections in target-agent configuration files. Manual user configuration outside those marked blocks is out of scope for Harness edits, except that Harness may read it when needed to avoid collisions or report conflicts.

## Consequences

This keeps Harness from becoming an invasive config rewriter and makes ownership explicit. Target adapters must support marked block rendering or an equivalent ownership boundary for each agent configuration format.
