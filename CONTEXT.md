# Éxito Agent Plugins

This context defines the language for the Éxito-owned agent plugin catalog and installer experience.

## Language

**Plugin**:
An installable unit of agent behavior approved for Éxito usage. A plugin may contain skills, MCP servers, sub-agents, commands, hooks, configuration, or other agent-specific assets.
_Avoid_: Skill when referring to the whole installable unit, extension, capability

**Curated Plugin Catalog**:
The Éxito-owned collection of approved plugins that users can browse, select, and install.
_Avoid_: Random upstream repo, raw marketplace, unfiltered skill list, capability catalog

**Catalog Source**:
The approved location Harness reads plugin definitions and assets from. In v1, the only supported catalog source is the curated catalog shipped inside `@grupo-exito/harness`.
_Avoid_: Arbitrary URL, local plugin source, raw git repository

**Harness Package Pin**:
The project dependency on a specific `@grupo-exito/harness` package version used to make project-local sync reproducible.
_Avoid_: Floating npx version, implicit latest package

**Installer CLI**:
The npm/npx command-line interface that installs selected catalog plugins into one or more supported agents.
_Avoid_: Catalog, registry

**Installation Target**:
The destination agent selected during installation, such as Codex or Claude Code.
_Avoid_: Installation scope, project-local, global, destination

**Installation Method**:
The file placement strategy selected during installation, such as symlink or copy.
_Avoid_: Install target, scope

**Éxito Plugin Manifest**:
The Éxito-owned manifest format that describes a plugin independently from any specific agent implementation. Agent-specific installers translate this manifest into each target agent's required files and configuration.
_Avoid_: Claude plugin manifest, Codex skill manifest, upstream manifest

**Component**:
A typed part inside a plugin, such as a skill, MCP server, agent, hook, command, app integration, or rule. Components are the internal manifest units that can be installed as part of a full plugin or selected individually.
_Avoid_: Plugin when referring to a single internal part, harness

**Selection**:
The user's install filter, such as installing a full plugin or only specific components using a type-and-name selector.
_Avoid_: Component when referring to the user's choice, harness

**Harness**:
The public CLI product that installs and manages Éxito plugins across supported agent targets. The npm package name is `@grupo-exito/harness`.
_Avoid_: exito-plugins, autoskills, skills CLI

**Target Adapter**:
The Harness module that translates the Éxito Plugin Manifest into files and configuration for a specific supported agent target.
_Avoid_: Plugin, component, installer

**Supported Component Type**:
A component type that Harness v1 knows how to validate and install. Harness v1 supports `skill`, `mcp`, `agent`, and `hook`.
_Avoid_: Arbitrary asset type, unsupported component

**Target-Specific Hook**:
A hook component whose behavior and installation format are defined for one supported agent target rather than shared across all targets.
_Avoid_: Portable hook, universal hook

**Managed MCP Runtime**:
An MCP component whose manifest includes the command, package, or binary needed to run the MCP server, not only the client configuration.
_Avoid_: Raw command, unverified binary

**Manual Runtime Command**:
A command that Harness prints for the user to run manually instead of executing automatically during installation.
_Avoid_: Automatic binary execution, postinstall execution

**Manual Action**:
A Harness-tracked setup step that the user must perform outside Harness because Harness does not execute it automatically.
_Avoid_: Automatic install, hidden prerequisite, recommendation

**Harness Lockfile**:
The project or global record of installed plugins and selected components, including version, targets, scope, installation method, source, and integrity metadata.
_Avoid_: Ad-hoc install log, cache, operation history

**Versioned Install State**:
Project-local Harness state that is intended to be committed with the project so the team shares the same installed plugin selection.
_Avoid_: Store assets, backups, operation history

**Local Install State**:
Machine-local Harness state that records runtime facts for one checkout, such as manual action completion.
_Avoid_: Versioned install state, portable lockfile, catalog metadata

**Materialization**:
The process of creating local Harness Store assets, links, and target configuration from versioned install state and the curated catalog.
_Avoid_: Fresh selection, catalog update, manual copy

