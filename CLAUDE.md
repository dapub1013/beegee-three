# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Baldur's Gate 3 (BG3) build and playthrough notes repository. All content is pure Markdown — there are no build systems, tests, or scripts.

## Repository Structure

- **Top-level `.md` files** — Standalone character build references (e.g. `shadow-assassin.md`, `hexblade-warlock.md`). These are generic builds not tied to a specific playthrough.
- **`durge/`** — Notes for a Dark Urge playthrough. `durge.md` is the main character; the other files are companions.
- **`doubleteam/`** — Notes for a "Double Team" playthrough. Each file tracks a companion. `gear-chase.md` is a gear-tracking-only document without a full leveling guide.
- **`cartoon/`** — Notes for a playthrough using the cast of the 1983 D&D cartoon. Each file tracks one character. `item-overlap.md` tracks gear conflicts across the party.

## Build Research Process

When creating a new character build, follow these steps in order before writing anything.

### Step 1 — Research the build

Search for current (post-patch 7) guides and tier lists for the class/subclass combination requested. Look for:
- Recommended ability score distributions at character creation
- Multiclass options and the optimal level split
- Feat order and the reasoning behind each choice
- Spell or ability priority by act
- Known synergies and mechanical interactions on Tactician difficulty

Prefer community resources that are explicitly post-patch 7. Note any interactions that may have been patched or changed.

### Step 2 — Research the gear

For each act, search `bg3.wiki` for best-in-slot items for this build. For every item included, verify:
- The exact item name as it appears on the wiki
- The location, including the specific container or NPC it comes from
- The coordinates (`X: ### Y: ###`)
- Whether it is looted, purchased, or found in a chest, and from whom
- Whether the source is unique (one per playthrough) or restockable

Do not include any item that cannot be verified from the wiki. If uncertain about a coordinate or source, say so explicitly in a note rather than guessing.

### Step 3 — Check for conflicts

Before finalising the gear list, cross-reference new items against existing builds in the same playthrough folder. Flag any item that is unique or single-stock and appears in more than one build. Consult `item-overlap.md` in the playthrough folder if one exists.

### Step 4 — Write the build

Follow the document format specified in `FORMAT.md`.

## Document Format

Full format specification is in `FORMAT.md`. Key conventions at a glance:

- **Leveling guide** — one `### Level N` section per level, documenting every choice made at that level
- **Items section** — organised by `## Act 1`, `## Act 2`, `## Act 3`
- **Item status markers** — `[ ]` not yet acquired, `[x]` acquired, `[-]` skipped or not applicable
- **Respec** — restarts the leveling guide from Level 1 under a `### Level N: **RESPEC**` heading, re-documenting all choices from scratch
- **Ability score redistribution** — documented inline under the item that triggers it, as a table

See `FORMAT.md` for the full item entry format, leveling guide structure, and notes conventions.
