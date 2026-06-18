# Use canonical profile IDs in filter contracts

Catalog profile filters use exact canonical profile IDs in command contracts, such as `role:frontend` or `technology:react`, instead of accepting human aliases like `fe`, `front`, or `reactjs` as valid filter values. Aliases can support textual search and suggestion UX that guides users to the canonical ID, but they do not become stored values or contract values, which keeps profile semantics stable and prevents shorthand drift from leaking into durable catalog behavior.
