# Item Redistribution Reference — Cartoon Party

This file documents every gear conflict resolution for the cartoon playthrough and the
changes required to each character's build file. Work through the files in the order
listed to avoid introducing new conflicts.

---

## How to Use This File

For each conflict block:
1. The **winner** keeps the item as-is in their build file — no change needed.
2. The **loser** section shows exactly what to change: which item to mark `[-]`, what
   alternative to add, and where to add it.
3. **Flags** at the bottom list unresolved gaps that require manual decisions.

Status markers follow the repository convention: `[ ]` not acquired, `[x]` acquired,
`[-]` skipped.

---

## Act 1 Conflicts

---

### Haste Helm
*Single chest — Blighted Village `X: 29 Y: 405`*

**Winner: Hank**
No change to `hank.md`.

---

**Bobby** — `bobby.md`

Mark skipped:
```
[-] Helmet: [Haste Helm](https://bg3.wiki/wiki/Haste_Helm)
  - `Blighted Village` Inside a Moss-Covered Chest near the well. `X: 29 Y: 405`
```

Add to `## Act 1` helmets:
```
[ ] Helmet: [Cap of Wrath](https://bg3.wiki/wiki/Cap_of_Wrath)
  - `Worg Pens` Looted from **Beastmaster Zurk**. `X: -95 Y: 453`
  - **Note:** Does not classify as armour — preserves Unarmoured Defense. Wrath on a
    kill synergises with Berserker's high-damage opening turn.
```

---

**Diana** — `diana.md`

Mark skipped:
```
[-] Helmet: [Haste Helm](https://bg3.wiki/wiki/Haste_Helm)
  - `Blighted Village` Inside a Moss-Covered Chest near the well. `X: 29 Y: 405`
```

Add to `## Act 1` helmets:
```
[ ] Helmet: [Helmet of Uninhibited Kushigo](https://bg3.wiki/wiki/Helmet_of_Uninhibited_Kushigo)
  - `Underdark` On the floor near the northern edge of the Myconid Colony. `X: 85 Y: 6`
  - **Note:** Deals 1d4 bonus damage on unarmed strikes while not wearing armour.
    Directly amplifies the Tavern Brawler unarmed loop. Verify coordinates in-game —
    Underdark item placement can shift across patches.
```

---

**Sheila** — `sheila.md`

Mark skipped:
```
[-] Helmet: [Haste Helm](https://bg3.wiki/wiki/Haste_Helm)
  - `Blighted Village` Inside a Moss-Covered Chest near the well. `X: 29 Y: 405`
```

No alternative needed. Sheila's build already lists [Covert Cowl](https://bg3.wiki/wiki/Covert_Cowl)
as her Act 2 helmet. The Haste Helm was a placeholder — she was never going to hold it
past Act 2 anyway.

---

### Ring of Protection
*One ring from Mol — Tiefling Hideout `X: 84 Y: 73`*

**Winner: Eric**
No change to `eric.md`.

---

**Diana** — `diana.md`

Mark skipped:
```
[-] Ring: [Ring of Protection](https://bg3.wiki/wiki/Ring_of_Protection)
  - `Tiefling Hideout` Rewarded by **Mol** for completing the quest *Steal the Sacred
    Idol* in the Emerald Grove. `X: 84 Y: 73`
```

