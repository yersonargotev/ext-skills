# Expose profile membership in plugin details

`harness catalog <plugin>` plugin detail output should show a plugin's Catalog Profile membership metadata, such as `role:frontend` and `technology:react`, so users can audit why the plugin appears in profile-filtered discovery contexts. This is transparency metadata only: profile membership remains a discovery concern and does not change install behavior, dependency selection, or default install semantics.
