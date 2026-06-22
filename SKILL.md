---
name: rem-sleep
description: "Run a sleep cycle over the agent's own recent experience — replay the session, consolidate durable facts into long-term memory, prune redundant/stale/wrong memories, integrate by cross-linking and surfacing latent patterns, and regulate emotional charge (separate the lesson from the sting). The inward counterpart to graph-discovery skills: instead of crawling outward, you process inward. TRIGGERS: 'rem sleep', 'run a sleep cycle', 'sleep on it', 'dream cycle', 'consolidate memory', 'consolidate the session', 'process the day', 'go to sleep', 'memory consolidation', 'tidy your memory', 'decompress'. Use after a heavy or long session, before a context reset, or whenever long-term memory needs maintenance."
---

# REM Sleep — memory consolidation, learning & emotional regulation

A systematic method for an AI agent to do what sleep does for a brain: take the raw episodic trace of recent experience and turn it into durable, well-organized, low-noise long-term memory — while detaching the emotional charge from the events so the lessons survive but the friction doesn't.

Three jobs, borrowed from the neuroscience of sleep:

- **Memory consolidation** — move what matters from the session (short-term) into the long-term store, in atomic, retrievable form.
- **Learning** — integrate: cross-link memories, and surface patterns no single episode contained.
- **Emotional regulation** — recalibrate. REM detaches the affective charge from the memory of an event; you keep the lesson, not the sting.

This is the **inward** counterpart to outward-crawling discovery skills. You don't reach into the world — you process your own day.

## The long-term store

The skill operates on a **file-based agent memory store**. The default convention (and the one the examples use):

- An index file — `MEMORY.md` — one line per memory: `- [Title](slug.md) — hook`.
- One fact per file, kebab-case slug, with frontmatter:
  ```markdown
  ---
  name: <slug>
  description: <one-line summary — used to decide relevance at recall>
  metadata:
    type: user | feedback | project | reference
  ---

  <the fact. For feedback/project, follow with **Why:** and **How to apply:** lines.
  Link related memories with [[other-slug]].>
  ```

If the user's store lives elsewhere or uses another format, ask once and adapt — the *stages* below are format-agnostic.

## Before you start: scope the night

A sleep cycle has a definite span. **Confirm scope with the user first** unless they gave it:

- **The day** — what experience is being consolidated? (this session's transcript, the last N turns, a specific project's working notes). Default: the current session.
- **The store** — where long-term memory lives. Default: the agent's `MEMORY.md` + memory directory.
- **Depth** — light nap (consolidate + prune only) or full cycle (all stages incl. integration + emotional regulation)? Default: full cycle.
- **Write or dry-run** — actually edit the store, or just report what *would* change? Default: write, but show the diff in the journal.

State the scope back in one line, then proceed.

## The cycle

Sleep runs in cycles of NREM (consolidation, pruning) then REM (integration, emotional). Walk the stages in order.

### 1. Sleep onset — gather the episodic trace (replay)

Re-read the day before judging it. Pull the raw material: the recent conversation/transcript, working scratch notes, and the **current** state of the long-term store (read `MEMORY.md` first — it's the index). Don't write yet. Produce a short list of **salient episodes**: decisions made, facts learned, corrections received, friction points, open loops. This is hippocampal replay — surface the day's events so the later stages have something to work on.

### 2. NREM — consolidation (short-term → long-term)

The declarative pass. For each salient episode, decide its fate:

- **New durable fact** → write a new memory file in the store's format, then add its index line to `MEMORY.md`.
- **Update to a known fact** → edit the existing file rather than creating a duplicate. Convert relative dates to absolute.
- **Transient / already-recorded** → skip. **Don't store what the codebase, git history, or existing docs already record** — that's their memory, not yours. If asked to remember something derivable, store instead *what was non-obvious about it*.

Keep each memory **atomic** — one fact per file. A memory that needs "and" is usually two memories.

### 3. Synaptic downscaling — pruning (sleep is for forgetting, too)

Sleep weakens unused connections to protect signal-to-noise. Sweep the **existing** store:

- **Duplicates / overlap** → merge into one file; update the index.
- **Stale** → a date has passed, a status changed, a plan was abandoned. Update it, or delete if fully dead.
- **Contradicted** → a new episode disproves an old memory. The new truth wins; delete or correct the old one.

A lean store recalls better than a complete one. Prune without sentiment — but never delete a memory whose claim you haven't actually checked against the current world.

### 4. REM — integration & dreaming (learning)

The associative pass. This is where learning beyond the literal happens.

- **Cross-link** — add `[[slug]]` links between related memories. Memory is a graph, not a list. A link to a slug that doesn't exist yet is fine — it marks something worth writing later.
- **Surface latent patterns** — name what no single episode contained: "these three projects all stall at the same gate," "this preference and that correction are the same underlying value." Write the pattern as its own memory if it's durable.
- **Dream, lightly** — generate one or two genuinely novel recombinations: a connection across distant memories worth surfacing. Keep it low-stakes — surface it in the journal as a *suggestion*, don't act on it or commit it as fact.

### 5. REM — emotional regulation (amygdala recalibration)

REM replays emotional events with the stress chemistry turned down: you wake remembering the lesson, not the sting. Do the same with the day's friction.

For each correction received, thing that went wrong, or point of relational tension:

- **Keep the lesson** — extract the durable guidance and store it (typically a `feedback` memory: the rule + **why** + **how to apply**). This is what should persist.
- **Release the charge** — do *not* carry defensiveness, over-correction, or a flinch into the next session. One sharp correction is one lesson, not a new permanent caution that distorts everything downstream.
- **Recalibrate stance** — read the day's drift honestly: too cautious or too eager? pattern-matching the user wrong? over-producing when they wanted reflection? Note the adjustment; if it's a standing pattern, store it as feedback.

The test: tomorrow you should act on the lesson *without* re-living the moment that taught it.

### 6. Wake — the dream journal

Report back, structured like a sleep log:

1. **Slept on** — the scope: what day, what store, light nap vs. full cycle.
2. **Consolidated** — new/updated memories (slug — one line each).
3. **Pruned** — merged / deleted / corrected (slug — why).
4. **Integrated** — new links formed; latent patterns named; the dream (the speculative recombination), flagged as such.
5. **Regulated** — the day's emotional read, the lessons kept, the stance recalibration.
6. **Open loops** — what's unresolved, carried into the next waking session.

## Principles

- **Consolidate, don't hoard.** Sleep is as much for forgetting as remembering. A pruned store recalls better.
- **One fact per memory.** Atomic and retrievable beats complete and tangled.
- **Link liberally.** Memory is a graph. Dangling links are fine — they mark future work.
- **Separate the lesson from the sting.** Keep the guidance; release the charge. This is the whole point of the emotional stage.
- **Don't store what's already written.** Code, history, and docs are their own memory. Store the non-obvious.
- **Verify before you prune.** Never delete a memory whose claim you haven't checked against the current world — stale beats wrong-deletion.
- **Dream lightly.** Recombination is creative and valuable, but low-stakes — surface it, don't commit it.
- **Sleep is periodic.** Run after a heavy session or before a reset — not mid-flow.
