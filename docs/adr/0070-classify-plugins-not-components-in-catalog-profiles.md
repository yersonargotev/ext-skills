# Classify plugins, not components, in catalog profiles

Harness catalog profiles will classify whole plugins rather than individual components such as skills, MCP servers, agents, or hooks. This keeps profiles aligned with the catalog's installable unit and avoids turning the first profile model into component-level curation, while plugin details can still expose the plugin's internal components during discovery.
