You are helping resolve gear conflicts in a Baldur's Gate 3 playthrough. 
The repository contains build files for each character and an item-overlap.md 
tracking conflicts.

Your task: for each conflicted item, research and propose the best alternative 
for the character who loses the contested item. Follow these steps in order.

## Step 1 — Identify conflicts

Read the item-overlap.md in the playthrough folder. For each conflict, note:
- The item name
- Which characters want it
- Whether the source is unique or single-stock
- The act it becomes available

## Step 2 — Determine who gets the contested item

For each conflict, decide which character benefits most from the item as written. 
Consider: does the item enable a core mechanical loop for one character more than 
the other? Is one character's build more dependent on the specific effect? Document 
your reasoning briefly.

## Step 3 — Research alternatives for the losing character

For each character who does not receive the contested item, search bg3.wiki for 
the best available substitute. The alternative must:
- Fill the same equipment slot
- Be available in the same act or earlier (do not push the character into Act 3 
  for a slot that was covered in Act 1)
- Not conflict with any other character's gear list
- Be verifiable on bg3.wiki with a confirmed source, location, and coordinates

Cross-reference every proposed alternative against all other character build files 
in the playthrough folder before finalising it.

## Step 4 — Output format

For each resolved conflict, output:

**[Item name]**
- Goes to: [Character] — [one sentence reason]
- [Losing character] alternative: [Item name](wiki url)
  - `Location` Source description with **NPC name**. `X: ### Y: ###`
  - Why: [one sentence on why this is the best available substitute]

If no suitable alternative exists within the same act, say so explicitly rather 
than proposing an item from a later act without flagging it.

## Step 5 — Flag unresolved conflicts

If a conflict involves 3+ characters competing for a single item, list all 
alternatives found and note which characters still have no adequate substitute 
after the primary assignment is made. Do not silently leave characters without 
coverage for a slot.

---

Playthrough folder to analyse: [CARTOON]
Characters in party: [LIST]
Focus on: [all conflicts / only Critical conflicts / specific item names]