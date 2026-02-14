# Business Growth Plugin Marketplace

A plugin marketplace providing AI-powered agents and skills for sales & marketing automation.

Part of the [AgentSkills.io](https://agentskills.io/home) ecosystem.

> **Note:** While optimized for [Claude Code](https://claude.com/claude-code), the skills in this marketplace can be used with any compatible AI assistant (openClaw, etc.).

## Available Plugins

| Plugin | Description |
|--------|-------------|
| [opportunity-master](./opportunity-master/) | Sales automation with SDR and Account Executive agents for LinkedIn prospecting and pipeline management |
| [ad-alchemist](./ad-alchemist/) | Expert advertising agent for Meta, Google, X.com, and YouTube paid campaigns |
| [community-pulse](./community-pulse/) | Social media marketing agent for community engagement across platforms (Reddit, LinkedIn, X, etc.) |

## Installation

### Recommended: Install via Skills CLI

For any skills-supporting agent (Claude Code, openClaw, etc.):

```bash
npx skills add https://github.com/Zuttam/business-growth-mp
```

### Alternative: Claude Code Native Plugin

If you're using Claude Code, add to your project's `.claude/settings.json`:

```json
{
  "enabledPlugins": {
    "opportunity-master@business-growth-marketplace": true
  }
}
```

### Alternative: Plugin Directory Flag

```bash
claude --plugin-dir /path/to/business-growth-marketplace/opportunity-master
```

### Alternative: Clone and Reference

```bash
git clone https://github.com/Zuttam/business-growth-mp.git
```

Then reference in your Claude Code configuration.

## Prerequisites

- **Browser MCP** - A browser automation MCP is required for web interactions (LinkedIn, Reddit, etc.). Supported options include:
  - [Claude in Chrome Extension](https://chromewebstore.google.com/detail/claude-in-chrome) (Recommended)
  - [Playwright MCP](https://github.com/microsoft/playwright-mcp)
  - Any other browser automation MCP
- Active sessions in the browser for relevant platforms (LinkedIn, Reddit, X, etc.)

## Quick Start

Once installed, you can use the available skills directly in Claude Code:

```
# Build a lead list
/opportunity-master:list-building VP Engineering at Series B SaaS companies

# Create an outreach campaign
/opportunity-master:campaign-creation list_vp_engineering_series_b

# Research a prospect
/opportunity-master:lead-research https://linkedin.com/in/johndoe

# Execute campaign actions
/opportunity-master:campaign-execution campaign_q1_outreach run
```

## Plugin Structure

```
business-growth-marketplace/
├── .claude-plugin/
│   └── marketplace.json      # Marketplace registry
├── opportunity-master/       # Sales automation plugin
├── ad-alchemist/            # Paid advertising plugin
├── community-pulse/         # Social media engagement plugin
└── README.md                # This file
```

## Creating Your Own Plugin

Want to add a plugin to this marketplace? See the plugin structure above and create a new directory with:

1. `.claude-plugin/plugin.json` - Plugin manifest
2. `agents/` - Agent definitions (optional)
3. `skills/` - Skill implementations (optional)
4. `commands/` - Slash commands (optional)
5. `hooks/` - Event hooks (optional)
6. `README.md` - Documentation

Then add your plugin to `.claude-plugin/marketplace.json`.

## Resources

- [AgentSkills.io](https://agentskills.io/home) - Browse and discover agent skills
- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [Plugin Development Guide](https://docs.anthropic.com/en/docs/claude-code/plugins)

## License

MIT License - See [LICENSE](./LICENSE) for details.

## Author

Matan Zutta