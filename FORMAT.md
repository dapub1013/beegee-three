# FORMAT.md

This file defines the document format for all character build files in this repository. Every build file must follow this structure exactly.

---

## File Structure

A build document has five sections in this order:

1. Header
2. Leveling guide
3. Items
4. Elixirs (optional)
5. Notes

---

## 1. Header

```markdown
# [Character Name]'s [Build Name]

[Build Reference](url) | [↓ Items](#items)
```

- The build reference link should point to the primary video or written guide the build is based on.
- Additional links (e.g. early game / late game references, a strategy section) may be added to the links bar separated by ` | `.
- If no external reference exists, omit the link and keep only the anchor links.

---

## 2. Leveling Guide

One `### Level N` section for every level from 1 to 12. Each section documents every choice made at that level. Do not skip levels — if nothing changes at a level, write the class line only.

### Level 1 block (full example)

```markdown
### Level 1

Class: Ranger

Favoured Enemy 1/1: Bounty Hunter

Natural Explorer 1/1: Beast Tamer

Cantrips 3/3:
- Guidance
- Thaumaturgy
- Light

Spells 6/6:
- Magic Missile
- Thunderwave
- Sleep
- Longstrider
- Feather Fall
- Grease

Subclass: Gloom Stalker

Ability Points

| Ability | Score | Modifier |
|---------|-------|----------|
| Strength | 8 | — |
| Dexterity | 17 | +2 |
| Constitution | 14 | — |
| Intelligence | 8 | — |
| Wisdom | 14 | +1 |
| Charisma | 10 | — |
```

### Subsequent level blocks

Include only the lines relevant to that level. Common entries:

```markdown
### Level 4

Class: Ranger

Feat: Sharpshooter

---

### Level 5

Class: Ranger

Spells 1/1: Spike Growth

---

### Level 8

Class: Rogue

Feat: Ability Improvement

| Ability | Score |
|---------|-------|
| Dexterity | 19 |
| Wisdom | 16 |
```

### Spell replacement

When a spell is replaced, show both the removed spell (struck through) and the new spell on the same line:

```markdown
Replace Spell: ~~Hex~~ Elemental Weapon
```

### Subclass

If the subclass is chosen after level 1, document it at the level it is selected:

```markdown
### Level 3

Class: Rogue

Subclass: Thief
```

### Respec

When a build requires a respec, insert a heading at the level the respec occurs and restart the leveling guide from Level 1, re-documenting all choices from scratch with the revised decisions:

```markdown
### Level 9: **RESPEC**

Redistribute as follows. Take levels 1–6 as above, then continue from Level 7.

### Level 1

Class: Monk

Ability Points
...
```

---

## 3. Items

Items are organised under `# Items` and divided into act subsections. Include only acts that have items.

```markdown
# Items

## Act 1

## Act 2

## Act 3
```

### Item entry format

```markdown
[STATUS] Slot: [Item Name](https://bg3.wiki/wiki/Item_Name)
  - `Location Name` Source description with **NPC name** in bold. `X: ### Y: ###`
```

**Status markers:**
- `[ ]` — not yet acquired
- `[x]` — acquired
- `[-]` — skipped or not applicable for this run

**Slot names** (use exactly these, singular, title case):
`Amulet`, `Armour`, `Boots`, `Cloak`, `Dagger`, `Gloves`, `Greatclub`, `Greatsword`, `Hand Crossbow`, `Helmet`, `Longbow`, `Longsword`, `Mace`, `Quarterstave`, `Ring`, `Scimitar`, `Shield`, `Shortbow`, `Shortsword`, `Trident`

**Location name** — in backticks, matches the in-game area name (e.g. `` `Goblin Camp` ``, `` `Last Light Inn` ``, `` `House of Hope` ``).

**NPC names** — in bold (e.g. **Grat the Trader**, **Dammon**, **Quartermaster Talli**).

**Quest names** — in italics (e.g. *Help Omeluum Investigate the Parasite*).

**Coordinates** — in backticks, format `X: ### Y: ###` with a space after each colon.

### Multiple sources for one item

If an item is available from more than one source, list each source on its own indented line:

