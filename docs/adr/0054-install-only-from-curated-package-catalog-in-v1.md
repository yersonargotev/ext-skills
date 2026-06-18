# Install only from the curated package catalog in v1

Harness v1 will install plugins only from the curated catalog shipped inside `@grupo-exito/harness`. It will not accept arbitrary URLs, local plugin paths, raw git repositories, or development-only local plugin installs such as `harness add ./local-plugin` as plugin sources.

## Consequences

Harness remains an Éxito-curated installer instead of becoming a generic plugin installer. This keeps trust, validation, and support boundaries clear, while leaving remote, custom, or development-link sources as a deliberate future decision outside v1.
