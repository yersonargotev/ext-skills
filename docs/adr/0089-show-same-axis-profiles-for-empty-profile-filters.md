# Show same-axis profiles for empty profile filters

When a user filters catalog discovery by a valid Catalog Profile and no plugins match, Harness will report no results and may show available profiles from the same axis, such as other `technology:*` values after an empty technology filter. We will not invent cross-axis recommendation magic because a valid empty filter should preserve the user's stated discovery intent instead of silently suggesting unrelated role, maturity, installation target, or endorsement concepts.
