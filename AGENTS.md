# Agent Guidelines

## Adding a New Plugin

When adding a new plugin to this marketplace:

1. Create the plugin directory (e.g., `my-plugin/`) with required structure:
   ```
   my-plugin/
   ├── .claude-plugin/
   │   └── plugin.json      # Plugin manifest
   ├── agents/              # Agent definitions (optional)
   ├── skills/              # Skill implementations (optional)
   ├── commands/            # Slash commands (optional)
   ├── hooks/               # Event hooks (optional)
   └── README.md            # Plugin documentation
   ```

2. Register the plugin in `.claude-plugin/marketplace.json`

3. **Update the root README.md:**
   - Add the plugin to the "Available Plugins" table with name, link, and description
   - Update the "Plugin Structure" section to include the new plugin directory