Diana already lists [Crusher's Ring](https://bg3.wiki/wiki/Crusher%27s_Ring) in
`## Act 1`. No addition needed — Crusher's Ring is her confirmed Act 1 ring.

---

**Presto** — `presto.md`

Mark skipped:
```
[-] Ring: [Ring of Protection](https://bg3.wiki/wiki/Ring_of_Protection)
  - `Tiefling Hideout` Rewarded by **Mol** for completing the quest *Steal the Sacred
    Idol* in the Emerald Grove. `X: 84 Y: 73`
```

Add to `## Act 1` rings:
```
[ ] Ring: [Ring of Mind-Shielding](https://bg3.wiki/wiki/Ring_of_Mind-Shielding)
  - `Underdark - Myconid Colony` Rewarded by **Omeluum** at the end of *Help Omeluum
    Investigate the Parasite*. `X: 112 Y: -88`
  - **Note:** Immunity to being charmed, frightened, or alignment-detected. Critical
    defensive coverage for a backline caster who cannot afford to be turned mid-fight.
    Presto is already at the Myconid Colony for Blurg — collect both on the same visit.
```

---

**Sheila** — `sheila.md`

Mark skipped:
```
[-] Ring: [Ring of Protection](https://bg3.wiki/wiki/Ring_of_Protection)
  - `Tiefling Hideout` Rewarded by **Mol** for completing the quest *Steal the Sacred
    Idol* in the Emerald Grove. `X: 84 Y: 73`
```

Sheila already lists [Strange Conduit Ring](https://bg3.wiki/wiki/Strange_Conduit_Ring)
in `## Act 1`. No addition needed.

---

### Boots of Striding
*Looted from Minthara — Shattered Sanctum `X: 335 Y: 43`*

**Winner: Eric**
No change to `eric.md`.

---

**Bobby** — `bobby.md`

Mark skipped:
```
[-] Boots: [Boots of Striding](https://bg3.wiki/wiki/Boots_of_Striding)
  - `Shattered Sanctum` Worn by **Minthara**. `X: 335 Y: 43`
```

Add to `## Act 1` boots:
```
[ ] Boots: [Linebreaker Boots](https://bg3.wiki/wiki/Linebreaker_Boots)
  - `Worg Pens` Looted from **Beastmaster Zurk**. `X: -95 Y: 453`
  - **Note:** Grants Wrath for 2 turns on Dash — useful for a Berserker who charges
    in to open combat. Same Goblin Camp area as Cap of Wrath; collect both together.
```

---

**Diana** — `diana.md`

Mark skipped:
```
[-] Boots: [Boots of Striding](https://bg3.wiki/wiki/Boots_of_Striding)
  - `Shattered Sanctum` Worn by **Minthara**. `X: 335 Y: 43`
```

Add to `## Act 1` boots:
```
[ ] Boots: [Boots of Genial Striding](https://bg3.wiki/wiki/Boots_of_Genial_Striding)
  - `Ebonlake Grotto` Sold by **Blurg**. `X: 111 Y: -89`
  - **Note:** Difficult terrain immunity keeps Diana in melee range without burning
    movement. Strong value for a monk crossing Grease, Spike Growth, and Web zones.
    No armour proficiency required.
```

---

### Broodmother's Revenge
*Carried by Kagha, Act 1 (Act 3 restock via Koll)*

**Winner: Hank**
No change to `hank.md`.

---

**Bobby** — `bobby.md`

Mark skipped:
```
[-] Amulet: [Broodmother's Revenge](https://bg3.wiki/wiki/Broodmother%27s_Revenge)
  - `Inner Sanctum` Carried by **Kagha** in the Emerald Grove in Act 1. `X: -461 Y: -22`
  - `High Hall` On a table of goods, owned by **Koll** in Act 3. `X: 235 Y: 44`
```

Add to `## Act 1` amulets:
```
[ ] Amulet: [Absolute's Talisman](https://bg3.wiki/wiki/Absolute%27s_Talisman)
  - `Shattered Sanctum` On **Priestess Gut** in her private chambers. `X: 386 Y: 8`
  - **Note:** Casts Healing Word as a bonus action once per Short Rest — free emergency
    sustain that costs no party resources. Best looted by splitting a single character
    off to speak with Gut privately; the other goblin leaders need not be aware.
```

---

### Caustic Band
*Sold by Derryth Bonecloak — Ebonlake Grotto `X: -55 Y: -93`*

**No resolution needed.** Derryth restocks non-unique items on long rest. Bobby and Eric
can each purchase one across separate long rests. Both `bobby.md` and `eric.md` keep
their entries unchanged.

---

### Amulet of Misty Step
*Eric: Defiled Temple `X: 386 Y: 8` / Presto: Omeluum (Myconid Colony)*

**No resolution needed.** Two separate confirmed sources — one per character. No changes
to either build file. Add a note to `presto.md` clarifying his source if not already
present:

```
[ ] Amulet: [Amulet of Misty Step](https://bg3.wiki/wiki/Amulet_of_Misty_Step)
  - `Myconid Colony` Sold by **Omeluum** after completing *Help Omeluum Investigate the
    Parasite*. `X: 112 Y: -88`
  - **Note:** Use Omeluum as Presto's source. Eric takes the Defiled Temple chest
    (`X: 386 Y: 8`). Do not compete for the same copy.
```

---

### Gloves of Dexterity
*Sold by A'jak'nir Jeera — Crèche Y'llek `X: 1380 Y: -798`*

**Winner: Sheila**
No change to `sheila.md`.

---

**Diana** — `diana.md`

Mark skipped:
```
[-] Gloves: [Gloves of Dexterity](https://bg3.wiki/wiki/Gloves_of_dexterity)
  - `Crèche Y'llek` Sold by **A'jak'nir Jeera**. `X: 1380 Y: -798`
```

Also remove or mark inapplicable the ability score redistribution table that follows the
Gloves of Dexterity entry in `diana.md` — it assumes DEX is set to 18, which no longer
applies. Diana holds her base STR 16 → 18 via ASIs and relies on Elixirs of Hill Giant
Strength for the STR boost period rather than re-statting around DEX 18. The respec
ability score tables (if any) that assumed Gloves of Dexterity should be deleted.

---

### Disintegrating Night Walkers
*Looted from Nere — Grymforge `X: -854 Y: 780`*

**Winner: Sheila**
No change to `sheila.md`.

---

**Hank** — `hank.md`

Mark skipped:
```
[-] Boots: [Disintegrating Night Walkers](https://bg3.wiki/wiki/Disintegrating_Night_Walkers)
  - `Grymforge` Worn by **Nere**; looted from his corpse. `X: -854 Y: 780`
```

Add to `## Act 1` boots:
```
[ ] Boots: [Boots of Speed](https://bg3.wiki/wiki/Boots_of_Speed)
  - `Underdark` Given by a rescued Deep Gnome slave near the Myconid Colony entrance
    after healing her (Lesser Restoration) or allowing her to explain her escape.
    `X: 73 Y: -187`
  - **Note:** Swift Strides grants Momentum on Dash (including Cunning Action: Dash).
    Extends Hank's first-turn repositioning and is not contested. Collect during the
    same Underdark visit as Blurg and Omeluum.
```

---

## Act 2 Conflicts

---

### Cloak of Protection
*Sold by Quartermaster Talli — Last Light Inn `X: -31 Y: 130`*

**Winner: Eric**
No change to `eric.md`.

---

**Bobby** — `bobby.md`

Mark skipped:
```
[-] Cloak: [Cloak of Protection](https://bg3.wiki/wiki/Cloak_of_Protection)
  - `Last Light Inn` Sold by **Quartermaster Talli** near the Last Light Inn waypoint.
    `X: -31 Y: 130`
```

Add to `## Act 2` cloaks:
```
[ ] Cloak: [Vivacious Cloak](https://bg3.wiki/wiki/Vivacious_Cloak)
  - `Grand Mausoleum` In a locked Traveller's Chest in the south-east corner.
    `X: -259 Y: -882` (DC 14 Sleight of Hand)
  - **Note:** Grants 8 temporary HP when casting a spell while in melee. Bobby is
    always in melee. No other party member is assigned this item.
```

---

**Diana** — `diana.md`

Mark skipped:
```
[-] Cloak: [Cloak of Protection](https://bg3.wiki/wiki/Cloak_of_Protection)
  - `Last Light Inn` Sold by **Quartermaster Talli** near the Last Light Inn waypoint.
    `X: -31 Y: 130`
```

> ⚠️ **No Act 2 cloak alternative confirmed for Diana.** She carries an empty cloak
> slot through Act 2. Talli relocates to Moonrise Towers before the end of Act 2 and
> may have a second copy of the Cloak of Protection in stock there — purchase it for
> Diana if available. Otherwise Diana's cloak slot remains open until Act 3.

---

### Cloak of Cunning Brume
*Sold by Mattis — Last Light Inn `X: -56 Y: 141`*

**Winner: Sheila**
No change to `sheila.md`.

---

**Hank** — `hank.md`

Mark skipped:
```
[-] Cloak: [Cloak of Cunning Brume](https://bg3.wiki/wiki/Cloak_of_Cunning_Brume)
  - `Last Light Inn` Sold by **Mattis**. `X: -56 Y: 141`
```

> ⚠️ **No Act 2 cloak alternative exists for Hank.** He carries an empty cloak slot
> through Act 2. This is acceptable for a backline archer who avoids melee. His Act 3
> cloak (Cloak of Displacement) arrives immediately on entering Rivington and closes
> the gap.

---

### Eversight Ring
*Single locked chest — House of Healing `X: 9 Y: -981`*

**Winner: Hank**
No change to `hank.md`. The priority note already in Hank's build file stands.

---

**Sheila** — `sheila.md`

Mark skipped:
```
[-] Ring: [Eversight Ring](https://bg3.wiki/wiki/Eversight_Ring)
  - `House of Healing` Found in a locked opulent chest in the corner of the morgue lab
    west of the zombie crypt. `X: 9 Y: -981`
```

Sheila already lists [Shadow-Cloaked Ring](https://bg3.wiki/wiki/Shadow-Cloaked_Ring)
in `## Act 2`. No addition needed — this is her confirmed Act 2 second ring.

---

### Callous Glow Ring
*Single chest near Balthazar — Gauntlet of Shar `X: -821 Y: -752`*

**Winner: Presto**
No change to `presto.md`.

---

**Diana** — `diana.md`

Mark skipped:
```
[-] Ring: [Callous Glow Ring](https://bg3.wiki/wiki/Callous_Glow_Ring)
  - `Gauntlet of Shar` In an opulent chest in the vault room near **Balthazar**.
    `X: -821 Y: -752`
```

Diana carries [Crusher's Ring](https://bg3.wiki/wiki/Crusher%27s_Ring) from Act 1 into
Act 2. No addition needed for her second ring slot at this stage.

---

### Risky Ring
*Sold by Araj Oblodra — Moonrise Towers `X: -128 Y: -193`*

**Winner: Bobby**
No change to `bobby.md`.

---

**Hank** — `hank.md`

Mark skipped:
```
[-] Ring: [Risky Ring](https://bg3.wiki/wiki/Risky_Ring)
  - `Moonrise Towers` Sold by **Araj Oblodra** on the main floor. `X: -128 Y: -193`
```

Add to `## Act 2` rings:
```
[ ] Ring: [The Whispering Promise](https://bg3.wiki/wiki/The_Whispering_Promise)
  - `Goblin Camp` Sold by **Grat the Trader**. `X: -99 Y: 424`
  - `Sacred Pool` Sold by **Volo**. `X: 260 Y: 510`
  - `Camp` Sold by **Volo**.
  - **Note:** Bless targets on Healing Word procs. Minor passive value for a ranged
    character; primarily fills the ring slot until a stronger Act 3 option appears.
    Not contested by any other party member.
```

---

### Yuan-Ti Scale Mail
*Sold by Quartermaster Talli — Last Light Inn `X: -31 Y: 130`*

**Winner: Sheila**
No change to `sheila.md`.

---

**Bobby** — `bobby.md`

Mark skipped:
```
[-] Armour: [Yuan-Ti Scale Mail](https://bg3.wiki/wiki/Yuan-Ti_Scale_Mail)
  - `Last Light Inn` Sold by **Quartermaster Talli** near the Last Light Inn waypoint.
    `X: -31 Y: 130`
```

Bobby already lists [Adamantine Scale Mail](https://bg3.wiki/wiki/Adamantine_Scale_Mail)
from Act 1. He holds it through Act 2 with no gap.

---

## Act 3 Conflicts

---

### Gauntlets of Hill Giant Strength
*Unique pedestal — House of Hope `X: -6549 Y: 2940`*

**Winner: Bobby**
No change to `bobby.md`.

---

**Eric** — `eric.md`

Mark skipped:
```
[-] Gloves: [Gauntlets of Hill Giant Strength](https://bg3.wiki/wiki/Gauntlets_of_Hill_Giant_Strength)
  - `House of Hope` On a pedestal in the Archive. `X: -6549 Y: 2940`
```

**Also delete the ability score redistribution table** that appears beneath the Gauntlets
entry in `eric.md`. That table (which dumps STR to 8) assumed the gauntlets were in
hand — without them, Eric holds STR 18 from his Level 8 ASI through the end of the game.
The final ability score block should read:

| Ability | Score | Modifier |
|---------|-------|----------|
| Strength | 18 | +4 |
| Dexterity | 10 | — |
| Constitution | 14 | — |
| Intelligence | 8 | — |
| Wisdom | 10 | — |
| Charisma | 20 | +5 |

*(Adjust based on Eric's actual respec at level 8 — the point is STR stays at 18, not
dumped to 8.)*

---

### Helldusk Boots
*Single locked chest — Wyrm's Rock Fortress `X: -32 Y: 219`*

**Winner: Sheila**
No change to `sheila.md`.

---

**Bobby** — `bobby.md`

Mark skipped:
```
[-] Boots: [Helldusk Boots](https://bg3.wiki/wiki/Helldusk_Boots)
  - `Wyrm's Rock Fortress` Found in a locked Gilded Chest on the top floor. `X: -32 Y: 219`
```

Add to `## Act 3` boots:
```
[ ] Boots: [Boots of Uninhibited Kushigo](https://bg3.wiki/wiki/Boots_of_Uninhibited_Kushigo)
  - `Astral Plane` Carried by **Prelate Lir'i'c** at the start of Act 3. `X: -163 Y: -1158`
  - **Note:** Bonus action damage on Unarmed Strike after a Dash. Less impactful on
    Bobby than on Diana, but the Dash synergy with Berserker/Thief is real. Not
    contested by any other party member.
```

---

### Armour of Agility
*Sold by Gloomy Fentonson — Stormshore Armoury `X: -41 Y: -71`*

**Winner: Hank**
No change to `hank.md`.

---

**Sheila** — `sheila.md`

Mark skipped:
```
[-] Armour: [Armour of Agility](https://bg3.wiki/wiki/Armour_of_Agility)
  - `Lower City` Sold by **Gloomy Fentonson** at Stormshore Armoury. `X: -41 Y: -71`
```

Sheila holds [Yuan-Ti Scale Mail](https://bg3.wiki/wiki/Yuan-Ti_Scale_Mail) from Act 2
as her Act 3 armour. No addition needed.

---

### Cloak of Displacement
*Sold by Entharl Danthelon — Danthelon's Dancing Axe `X: -10 Y: 143`*

**Winner: Hank**
No change to `hank.md`.

---

**Eric** — `eric.md`

Mark skipped:
```
[-] Cloak: [Cloak of Displacement](https://bg3.wiki/wiki/Cloak_of_Displacement)
  - `Danthelon's Dancing Axe` Sold by **Entharl Danthelon** in Wyrm's Crossing.
    `X: -10 Y: 143`
```

Eric holds [Cloak of Protection](https://bg3.wiki/wiki/Cloak_of_Protection) purchased
from Talli in Act 2. He carries it through Act 3 with no gap.

---

### Horns of the Berserker
*Sold by Entharl Danthelon — Danthelon's Dancing Axe `X: -10 Y: 143`*

**Winner: Diana**
No change to `diana.md`.

---

**Bobby** — `bobby.md`

Mark skipped:
```
[-] Helmet: [Horns of the Berserker](https://bg3.wiki/wiki/Horns_of_the_Berserker)
  - `Danthelon's Dancing Axe` Sold by **Entharl Danthelon**. `X: -10 Y: 143`
```

Bobby uses [Grymskull Helm](https://bg3.wiki/wiki/Grymskull_Helm) as his Act 3 helmet.
If it is not already in his build file, add:
```
[ ] Helmet: [Grymskull Helm](https://bg3.wiki/wiki/Grymskull_Helm)
  - `Adamantine Forge` Carried by **Grym**. `X: -557 Y: 234`
  - **Note:** Prevents critical hits and grants fire resistance. Strong Act 1 pick
    that holds through Act 3. Kill Grym using the forge hammer for the guaranteed drop.
```

---

### Mask of Soul Perception
*Single locked chest — Devil's Fee `X: -33 Y: 20`*

**Winner: Hank**
No change to `hank.md`.

---

**Sheila** — `sheila.md`

Mark skipped:
```
[-] Helmet: [Mask of Soul Perception](https://bg3.wiki/wiki/Mask_of_Soul_Perception)
  - `Devil's Fee` In a locked Gilded Chest (DC 20 Sleight of Hand) in **Helsik's**
    room upstairs. `X: -33 Y: 20`
```

Sheila already lists [Covert Cowl](https://bg3.wiki/wiki/Covert_Cowl) from Act 2 as
her helmet. No addition needed.

---

## Unresolved Gaps

These three issues have no clean item-based fix and require a manual decision before
finalising the build files.

---

### ⚠️ Diana — No Act 2 Cloak

**Problem:** Every Act 2 cloak is contested or assigned to another character. Diana
carries an empty cloak slot from Last Light Inn through the end of Act 2.

**Options:**
1. Accept the gap. Diana's AC and saves are covered by other items and her movement kit.
   She picks up a cloak in Act 3 if one becomes available.
2. Check whether Talli carries a second Cloak of Protection when she relocates to
   Moonrise Towers after the Isobel fight. If so, purchase it for Diana immediately.
3. Use [Cloak of Cunning Brume](https://bg3.wiki/wiki/Cloak_of_Cunning_Brume) from
   Mattis if Sheila's priorities change — but this requires reopening Sheila's gear.

---

### ⚠️ Hank — No Act 2 Cloak

**Problem:** Cloak of Cunning Brume goes to Sheila. No other Act 2 cloak is uncontested
for Hank.

**Decision:** Accept the empty slot. Hank is a backline archer who avoids melee; the
cloak slot matters less for him than for front-liners. Cloak of Displacement arrives
immediately on entering Rivington at the start of Act 3 and closes the gap.

*No change needed to `hank.md` beyond marking Cloak of Cunning Brume as `[-]`.*

---

### ⚠️ Eric — STR Reduced Without Gauntlets of Hill Giant Strength

**Problem:** The ability score redistribution table in `eric.md` assumes STR is dumped
to 8 after equipping the Gauntlets. Without them, this respec never happens. Eric's
melee damage is reduced by approximately 4 per hit compared to the original plan, but
the build remains fully functional.

**Decision:** Delete the post-Gauntlets redistribution table from `eric.md`. Eric ends
the game with STR 18, CHA 20, and CON 14 (or adjusted per actual respec). Sacred Weapon
covers the to-hit gap; Lay on Hands and Aura of Protection are unaffected.

*See the Eric block in Act 3 Conflicts above for the corrected final ability score table.*

---

## Vendor Timing Notes

These items are sold by the same vendor and should be purchased in the same visit to
avoid missing the window:

**Entharl Danthelon — Danthelon's Dancing Axe, Wyrm's Crossing (Act 3):**
- Horns of the Berserker → Diana
- Cloak of Displacement → Hank
- *(Bobby's Boots of Uninhibited Kushigo is looted, not purchased here)*

**Quartermaster Talli — Last Light Inn (Act 2):**
- Cloak of Protection → Eric
- Yuan-Ti Scale Mail → Sheila
- *(Bobby and Diana are not buying from Talli — no queue conflict)*

**Talli at Moonrise Towers (end of Act 2):**
- Check stock for a second Cloak of Protection → Diana (see Diana gap above)

**Gloomy Fentonson — Stormshore Armoury (Act 3):**
- Armour of Agility → Hank
- *(Sheila holds Yuan-Ti Scale Mail — no competing purchase here)*
