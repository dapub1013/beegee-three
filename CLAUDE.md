# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Baldur's Gate 3 (BG3) build and playthrough notes repository. All content is pure Markdown — there are no build systems, tests, or scripts.

## Repository Structure

- **Top-level `.md` files** — Standalone character build references (e.g. `shadow-assassin.md`, `hexblade-warlock.md`). These are generic builds not tied to a specific playthrough.
- **`durge/`** — Notes for a Dark Urge playthrough. `durge.md` is the main character; the other files are companions.
- **`doubleteam/`** — Notes for a "Double Team" playthrough. Each file tracks a companion. `gear-chase.md` is a gear-tracking-only document without a full leveling guide.

## Document Format Conventions

Each build document follows this structure:

1. **Header** — `# Character Name or Build Name`
2. **Links bar** — `[Build Reference](url) | [↓ Items](#items) | [↓ Strategy](#combat-strategy)`
3. **Leveling guide** — `### Level N` sections, each containing class choice, subclass, feats, spells/cantrips, and ability scores as a table
4. **Items section** — `# Items`, organized by `## Act 1 / Act 2 / Act 3`
5. **Combat Strategy section** — `# Combat Strategy`, organized by act (where applicable)
6. **Notes section** — Optional synergy item sets and tactical notes

### Item Entry Format

```markdown
[STATUS] Slot: [Item Name](https://bg3.wiki/wiki/Item_Name)
  - `Location Name` Source description with **NPC name** in bold. `X: 000 Y: 000`
```

Item status markers:
- `[x]` — acquired
- `[ ]` — not yet acquired
- `[-]` — skipped or not applicable

### Respec Notes

When a build requires a respec at a certain level, the leveling guide restarts from Level 1 after a `### Level N: **RESPEC**` heading, re-documenting all choices from scratch with the revised decisions.
