# REM Sleep — a Claude Code skill

A [Claude Code](https://claude.com/claude-code) skill that lets an AI agent do what sleep does for a brain: take the raw episodic trace of a session and turn it into durable, well-organized, low-noise long-term memory — while detaching the emotional charge from the events, so the lessons survive but the friction doesn't.

It's the **inward** counterpart to outward-crawling discovery skills (like [octopus investigation](https://github.com/thdelmas/open-source-octopus-investigation)). Instead of reaching into the world, the agent processes its own day.

## The three jobs of sleep

- **Memory consolidation** — move what matters from the session (short-term) into the long-term store, in atomic, retrievable form.
- **Learning** — integrate: cross-link memories, and surface patterns no single episode contained.
- **Emotional regulation** — recalibrate. REM detaches the affective charge from the memory of an event; you keep the lesson, not the sting.

## Why it works

- **Consolidate, don't hoard** — sleep is as much for forgetting as remembering; a pruned store recalls better.
- **One fact per memory** — atomic and retrievable beats complete and tangled.
- **Link liberally** — memory is a graph, not a list; dangling links mark future work.
- **Separate the lesson from the sting** — keep the guidance, release the charge.
- **Dream lightly** — recombination is creative and valuable, but low-stakes; surface it, don't commit it.

## The long-term store

The skill operates on a **file-based agent memory store** — by default an index `MEMORY.md` (one line per memory) plus one fact per file with frontmatter (`name`, `description`, `type`). If your store uses another format, the skill asks once and adapts — the sleep *stages* are format-agnostic.

## Install

Works with **Claude Code**, **Codex**, and **Cursor**. Clone the repo once, then install for your tool(s):

```bash
git clone https://github.com/thdelmas/rem-sleep.git
cd rem-sleep
```

### Claude Code

Claude skills are a folder containing `SKILL.md`. Copy it into your skills directory:

```bash
# Global (all projects)
mkdir -p ~/.claude/skills/rem-sleep
cp SKILL.md ~/.claude/skills/rem-sleep/

# Or per-project: .claude/skills/rem-sleep/SKILL.md
```

Invoke with `/rem-sleep`, or just say *"sleep on it"* / *"consolidate the session"*.

### Codex

Codex skills use the **same `SKILL.md` format** as Claude — only the directory differs:

```bash
# User scope (all repos)
mkdir -p ~/.agents/skills/rem-sleep
cp SKILL.md ~/.agents/skills/rem-sleep/

# Or per-repo: .agents/skills/rem-sleep/SKILL.md
```

### Cursor

Cursor uses plain-markdown commands. Copy the command file:

```bash
# Global (all projects)
mkdir -p ~/.cursor/commands
cp cursor/rem-sleep.md ~/.cursor/commands/

# Or per-project: .cursor/commands/rem-sleep.md
```

Type `/` in Cursor's chat and pick **rem-sleep**.

## The cycle

See [`SKILL.md`](./SKILL.md) for the full process. Sleep runs in cycles of NREM (consolidation, pruning) then REM (integration, emotional). In short:

1. **Sleep onset — replay** — re-read the day; list the salient episodes before judging them.
2. **NREM — consolidate** — move durable facts into long-term memory, atomic; skip what's already written.
3. **Synaptic downscaling — prune** — merge duplicates, update the stale, correct the contradicted.
4. **REM — integrate** — cross-link memories, name latent patterns, and dream one or two recombinations.
5. **REM — regulate** — keep the lesson, release the charge, recalibrate stance.
6. **Wake — dream journal** — report what consolidated, what was pruned, what connected, the emotional read, and the open loops.

## License

MIT
