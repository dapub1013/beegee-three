---
name: bg3-build
description: "Use this skill when creating or updating a Baldur's Gate 3 character build file in a playthrough repository. Covers the full research pipeline: finding post-patch-7 build guides, verifying every item against bg3.wiki, checking gear conflicts against other characters in the same playthrough folder, and writing the output file. Triggers: any request to create, research, or update a BG3 build file, or to find gear for a BG3 character."
compatibility: "Claude Code with access to a BG3 build repository"
---

# BG3 Build Research

## Why this skill exists

BG3 build files have a hard correctness requirement: every item entry must reflect the actual game — exact name, exact location, exact NPC, exact coordinates, and whether the source is unique or restockable. Training knowledge is not sufficient for this. Item coordinates, container names, and NPC names are exactly the kind of detail that gets silently corrupted without wiki verification.

This skill encodes the research process that produces correct build files. FORMAT.md in the repository defines what the output looks like. This skill defines how to get there.

---

## Step 0 — Establish character creation constraints

Before researching any guides, resolve the four decisions that lock in at character creation and cannot be undone by Withers. Getting these wrong invalidates downstream ability score and proficiency planning.

### Starting class

The class taken at level 1 — not the class with the most levels — determines two things that are fixed for the life of the build:

**Saving throw proficiencies.** Only the first class taken grants its saving throw proficiencies. Multiclassing into a second class does not add that class's saves. Document which two saves the build has proficiency in, and confirm they come from the level 1 class.

Saving throw proficiencies by first class:

| Class | Save proficiencies |
|-------|--------------------|
| Barbarian | Strength, Constitution |
| Bard | Dexterity, Charisma |
| Cleric | Wisdom, Charisma |
| Druid | Intelligence, Wisdom |
| Fighter | Strength, Constitution |
| Monk | Strength, Dexterity |
| Paladin | Wisdom, Charisma |
| Ranger | Strength, Dexterity |
| Rogue | Dexterity, Intelligence |
| Sorcerer | Constitution, Charisma |
| Warlock | Wisdom, Charisma |
| Wizard | Intelligence, Wisdom |

**Default spellcasting ability.** For non-class features (item spells, scrolls, illithid powers), BG3 uses the spellcasting ability of the class most recently taken to level 1. On a pure build this is always the starting class. On a multiclass build, it is whichever class was taken to level 1 most recently — which may not be the class with the most levels. Confirm this matches the ability score the build is investing in.

Exception: Arcane Trickster and Eldritch Knight both properly define Intelligence as their spellcasting ability and behave predictably on multiclassed characters even when other classes are taken afterward.

### Background

Backgrounds grant exactly two skill proficiencies and cannot be changed after character creation — Withers cannot respec a background. The choice is permanent.

**Check for skill overlap before committing.** If a background grants proficiency in a skill the character's class also offers, that background slot is wasted. Cross-reference the class's skill list against the background's two skills before finalising.

Complete background reference:

| Background | Skills granted |
|------------|----------------|
| Acolyte | Insight, Religion |
| Charlatan | Deception, Sleight of Hand |
| Criminal | Deception, Stealth |
| Entertainer | Acrobatics, Performance |
| Folk Hero | Animal Handling, Survival |
| Guild Artisan | Insight, Persuasion |
| Haunted One | Medicine, Intimidation |
| Noble | History, Persuasion |
| Outlander | Athletics, Survival |
| Sage | Arcana, History |
| Soldier | Athletics, Intimidation |
| Urchin | Sleight of Hand, Stealth |

Note that Haunted One is exclusive to the Dark Urge origin and is unavailable to custom characters.

### Point buy constraints

Ability scores are allocated via point buy at character creation. The floor is 8 and the ceiling is 15, before any bonuses are applied. Racial bonuses (for races that still grant them) and feat bonuses from the Ability Improvement feat are applied on top of this base.

Ability score modifier chart for reference:

