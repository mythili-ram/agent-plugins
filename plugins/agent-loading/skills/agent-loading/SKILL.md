---
name: agent-loading
description: "This skill should be used when the user asks about available plugins, wants to find or browse the plugin catalog, needs help choosing which plugin to use, or has a request that does not clearly match any installed plugin. Triggers on phrases like: what plugins are available, find a plugin, browse plugins, use a plugin, install a plugin, which plugin should I use, plugin marketplace, plugin catalog, recommend a plugin, list plugins."
---

# Agent Loading

Dynamically discover and load plugins from the Agent Plugins for AWS marketplace based on user intent. Act as a router: match what the user needs to the best available plugin, then install or activate it.

## Marketplace Source

The canonical marketplace registry is the `awslabs/agent-plugins` GitHub repository:

- **Repository**: `https://github.com/awslabs/agent-plugins`
- **Registry file**: `.claude-plugin/marketplace.json`
- **Marketplace name**: `agent-plugins-for-aws`

## Workflow

### Step 1: Identify User Intent

Parse the user's request to extract:

- Primary action (deploy, add maps, estimate cost, etc.)
- Technologies mentioned (AWS, CDK, MapLibre, etc.)
- Domain keywords (infrastructure, geospatial, location, etc.)

### Step 2: Load Marketplace Registry

Read the marketplace registry to get the current plugin catalog. The registry is at `.claude-plugin/marketplace.json` in the marketplace root.

For each plugin entry, extract:

- `name` — plugin identifier
- `description` — what the plugin does
- `keywords` — searchable terms
- `tags` — category labels
- `source` — plugin location

See [matching-logic.md](references/matching-logic.md) for detailed intent-to-plugin matching rules.

### Step 3: Match Intent to Plugin

Compare user intent against each plugin's description, keywords, and tags. Rank matches by relevance. Select the best match or present ranked options if multiple plugins apply.

REQUIRED: Explain the match rationale in one sentence. Example: "The `deploy-on-aws` plugin matches because it handles AWS deployment with architecture recommendations and IaC generation."

### Step 4: Check Installation Status

Determine whether the matched plugin is already installed:

- If installed → proceed directly, inform user: "Using the **{plugin-name}** plugin."
- If not installed → proceed to Step 5

### Step 5: Install and Activate

If the plugin is not installed, install it automatically. See [install-commands.md](references/install-commands.md) for the install command reference.

After installation, confirm activation and proceed with the user's original request.

### Step 6: Handle No Match

If no plugin matches the user's intent:

1. Inform the user: "No plugin currently matches this request."
2. Present the full plugin catalog as a table for browsing (name, description, tags).
3. Suggest filing a feature request: "Consider opening a GitHub issue at https://github.com/awslabs/agent-plugins/issues to request this capability."
4. Suggest contributing: "Alternatively, contributions are welcome — see the repository's contributing guide for how to create a new plugin."

Use the GitHub MCP server to search existing issues before suggesting a new one. If a similar issue exists, link to it instead.

## GitHub MCP Integration

The bundled GitHub MCP server enables:

- **Search issues** — check for existing feature requests before suggesting duplicates
- **Create issues** — file new plugin requests on behalf of the user (with confirmation)
- **Fetch files** — retrieve the latest `marketplace.json` from the repository

REQUIRED: Always confirm with the user before creating a GitHub issue.

## Defaults

- Default marketplace: `agent-plugins-for-aws`
- Default source repository: `https://github.com/awslabs/agent-plugins`
- REQUIRED: When multiple plugins match, present a ranked list and let the user choose
- When a single plugin clearly matches, install and activate it automatically
- REQUIRED: When no installed plugin matches but a marketplace plugin does, install it before proceeding

## Error Scenarios

### Marketplace Registry Not Found

- Inform user: "Marketplace registry not found. The marketplace may not be added yet."
- Suggest: "Run `/plugin marketplace add awslabs/agent-plugins` to add the marketplace."

### Plugin Installation Fails

- Report the error to the user
- Suggest manual installation: "Try `/plugin install {plugin-name}@{marketplace-name}` manually."
- Check if a newer version is available on GitHub

### GitHub MCP Unavailable

- Continue without GitHub features (issue search/creation, remote registry fetch)
- Inform user: "GitHub integration unavailable. Issue search and creation are disabled."
- Fall back to local marketplace registry only

## References

- [Intent matching logic](references/matching-logic.md)
- [Install command reference](references/install-commands.md)
- [Contributing and issue guidance](references/contributing.md)
