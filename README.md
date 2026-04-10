# Pricefx Plugins

A marketplace registry of Claude Code plugins for Pricefx development workflows.

## Available Plugins

| Plugin | Description |
|--------|-------------|
| [pricefx-im-plugin](https://github.com/pricefx/pricefx-im-plugin) | Building, reviewing, debugging, and maintaining Pricefx Integration Manager projects |

## Installation

All commands below are run inside a Claude Code session (CLI or IDE).

### 1. Add the Pricefx marketplace

```
/plugin marketplace add pricefx/pricefx-plugins
```

This registers the marketplace so Claude Code knows about all available Pricefx plugins.

### 2. Install a plugin

```
/plugin install pricefx-im-plugin@pricefx-plugins
```

You can choose the installation scope (user, project, or local) during the interactive prompt.

### Useful commands

```
/plugin                                  # Open plugin manager UI
/plugin marketplace list                 # List configured marketplaces
/plugin marketplace update pricefx-plugins  # Refresh plugin catalog
/plugin disable pricefx-im-plugin@pricefx-plugins  # Disable without uninstalling
/plugin uninstall pricefx-im-plugin@pricefx-plugins  # Remove completely
/reload-plugins                          # Reload plugins without restarting
```

## Adding a New Plugin

1. Create a new plugin repository with a `.claude-plugin/` directory containing your plugin configuration (skills, agents, etc.).

2. Add an entry to `.claude-plugin/marketplace.json`:

```json
{
  "name": "your-plugin-name",
  "description": "Short description of what the plugin does",
  "version": "1.0.0",
  "category": "productivity",
  "source": {
    "source": "url",
    "url": "https://github.com/pricefx/your-plugin-repo.git"
  }
}
```

3. Submit a pull request to this repository.

## Repository Structure

```
.claude-plugin/
  marketplace.json    # Plugin registry with all available plugins
```

## License

Apache-2.0
