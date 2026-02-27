# Plugin Install Command Reference

## Prerequisites

The marketplace must be added before plugins can be installed:

```
/plugin marketplace add awslabs/agent-plugins
```

## Install a Plugin

```
/plugin install {plugin-name}@{marketplace-name}
```

### Examples

```
/plugin install deploy-on-aws@agent-plugins-for-aws
/plugin install amazon-location-service@agent-plugins-for-aws
/plugin install agent-loading@agent-plugins-for-aws
```

## Check Installed Plugins

To verify which plugins are currently installed and enabled, check the project's `.claude/settings.json` file for the `enabledPlugins` array.

## Test a Plugin Locally

For development or testing without marketplace installation:

```bash
claude --plugin-dir ./plugins/{plugin-name}
```

## Troubleshooting

### "Marketplace not found"

Run: `/plugin marketplace add awslabs/agent-plugins`

### "Plugin not found in marketplace"

- Verify the plugin name matches exactly (kebab-case)
- Check that the marketplace registry includes the plugin
- The marketplace may need updating — fetch latest from GitHub

### "Plugin already installed"

The plugin is ready to use. No action needed — proceed with the user's request.
