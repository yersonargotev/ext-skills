# Support `--except` for full install exclusions

Harness will support `--except type:id` to install a plugin except for specific components. Like `--only`, `--except` supports repeated flags and comma-separated values, with repeated flags as the canonical documented form.

## Consequences

`--except` is useful for mostly-full installs where only one component is unwanted. Harness must reject commands that combine `--only` and `--except`, because they express conflicting selection models.
