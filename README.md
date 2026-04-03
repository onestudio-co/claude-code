# one-studio

A Claude Code plugin marketplace by [One Studio](https://one-studio.co).

## What is this?

This is a **marketplace** that distributes Claude Code plugins built by One Studio. Plugins are installed and updated directly from within Claude Code.

## Available Plugins

### `collection`

A collection of Claude Code skills including:

- **`/slim`** — Context Budget Auditor. Measures and compresses the token cost of your Claude Code agent system. Audits always-loaded files (`CLAUDE.md`, `MEMORY.md`, agent files, memory indexes), proposes a two-tier split, and compresses everything — without losing content.

See the [collection README](plugins/collection/README.md) for full details.

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

### 3. Use the skills

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
