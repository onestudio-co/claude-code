# claude-code

A collection of Claude Code skills built by [One Studio](https://one-studio.co).

## What are Claude Code skills?

Skills are reusable prompts that extend Claude Code with domain-specific workflows. Drop a skill file into `.claude/commands/` and invoke it with `/skill-name` in any Claude Code session.

## Skills

### `/slim` — Context Budget Auditor

Measures and compresses the token cost of your Claude Code agent system.

Every agent spawn loads `CLAUDE.md` + `MEMORY.md` + the agent file + its memory index — all verbatim. As projects grow, these files accumulate detail that's only needed occasionally. `slim` audits all always-loaded files, proposes a two-tier split (fast-tier always loaded, slow-tier read on demand), and compresses agent files and memory indexes — without losing any content.

**Run it when:**
- Spawning an agent costs more tokens than expected
- `CLAUDE.md` has grown beyond ~5KB
- Agent files have accumulated protocol details that duplicate `CLAUDE.md`
- You want a monthly context hygiene pass

**What it does (6 phases):**
1. **Audit** — measures every always-loaded file, prints a token cost table sorted by impact
2. **CLAUDE.md split** — extracts reference material to `docs/claude/*.md`, keeps only the fast-tier in `CLAUDE.md`
3. **MEMORY.md compression** — collapses verbose entries to one-liners, removes dead links
4. **Agent file compression** — removes duplication with `CLAUDE.md`, cuts prose rationale, keeps domain-specific rules
5. **Memory index compression** — each entry to one line, under 80 lines per index
6. **Model right-sizing** — audits `model:` frontmatter per agent, recommends Haiku/Sonnet/Opus based on task type, documents a dynamic escalation pattern for edge cases

Interactive — proposes changes, waits for approval before writing each phase.

## Installation

Copy the skill file to your project's `.claude/commands/` directory:

```bash
cp skills/slim/SKILL.md /your-project/.claude/commands/slim.md
```

Then invoke in Claude Code:

```
/slim
```

## License

MIT