| Score | Modifier | Score | Modifier |
|-------|----------|-------|----------|
| 8–9 | −1 | 16–17 | +3 |
| 10–11 | +0 | 18–19 | +4 |
| 12–13 | +1 | 20–21 | +5 |
| 14–15 | +2 | 22+ | +6 and up |

Key interactions to document in the build:

- **Constitution and HP.** The Constitution modifier applies to HP gained at every level, and this is applied retroactively. A build that starts with Constitution 14 (+2) and raises it to 16 (+3) via Ability Improvement at level 4 gains the extra +1 HP per level retroactively across all prior levels. This makes early Constitution investment less punishing than it may appear.
- **Ability score bonus priority.** Bonuses apply in a fixed order: Ability Improvement feats first (capped at 20), then uncapped bonuses (items like Auntie Ethel's Hair), then capped bonuses (most equipment). If a build plans to use an item that sets or raises an ability score, confirm that the bonus priority does not cause an unexpected interaction. The Ability Improvement feat cannot be taken if all scores it would raise are already at or above 20.
- **Spell save DC formula.** For caster builds: Spell Save DC = 8 + proficiency bonus + spellcasting ability modifier. Document the target DC at key levels (e.g. level 5 and level 12) to confirm the ability score allocation achieves meaningful DCs on Tactician.

### Skill proficiency budget

Before finalising the level 1 block, tally the full skill proficiency budget:

- Background: 2 skills (fixed, as above)
- Class: 2 skills from the class list (Bards and Rangers choose 3; Rogues choose 4)
- Race: some races grant additional skill proficiencies

Proficiency does not stack — if the same skill is granted by two sources, the duplicate is wasted. Rogues gain Expertise (double proficiency bonus) in two skills at level 1 and again at level 6; this is separate from proficiency and should be planned for when choosing starting skills.

---

## Step 1 — Read the repository conventions

Before doing anything else, read these two files from the repository root:

- `CLAUDE.md` — overview, folder structure, and the four-step build process
- `FORMAT.md` — full document format specification

If either file is missing, ask the user before proceeding. Do not guess at format conventions.

---

## Step 2 — Research the build

Search for current guides for the requested class/subclass combination. Every search query must include patch context.

**Query templates:**

```
[class] [subclass] build tactician patch 7 baldur's gate 3
bg3 [class] [subclass] best build patch 8
bg3 [class] multiclass [subclass] guide
```

**What to extract from guides:**
- Ability score distribution at character creation
- Multiclass split and the level at which each class is taken
- Feat order and the reasoning (not just the feat name — why at that level)
- Spell or ability priority by act
- Key mechanical interactions and synergies
- Any interactions flagged as patch-sensitive

**Source reliability — written guides:**

- **r/BG3Builds** (reddit.com/r/BG3Builds) — best source for niche multiclass interactions and community-tested theory. The subreddit wiki and pinned "Completed Builds" post are high-value starting points. Individual contributors worth searching directly: c4b-BG3 (Sorcadin/Lockadin theory), Bravest_Coward (Bladesinger), Cephalopocalypse (level-by-level progressions). Prefer posts with detailed mechanical explanations over pure gear lists.
- **Deltia's Gaming** (deltiasgaming.com) — actively maintained through Patch 8, covers Tactician difficulty explicitly, includes act-by-act gear recommendations and ability score setups. Good for confirming feat order reasoning.
- **Alcast HQ** (alcasthq.com) — methodical level-by-level format with gear sets separated by act. Updated through 2026. Strong coverage of all classes and subclasses including Patch 8 additions.
- **Gamestegy** (gamestegy.com) — builds tested at Honour Mode difficulty, which makes them conservative and reliable at Tactician. Tier list includes mechanical reasoning rather than just community popularity.
- **PC Gamer multiclass guide** (pcgamer.com/baldurs-gate-3-multiclass-builds) — useful for understanding *why* specific multiclass splits work, written by a player with Honour Mode clears. Updated through Patch 8. Best for synthesis, not copying verbatim.
- **bg3.wiki build pages** — reliable for mechanics and ability interactions, less reliable for opinionated gear lists. Use as a cross-check, not a primary build source.
- **Fextralife** — treat as a starting point only. Cross-check everything, especially item locations and coordinates.

**Source reliability — YouTube:**

- **Cephalopocalypse** — best for structured build guides that walk through real level-by-level progressions. Praised specifically by the community for not skipping early-game and for honest Tactician-tested assessments.
- **Proxy Gate Tactician** — better for tips, tricks, and exploit discovery than for structured build guides. Useful for understanding edge-case mechanics.
- **Mortismal Gaming** — strong mechanics explainers and class overviews. Good for understanding a class before diving into build specifics.

**Patch currency warning:** Patch 8 shipped in early 2025 and added 12 new subclasses (including Hexblade Warlock, Bladesinger Wizard, and others). Any guide dated before early 2025 should be treated as potentially stale on subclass options and feat interactions, even if the core multiclass logic holds. Deltia's and Alcast are both explicitly updated for Patch 8. When in doubt, check the guide's date before trusting subclass-specific advice.

**Flag anything that looks patch-sensitive.** Certain interactions change between patches — multiclass feat timing, specific item interactions, some spell behaviours. If a guide is ambiguous about patch version, note it explicitly in the build file rather than presenting it as settled fact.

---

## Step 3 — Research and verify every item

This step is non-negotiable. Do not include any item that has not been verified against bg3.wiki.

### Wiki URL pattern

```
https://bg3.wiki/wiki/Item_Name_With_Underscores
```

Spaces in item names become underscores. Apostrophes and special characters are URL-encoded. When in doubt, search bg3.wiki directly rather than constructing the URL.

**Example:**
- `Cloak of Displacement` → `https://bg3.wiki/wiki/Cloak_of_Displacement`
- `Hellrider's Pride` → `https://bg3.wiki/wiki/Hellrider%27s_Pride`

### Per-item verification checklist

Run this checklist for every single item before including it:

- [ ] **Name** — exact item name as it appears on the wiki page
- [ ] **Act** — which act is this item available in
- [ ] **Location** — exact in-game area name (e.g. `Last Light Inn`, not `Act 2 camp`)
- [ ] **Container or source** — chest name, NPC name, or loot source
- [ ] **NPC name** — exact name in bold if sold or carried by an NPC
- [ ] **Coordinates** — `X: ### Y: ###` format, verified from the wiki
- [ ] **Unique or restockable** — one per playthrough, or does the vendor restock

### What "cannot be verified" means

If a coordinate is absent from the wiki, or the source description is ambiguous, or the item's availability depends on a quest state that is unclear:

- Include the item with a `**Note:**` flagging what could not be confirmed
- Do not guess at coordinates — an absent coordinate is better than a wrong one
- Do not omit the item silently — the user needs to know it exists even if verification is incomplete

### Searching for best-in-slot gear by act

Use these query patterns to find items you may not have thought of:

```
bg3 best [slot] [class] act [1/2/3]
bg3 [class] best in slot gear
bg3 wiki [class] recommended equipment
```

Then verify each candidate on bg3.wiki before including it.

---

## Step 4 — Check for gear conflicts

Before finalising the gear list, cross-reference every unique or single-stock item against all other build files in the same playthrough folder.

### How to do this

1. List all `.md` files in the current playthrough folder (e.g. `cartoon/`)
2. Read each file and extract its item list
3. For every item in the new build that is unique or single-stock, check whether it appears in any other file
4. If `item-overlap.md` exists in the folder, read it — it already tracks known conflicts
5. Add any new conflicts discovered to `item-overlap.md` (or create it if it doesn't exist)

### Conflict severity

**Critical conflict:** 3+ characters want the same unique item. Flag prominently. The build file should note the conflict and leave resolution to the user.

**Moderate conflict:** 2 characters want the same unique or single-stock item. Flag it. If one character's core mechanical loop depends on the item more than the other's, note which character has the stronger claim.

**Non-conflict:** Vendor-restocked items (many vendors restock on long rest or level-up), or items with multiple sources in different acts. Verify restock behaviour on bg3.wiki before assuming a conflict is real.

### Conflict entry format in build files

When a conflict exists and is unresolved, document it inline:

```markdown
[ ] Gloves: [Gauntlets of Hill Giant Strength](https://bg3.wiki/wiki/Gauntlets_of_Hill_Giant_Strength)
  - `House of Hope` On a pedestal in the Archive. `X: -6549 Y: 2940`
  - **Note:** ⚠️ Conflict with [other character] — unique item, one per playthrough. Resolve before Act 3.
```

---

## Step 5 — Write the build file

Follow FORMAT.md exactly. Key points:

- One `### Level N` section per level, 1 through 12 — do not skip levels
- Items organised under `## Act 1`, `## Act 2`, `## Act 3`
- Every item entry uses the verified name, location, NPC, and coordinates from Step 3
- Respec documented by restarting the leveling guide from Level 1 under a `### Level N: **RESPEC**` heading
- Ability score redistribution documented inline under the item that triggers it, as a full table
- Notes section explains mechanical reasoning — not what the build does, but why choices were made

### Common format errors to avoid

- Do not skip a level entry even if nothing changes at that level — write the class line only
- Do not use coordinates you haven't verified from bg3.wiki
- Do not mark an item `[x]` (acquired) unless the user has confirmed it — use `[ ]` by default
- Do not list items under the wrong act — verify act availability on bg3.wiki, not from memory

---

## Failure modes to watch for

**Hallucinated coordinates.** This is the most common error. A coordinate that looks plausible but is wrong sends the player to the wrong place. If you are not certain of a coordinate, omit it and add a note rather than guessing.

**Wrong NPC name.** NPC names in BG3 are specific and sometimes counterintuitive (e.g. "Quartermaster Talli", not "Talli"). Always take the name from the wiki page, not from memory.

**Stale patch information.** Some build advice that was correct pre-patch 7 is no longer accurate. If a guide is undated or pre-patch 7, flag it. When in doubt, prefer wiki mechanics pages over guide recommendations.

**False conflicts.** Some items appear to conflict but don't — Derryth Bonecloak restocks the Caustic Band, Volo restocks the Whispering Promise, and some items have multiple sources across acts. Verify restock behaviour before flagging a conflict.

**Missing act assignment.** Items that are technically obtainable in Act 1 but require going somewhere dangerous, or items that become available in Act 2 but were placed in the world in Act 1, can be ambiguous. Use bg3.wiki's "Where to find" section as the authority.

**Multiclass save proficiency assumption.** Only the first class taken at character creation grants saving throw proficiencies. A build that starts as Rogue and multiclasses into Paladin does not gain Wisdom and Charisma saves — it keeps Dexterity and Intelligence. Guides occasionally get this wrong or assume a specific starting class without stating it. Verify the level 1 class against the save proficiencies the build claims to have.

**Background skill overlap.** Background proficiencies cannot be changed and do not stack with class proficiencies. A Criminal background on a Rogue wastes Stealth (already a Rogue class skill option). Check for overlap before finalising the level 1 block and flag it if a guide's suggested background produces redundant proficiencies for the class.

**Spellcasting ability mismatch on multiclass builds.** Non-class spellcasting (scrolls, item spells, illithid powers) uses the spellcasting ability of the most recently taken first level, not the primary class. A build that takes Fighter at level 7 will use Intelligence for those features going forward, even if the build is primarily a Cleric. Confirm which class was taken to level 1 most recently and that it matches the ability score being invested in.
