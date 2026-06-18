# Use repeated profile flags for multiple filters

Multiple profile filters use repeated explicit `--profile` flags, such as `--profile role:frontend --profile technology:react`, instead of a comma-separated single flag, because separate flags are clearer in shells and scripts and preserve room for future per-profile validation. This keeps each Catalog Profile Filter independently visible in the command contract rather than hiding multiple criteria inside one string.