**Sync**:
A Harness operation that materializes or reconciles local operational state from versioned install state without changing the user's selected plugins or components.
_Avoid_: Add, update, fresh install

**Integrity Metadata**:
Checksums recorded by Harness for installed plugin assets so future operations can detect drift, tampering, or mismatched installed state.
_Avoid_: Best-effort version check, timestamp comparison

**Drift**:
A mismatch between the installed plugin state recorded by Harness and the files or configuration currently found on disk.
_Avoid_: Normal update, expected local change, automatic repair

**Collision**:
A conflict where Harness would install a plugin component into a name, path, command, or target-agent entry already occupied by non-Harness-owned state.
_Avoid_: Update, drift, automatic rename

**Force Install**:
An explicit user choice that allows Harness to replace colliding non-Harness-owned state during an installation transaction.
_Avoid_: Drift repair, default overwrite, silent replacement

**Install Alias**:
An explicit alternate name chosen by the user to install a colliding component without replacing the existing state.
_Avoid_: Automatic rename, hidden suffix

**Repair**:
An explicit Harness operation that reconciles detected drift after the user chooses how to restore or replace mismatched installed state.
_Avoid_: Automatic fix, implicit overwrite

**Harness Store**:
The stable Harness-managed asset location used as the source for installed plugin files.
_Avoid_: npx cache, npm package cache, target agent directory

**Config Backup**:
A copy of any existing target-agent configuration file that Harness creates before modifying it.
_Avoid_: Best-effort recovery, undocumented overwrite

**Operation Backup**:
A config backup associated with one specific Harness operation ID.
_Avoid_: Shared backup, latest backup, overwrite-in-place backup

**Harness-Managed Config Block**:
The marked section of a target-agent configuration file that Harness owns and may modify.
_Avoid_: Whole config file, manual user config, unmarked entries

**Rollback**:
A Harness command that restores target-agent configuration from a centralized backup created during installation.
_Avoid_: Uninstall, remove

**Operation ID**:
The stable identifier for a recorded Harness transaction that can be referenced for audit, repair, or rollback.
_Avoid_: Timestamp only, latest install, implicit history

**Operation History**:
The append-only Harness record of completed and failed install, update, remove, repair, and rollback transactions.
_Avoid_: Current installed state, lockfile entry, mutable audit log

**Garbage Collection**:
An explicit maintenance operation that removes old Harness-managed store assets, backups, or history entries according to user-selected retention rules.
_Avoid_: Automatic pruning, silent cleanup, rollback

**Remove**:
A Harness command that uninstalls selected plugin files and cleans target-agent configuration while preserving backup/history data needed for traceability or rollback.
_Avoid_: Rollback, delete everything

**Partial Remove**:
A remove operation that uninstalls selected components from an installed plugin while leaving the rest of the plugin installed.
_Avoid_: Full remove, reconfigure, broken uninstall

**Recommended Setup**:
Non-automatic manifest guidance that tells users what other plugins, components, or manual steps may improve or complete an installation.
_Avoid_: Automatic dependency, transitive install

**Schema Version**:
The required explicit version of the Éxito Plugin Manifest format used by a plugin definition.
_Avoid_: Implicit manifest version, package version

**Plugin Version**:
The semantic version of a catalog plugin used to compare available plugin releases against installed lockfile state.
_Avoid_: Schema version, package version, catalog version

**Downgrade**:
An update operation that would replace an installed plugin with an older plugin version than the one recorded in the Harness Lockfile.
_Avoid_: Normal update, repair, rollback

**Harness Plugin Manifest File**:
The `harness.plugin.json` file that contains an Éxito Plugin Manifest.
_Avoid_: plugin.json, plugin.yaml

**Plugin Directory**:
The catalog folder for one plugin, located at `catalog/plugins/<plugin-name>/`, containing `harness.plugin.json` and all plugin-owned assets.
_Avoid_: Shared asset bucket, flat catalog

**Plugin Name**:
The stable catalog identifier for a plugin, used in commands such as `harness add <plugin-name>`.
_Avoid_: Component id

**Component ID**:
The stable identifier for a component within a plugin, used with its type in selections such as `--only skill:code-review`.
_Avoid_: Plugin name

