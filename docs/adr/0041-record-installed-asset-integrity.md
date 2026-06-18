# Record installed asset integrity

Harness will record checksums for installed plugin assets in the Harness Lockfile. Future update, remove, rollback, and verification flows can compare the lockfile checksums against the Harness Store to detect drift, tampering, or mismatched installed state.

## Consequences

Integrity metadata makes installed state auditable instead of trusting file presence alone. Operations that find checksum drift must stop before mutation and report the mismatch, unless the user explicitly chooses a repair flow.
