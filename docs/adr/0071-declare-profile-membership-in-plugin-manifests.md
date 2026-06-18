# Declare profile membership in plugin manifests

Catalog profile membership lives in each plugin's `harness.plugin.json` rather than in a separate external profile index. This keeps curation versioned with the plugin it describes and avoids drift between the catalog/index and the plugin manifests as profiles or plugins evolve.
