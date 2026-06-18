# Support required components

Harness manifests may mark components as required with `required: true`. Required components cannot be excluded with `--except` in v1 because they are necessary for the plugin to function as intended.

## Consequences

Plugin authors can protect structural components from accidental omission. Harness must reject invalid selections before installation and explain clearly when a requested exclusion is rejected because the component is required. If softer guidance is needed later, it should use a separate concept such as recommended components, not weaken `required`.
