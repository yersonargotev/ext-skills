# Éxito Agent Plugins

This context defines the language for the Éxito-owned agent plugin catalog and installer experience.

## Language

**Plugin**:
An installable unit of agent behavior approved for Éxito usage. A plugin may contain skills, MCP servers, sub-agents, commands, hooks, configuration, or other agent-specific assets.
_Avoid_: Skill when referring to the whole installable unit, extension, capability

**Curated Plugin Catalog**:
The Éxito-owned collection of approved plugins that users can browse, select, and install.
_Avoid_: Random upstream repo, raw marketplace, unfiltered skill list, capability catalog

**Installer CLI**:
The npm/npx command-line interface that installs selected catalog plugins into one or more supported agents.
_Avoid_: Catalog, registry

**Installation Target**:
The destination agent and scope selected during installation, such as Claude Code, Codex, GitHub Copilot, project-local, or global.
_Avoid_: Agent when also referring to scope, destination

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

**Harness Lockfile**:
The project or global record of installed plugins and selected components, including version, targets, scope, installation method, source, and integrity metadata. Project installs use `.harness/lock.json`; global installs use `~/.config/harness/lock.json`.
_Avoid_: Ad-hoc install log, cache

**Config Backup**:
A copy of any existing target-agent configuration file that Harness creates before modifying it. Project backups live under `.harness/backups/`; global backups live under `~/.config/harness/backups/`.
_Avoid_: Best-effort recovery, undocumented overwrite

**Rollback**:
A Harness command that restores target-agent configuration from a centralized backup created during installation.
_Avoid_: Uninstall, remove

**Remove**:
A Harness command that uninstalls selected plugin files and cleans target-agent configuration while preserving backup/history data needed for traceability or rollback.
_Avoid_: Rollback, delete everything

**Recommended Setup**:
Non-automatic manifest guidance that tells users what other plugins, components, or manual steps may improve or complete an installation.
_Avoid_: Automatic dependency, transitive install

**Schema Version**:
The explicit version of the Éxito Plugin Manifest format used by a plugin definition.
_Avoid_: Implicit manifest version, package version

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

**Installation Scope**:
Whether Harness installs into the current project or the user's global agent environment. Project-local is the default; global is selected with `--scope global`.
_Avoid_: Installation target, global flag only

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

**Dry Run**:
A non-writing execution mode where Harness resolves the requested install/update/remove plan and reports what would change without modifying files or configuration.
_Avoid_: Confirmation prompt, interactive install

**Catalog View**:
The CLI surface for browsing available curated plugins before installation, separate from listing installed state.
_Avoid_: Installed list, lockfile view
