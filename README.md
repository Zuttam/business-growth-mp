# Business Growth Marketplace

A plugin marketplace for [Claude Code](https://claude.com/claude-code) providing AI-powered agents and skills for B2B sales automation.

Part of the [AgentSkills.io](https://agentskills.io/home) ecosystem.

## What is a Plugin Marketplace?

A plugin marketplace is a collection of Claude Code plugins distributed together. Each plugin provides specialized agents, skills, and commands that extend Claude Code's capabilities for specific domains.

This marketplace focuses on **business growth and sales automation**, providing tools for:
- Lead generation and prospecting
- LinkedIn outreach campaigns
- Pipeline management
- Sales strategy and deal progression

## Available Plugins

| Plugin | Description |
|--------|-------------|
| [opportunity-master](./opportunity-master/) | Sales automation with SDR and Account Executive agents for LinkedIn prospecting and pipeline management |

## Installation

### Option 1: Add to Project Settings (Recommended)

Add to your project's `.claude/settings.json`:

```json
{
  "enabledPlugins": {
    "opportunity-master@business-growth-marketplace": true
  }
}
```

Then ensure the marketplace is accessible to Claude Code by placing it in a known plugins directory or referencing it directly.

### Option 2: Use Plugin Directory Flag

Run Claude Code with the plugin directory:

```bash
claude --plugin-dir /path/to/business-growth-marketplace/opportunity-master
```

### Option 3: Clone and Reference

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/business-growth-marketplace.git
   ```

2. Reference in your Claude Code configuration

## Prerequisites

- **Claude Code CLI** - Install from [claude.com/claude-code](https://claude.com/claude-code)
- **Claude in Chrome Extension** - Required for browser automation (LinkedIn interactions)
- Active LinkedIn session in browser

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
│   ├── .claude-plugin/
│   │   └── plugin.json      # Plugin manifest
│   ├── agents/              # SDR and AE agent definitions
│   ├── skills/              # Skill implementations
│   ├── hooks/               # Initialization hooks
│   └── README.md            # Plugin documentation
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