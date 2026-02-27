---
name: browse-plugins
description: "Browse the full Agent Plugins for AWS marketplace catalog. Lists all available plugins with descriptions, keywords, and installation status."
allowed-tools: "Read Bash"
---

# Browse Plugins

Display the full plugin catalog from the Agent Plugins for AWS marketplace.

## Instructions

1. Read the marketplace registry at `.claude-plugin/marketplace.json` in the marketplace root
1. For each plugin in the registry, present a summary table with columns: Plugin, Description, Tags, Installed?
1. Check `.claude/settings.json` in the current project for `enabledPlugins` to determine installation status
1. Mark each plugin as "Installed" or "Not installed"
1. After displaying the table, inform the user:
   - To install a plugin: `/plugin install {name}@agent-plugins-for-aws`
   - To request a new plugin: open an issue at `https://github.com/awslabs/agent-plugins/issues`
   - To contribute a plugin: see `https://github.com/awslabs/agent-plugins` contributing guide