**Component Key**:
The pair of `type` and `id` that uniquely identifies a component inside a plugin, such as `skill:review` or `agent:review`.
_Avoid_: Globally unique component id

**Target Invocation Policy**:
A target-adapter rule that controls whether an installed component is directly user-invocable, model-invocable, or hidden for that specific agent target.
_Avoid_: Global manifest behavior, naming workaround

**Invocation Metadata**:
Optional component metadata that declares whether a component should be directly user-invocable or model-invocable when the target adapter supports those concepts.
_Avoid_: Adapter guess, implicit invocation behavior

**Component Target Constraint**:
The component-level list of supported installation targets, used when a component is only valid for specific agents.
_Avoid_: Adapter inference, universal by accident

**Compatible Component**:
A plugin component whose target constraints allow installation into the selected installation target.
_Avoid_: Installed component, required component, selected component

**Skipped Component**:
A plugin component that Harness leaves out of an install plan because it is incompatible with the selected installation target.
_Avoid_: Failed component, removed component

**Installation Scope**:
Whether Harness installs into the current project or the user's global agent environment.
_Avoid_: Installation target, global flag only

**Scope Precedence**:
The rule Harness uses when project-local and global installed state both apply. Project-local state takes precedence over global state when commands run inside that project.
_Avoid_: Merge order, target selection, catalog priority

**Full Plugin Install**:
The default `add` flow when the user selects a plugin without an explicit `--only` filter. Harness installs every compatible component in the selected plugin.
_Avoid_: Interactive selection by default, partial install by accident

**Partial Selection**:
An explicit install filter declared with `--only type:id`, used when the user wants only specific components from a plugin.
_Avoid_: Default install, implicit component selection

**Exclusion Selection**:
An explicit install filter declared with `--except type:id`, used when the user wants a full plugin install minus specific components.
_Avoid_: Partial selection, only selection

**Required Component**:
A component that is necessary for the plugin to function as intended and cannot be excluded with `--except`.
_Avoid_: Recommended component, optional component

**Required Closure**:
The complete set of required components that Harness must include for a selected plugin or partial selection to function as intended.
_Avoid_: Recommended setup, optional dependency, transitive dependency

**Dry Run**:
A non-writing execution mode where Harness resolves the requested install/update/remove plan and reports what would change without modifying files or configuration.
_Avoid_: Confirmation prompt, interactive install

**Structured Output**:
Machine-readable Harness command output, such as JSON, intended for CI, automation, and agent consumption.
_Avoid_: Human-only logs, ad-hoc parsing

**Exit Code**:
A stable process status code Harness returns so scripts, CI, and agents can distinguish success, validation errors, drift, collisions, and lock contention.
_Avoid_: Generic failure only, message parsing

**Install Transaction**:
A single Harness install, update, remove, or rollback operation whose file and configuration changes are applied as one recoverable unit.
_Avoid_: Best-effort install, partial mutation, loose file copy

**No-op**:
A successful Harness operation that finds the requested state already satisfied and therefore makes no changes.
_Avoid_: Error, skipped failure, duplicate install

**Scope Lock**:
An exclusive guard that prevents concurrent Harness transactions from mutating the same project or global installation scope.
_Avoid_: Best-effort concurrency, optimistic overwrite

**Catalog View**:
The CLI surface for browsing available curated plugins before installation, separate from listing installed state.
_Avoid_: Installed list, lockfile view

**Installed List**:
The summarized CLI view of currently installed Harness plugins and components.
_Avoid_: Catalog view, diagnostic report, full lockfile dump

**Plugin Status**:
The detailed diagnostic CLI view for one installed plugin, including targets, manual actions, drift, backups, and operation history references.
_Avoid_: Catalog details, installed list, raw history

**Update**:
A Harness operation that refreshes already installed plugins according to the Harness Lockfile while preserving the user's previous component and target selection.
_Avoid_: Fresh install, catalog refresh, implicit new plugin install

**Reconfigure**:
A future Harness operation that intentionally changes an installed plugin's selected components, targets, scope, or installation method.
_Avoid_: Add, update, accidental reinstall
