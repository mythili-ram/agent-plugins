# Agent Loading

Dynamically discover, recommend, and load plugins from the [Agent Plugins for AWS](https://github.com/awslabs/agent-plugins) marketplace based on user intent.

## Overview

The **agent-loading** plugin acts as a smart router for the plugin marketplace. Instead of requiring users to know which plugin to install, it automatically matches their intent to the best available plugin, installs it if needed, and hands off execution.

### The Problem

Users have a task ("deploy my app to AWS", "add a map to my site") but don't know which plugin handles it. They'd need to browse the catalog, read descriptions, and manually install — friction that slows adoption.

### The Solution

Agent-loading intercepts broad user intent, scores it against the full plugin catalog, and either activates an already-installed plugin or installs the right one on the fly.

## How It Works

### Agent Perspective

```
User says: "I want to host my Flask app on AWS"
         ↓
agent-loading skill auto-triggers (matches "host", "AWS")
         ↓
Reads marketplace.json → scores plugins by keyword/description/tag match
         ↓
Best match: deploy-on-aws (score: 9 — "aws", "deploy", "host" all match)
         ↓
Check: is deploy-on-aws installed?
  ├─ YES → "Using the deploy-on-aws plugin." → proceed
  └─ NO  → /plugin install deploy-on-aws@agent-plugins-for-aws → proceed
```

### User Perspective

#### Scenario 1: Plugin exists and is installed

> User: "Add a map with geocoding to my React app"
>
> Agent: "Using the **amazon-location-service** plugin. It handles maps, geocoding, routing, and geospatial features with Amazon Location Service."
>
> _(proceeds with location service skill)_

#### Scenario 2: Plugin exists but not installed

> User: "Deploy this to AWS"
>
> Agent: "The **deploy-on-aws** plugin handles AWS deployment with architecture recommendations, cost estimates, and IaC generation. Installing it now..."
>
> _(installs plugin, then proceeds with deploy skill)_

#### Scenario 3: No matching plugin

> User: "Set up monitoring for my application"
>
> Agent: "No plugin currently matches this request. Here's the full catalog:"
>
> | Plugin                  | Description                   | Tags                        |
> | ----------------------- | ----------------------------- | --------------------------- |
> | deploy-on-aws           | Deploy applications to AWS... | aws, deploy, infrastructure |
> | amazon-location-service | Maps, geocoding, routing...   | aws, location, maps         |
>
> "You can request this capability by opening an issue at https://github.com/awslabs/agent-plugins/issues, or contribute a plugin yourself."

#### Scenario 4: Browsing the catalog

> User: "/agent-loading:browse-plugins"
>
> Agent: _(displays full catalog table with installation status)_

## Components

### Skill: agent-loading

The core auto-triggering skill. Activates when the user asks about available plugins, needs help choosing which plugin to use, or has a request that doesn't clearly match any installed plugin.

**Auto-triggers on:** "what plugins are available", "find a plugin", "browse plugins", "which plugin should I use", "install a plugin", "recommend a plugin", "plugin catalog".

**Workflow:**

1. Parse user intent (action, technologies, domain keywords)
2. Load marketplace registry
3. Score plugins against intent using keyword/description/tag matching
4. Check installation status
5. Install if needed, or use existing
6. Hand off to the matched plugin's skill
7. If no match: show catalog, suggest issue, suggest contributing

### Command: browse-plugins

User-invocable slash command (`/agent-loading:browse-plugins`) to explicitly browse the full marketplace catalog without a specific intent.

Displays a table of all plugins with descriptions, tags, and installation status.

### MCP Server: GitHub

Integrates the official [GitHub MCP server](https://github.com/modelcontextprotocol/servers/tree/main/src/github) for:

- **Issue search** — find existing feature requests before creating duplicates
- **Issue creation** — file new plugin requests (with user confirmation)
- **File fetching** — retrieve the latest marketplace.json from the repository

## Installation

### Prerequisites

1. Add the marketplace (one-time):

   ```
   /plugin marketplace add awslabs/agent-plugins
   ```

2. Set a GitHub personal access token (for GitHub MCP features):

   ```bash
   export GITHUB_PERSONAL_ACCESS_TOKEN=<your-github-pat>
   ```

   The token needs `repo` scope for issue search and creation. GitHub MCP features are optional — the plugin works without them using the local registry only.

### Install

```
/plugin install agent-loading@agent-plugins-for-aws
```

### Test Locally

```bash
claude --plugin-dir ./plugins/agent-loading
```

## Configuration

No additional configuration required. The plugin reads the marketplace registry that was added via `/plugin marketplace add`.

### Optional: GitHub MCP

Set `GITHUB_PERSONAL_ACCESS_TOKEN` environment variable to enable:

- Searching existing GitHub issues before suggesting new ones
- Creating feature request issues on behalf of the user
- Fetching the latest marketplace registry from GitHub

Without this token, the plugin falls back to the local marketplace registry and skips issue-related features.

## Plugin Catalog

The plugin routes to all plugins registered in the `agent-plugins-for-aws` marketplace:

| Plugin                  | Category   | Description                                                                           |
| ----------------------- | ---------- | ------------------------------------------------------------------------------------- |
| deploy-on-aws           | deployment | Deploy applications to AWS with architecture recommendations, cost estimates, and IaC |
| amazon-location-service | location   | Maps, geocoding, routing, and geospatial features with Amazon Location Service        |

As new plugins are added to the marketplace, agent-loading automatically discovers and routes to them — no updates to this plugin are needed.

## Architecture

```
plugins/agent-loading/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── .mcp.json                    # GitHub MCP server configuration
├── commands/
│   └── browse-plugins.md        # /browse-plugins slash command
├── skills/
│   └── agent-loading/
│       ├── SKILL.md             # Core routing skill (auto-triggers)
│       └── references/
│           ├── matching-logic.md    # Intent scoring algorithm
│           ├── install-commands.md  # Plugin install reference
│           └── contributing.md      # Issue/contribution guidance
└── README.md                    # This file
```

## Examples

### Trigger Phrases

The skill auto-triggers on a wide range of user intents:

- "Deploy my app to AWS"
- "Host this on AWS"
- "Add a map to my application"
- "I need geocoding for addresses"
- "What plugins are available?"
- "Find a plugin for..."
- "Estimate AWS costs"
- "Set up CDK infrastructure"
- "Add location features"
- "Route between two points"

### Testing the Skill

```bash
# Test with deploy intent
claude --plugin-dir ./plugins/agent-loading
> "Deploy my Flask app to AWS"
# Expected: matches deploy-on-aws, installs if needed, proceeds

# Test with location intent
> "Add a map with places search"
# Expected: matches amazon-location-service

# Test with no match
> "Set up a CI/CD pipeline"
# Expected: no match, shows catalog, suggests issue

# Test browse command
> /agent-loading:browse-plugins
# Expected: full catalog table
```

## Contributing

To add a new plugin that agent-loading can route to:

1. Create the plugin in `plugins/{plugin-name}/`
2. Add it to `.claude-plugin/marketplace.json`
3. Include descriptive `keywords` and `tags` for accurate matching
4. Submit a pull request

See [DESIGN_GUIDELINES.md](../../docs/DESIGN_GUIDELINES.md) and [DEVELOPMENT_GUIDE.md](../../docs/DEVELOPMENT_GUIDE.md) for detailed guidance.
