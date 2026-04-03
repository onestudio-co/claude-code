# one-studio

A Claude Code plugin marketplace by [One Studio](https://one-studio.co).

## What is this?

This is a **marketplace** that distributes Claude Code plugins built by One Studio. Plugins are installed and updated directly from within Claude Code.

## Available Plugins

### `collection`

A collection of Claude Code skills including:

- **`/slim`** — Context Budget Auditor. Measures and compresses the token cost of your Claude Code agent system. Audits always-loaded files (`CLAUDE.md`, `MEMORY.md`, agent files, memory indexes), proposes a two-tier split, and compresses everything — without losing content.

See the [collection README](https://github.com/onestudio-co/collection) for full details.

## Installation

### 1. Add the marketplace

From within Claude Code:

```
/plugin marketplace add onestudio-co/claude-code
```

Or from the CLI:

```bash
claude plugin marketplace add onestudio-co/claude-code
```

### 2. Install a plugin

```
/plugin install collection@one-studio
```

### 3. Restart the session

After installing, **restart your Claude Code session** (`/exit` then relaunch) to load the new plugins.

> **Note:** The built-in `/reload-plugins` command _should_ reload newly added plugins without a restart, but it currently does not. This is a [known bug](https://github.com/anthropics/claude-code/issues/35641). Once the Anthropic team fixes it, you can use `/reload-plugins` instead of restarting.

### 4. Use the skills

```
/slim
```

## Update

```
/plugin marketplace update one-studio
```

Or from the CLI:

```bash
claude plugin marketplace update one-studio
```

## License

MIT
