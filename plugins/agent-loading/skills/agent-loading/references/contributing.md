# Contributing and Issue Guidance

## Filing a Feature Request

When no plugin matches the user's intent, suggest filing a GitHub issue.

### Before Creating an Issue

REQUIRED: Search existing issues first using the GitHub MCP server.

Search query: the user's intent keywords + "plugin" in the `awslabs/agent-plugins` repository.

If a matching issue exists:

- Link to the existing issue
- Suggest the user add a thumbs-up reaction to signal demand
- Do NOT create a duplicate

### Issue Template

If no existing issue matches, create a new one (with user confirmation):

**Title**: `Plugin request: {brief description of capability}`

**Body**:

```markdown
## Requested Capability

{Description of what the user wants to do}

## Use Case

{Why this plugin would be valuable}

## Suggested Keywords

{Keywords that would trigger this plugin}

---

Filed via the agent-loading plugin.
```

**Labels**: `enhancement`, `plugin-request`

### Repository Link

Direct users to: `https://github.com/awslabs/agent-plugins/issues`

## Contributing a New Plugin

For users interested in building the plugin themselves:

1. Fork the repository: `https://github.com/awslabs/agent-plugins`
2. Follow the development guide: `docs/DEVELOPMENT_GUIDE.md`
3. Review design guidelines: `docs/DESIGN_GUIDELINES.md`
4. Use existing plugins as templates (`deploy-on-aws`, `amazon-location-service`)
5. Submit a pull request

### Plugin Structure Quick Reference

```
plugins/{plugin-name}/
├── .claude-plugin/
│   └── plugin.json
├── .mcp.json              # If MCP servers needed
└── skills/
    └── {skill-name}/
        ├── SKILL.md
        └── references/
```

### Quality Requirements

- `mise run build` must pass
- Plugin manifest validates against schema
- Skill descriptions include specific trigger phrases
- SKILL.md under 300 lines
- Reference files under 100 lines each