```markdown
[ ] Ring: [The Whispering Promise](https://bg3.wiki/wiki/The_Whispering_Promise)
  - `Goblin Camp` Sold by **Grat the Trader**. `X: -99 Y: 424`
  - `Sacred Pool` Sold by **Volo**. `X: 260 Y: 510`
  - `Camp` Sold by **Volo**.
```

### Notes on items

Add a note beneath an item entry for anything the player needs to know — priority, conditions, timing, or ability score redistribution triggered by equipping it:

```markdown
[ ] Boots: [Disintegrating Night Walkers](https://bg3.wiki/wiki/Disintegrating_Night_Walkers)
  - `Grymforge` Worn by **Nere**; looted from his corpse. `X: -854 Y: 780`
  - **Note:** Priority acquisition — grants Misty Step and immunity to being enwebbed, entangled, or ensnared.
```

### Ability score redistribution

When equipping an item triggers a recommended ability score redistribution, document it inline beneath the item entry as a full table:

```markdown
[ ] Gloves: [Gloves of Dexterity](https://bg3.wiki/wiki/Gloves_of_dexterity)
  - `Crèche Y'llek` Sold by **A'jak'nir Jeera**. `X: 1380 Y: -798`
  - **Note:** Sets DEX to 18. Once equipped, redistribute ability points:

| Ability | Score | Modifier |
|---------|-------|----------|
| Strength | 17 | +2 |
| Dexterity | 8 | — |
| Constitution | 16 | +1 |
| Intelligence | 8 | — |
| Wisdom | 15 | - |
| Charisma | 8 | — |
```

---

## 4. Elixirs (optional)

Include an `# Elixirs` section when the build depends on consumables for its core mechanical loop (e.g. Elixirs of Hill Giant Strength for a Tavern Brawler monk, Elixirs of Bloodlust for a barbarian).

```markdown
# Elixirs

[Elixirs of Hill Giant Strength](https://bg3.wiki/wiki/Elixir_of_Hill_Giant_Strength)
- Buy from **Auntie Ethel** *before* starting her quest. `Druid's Grove`
- **Note:** Use until the [Club of Hill Giant Strength](https://bg3.wiki/wiki/Club_of_Hill_Giant_Strength) is obtained from the Arcane Tower. Do not go south of the `Blighted Village` until these elixirs are no longer needed.

[Elixirs of Cloud Giant Strength](https://bg3.wiki/wiki/Elixir_of_Cloud_Giant_Strength)
- Use once available in Act 3 alongside Gloves of Soul Catching.
```

Omit this section entirely for builds that do not rely on elixirs.

---

## 5. Notes

The notes section explains the build's mechanical logic — why choices were made, how key features interact, and what the player should prioritise in combat. It is not a summary of what the build does; it is the reasoning behind it.

```markdown
# Notes

**Feature name:** Explanation of why this feature matters, how it interacts with other choices, and how to use it effectively on Tactician. Keep each note to one paragraph. Lead with the most important information.
```

Write one note per meaningful mechanic or item interaction. Do not write notes for self-explanatory choices. Aim for 4–8 notes per build.

---

## Gear-Only Documents

Some documents track gear for a run without a full leveling guide (e.g. `gear-chase.md`). These use the same item entry format but omit the leveling guide and notes sections. Organise items by character rather than by act:

```markdown
# Route

1. `Location` — Action *(Character)*

---

# Character Name

[ ] Slot: [Item Name](url)
  - `Location` Source. `X: ### Y: ###`
```

---

## Item Overlap Documents

Each playthrough folder with multiple characters should have an `item-overlap.md` tracking conflicts on unique or single-stock items. Format:

```markdown
# Item Overlap Report — [Party Name]

## Critical Conflicts (3+ characters, unique or single-stock source)

| Item | Act | Characters | Source |
|------|-----|-----------|--------|

## Moderate Conflicts (2 characters, scarce or unique source)

| Item | Act | Characters | Source Notes |
|------|-----|-----------|-------------|

## Resolutions

**[Item name] → [Character]**
Reasoning.

## Final Assignments Summary

| Item | Goes To |
|------|---------|
```
