# Hank Build Audit — Gloom Stalker 7 / Thief 5

Audited against BG3 mechanics (knowledge cutoff August 2025, covers Patch 7 thoroughly and early Patch 8 discussion). Web search was unavailable for external guide verification.

---

## Critical Issue

**Lightning Arrow at Level 11 (post-respec Ranger 7) is mechanically impossible.**

Rangers are half-casters. Spell level access by individual class level:
- Ranger 5–8: Up to 2nd-level spells
- Ranger 9–12: Up to 3rd-level spells

Lightning Arrow is a 3rd-level spell. At 7 Ranger levels, Hank cannot learn or cast it. The post-respec Level 11 entry is wrong.

What Hank *actually* gains at Ranger 7 is **Stalker's Flurry** — the Gloom Stalker Level 7 subclass feature. When you miss an attack this turn, you can immediately make another attack as a free bonus. For a build that fires multiple arrows per round (Dread Ambusher + Extra Attack + Thief bonus action), this is a significant DPR pickup. It's likely the real reason the build goes to Ranger 7.

**Action required:** Replace `Spells 1/1: Lightning Arrow` at post-respec Level 11 with the Stalker's Flurry feature note. Consider whether to add a different 2nd-level Ranger spell at that slot — Pass Without Trace is the community consensus best-in-slot for a stealth archer party (+10 to stealth for the whole party, concentration-free).

---

## Mechanical Issues

### DEX 17 at creation wastes one ability point

DEX 16 and DEX 17 both give +3 modifier. With two +2 ASIs:
- DEX 16 → 18 → 20 (hits cap cleanly)
- DEX 17 → 19 → 21, capped to 20 (same endpoint, one creation point wasted)

The extra point from dropping to DEX 16 could go into CON (14 → 15) or WIS (14 → 15, better spell DC at low levels). Minor — the modifier difference is zero — but it is a creation inefficiency.

### Stalker's Flurry not mentioned in Notes

The Notes explain Sharpshooter math, first-turn burst, Titanstring, Eversight, and Risky Ring. But the reason the build takes 7 Ranger levels (rather than stopping at 5 or 6) is never stated. Without documentation, the return to Ranger at Level 10–11 reads like it's purely for Favoured Enemy/Natural Explorer picks, which is a weak justification.

**Action required:** Add a note explaining that Stalker's Flurry is what justifies the 7th Ranger level.

### Spell save DC is low throughout

WIS 14 gives +2, so Spell Save DC = 8 + prof + 2. This is DC 10 at Level 3 and only reaches DC 15 at Level 12. Ensnaring Strike (STR save) will miss often against strong enemies in Act 2–3. This is not a build flaw — the spells are used for area denial more than reliable CC — but it should be noted explicitly. Spike Growth in particular doesn't require a save to deal damage, so it is unaffected.

---

## Gear Issues

### Strange Conduit Ring / Helmet of Arcane Acuity interaction is unverified

The community interaction: Strange Conduit Ring procs +1d4 psychic damage on weapon attacks while concentrating on a spell. If that psychic damage counts as "spell damage" for the Helmet of Arcane Acuity's Arcane Acuity stack trigger, then every arrow Hank fires while Hunter's Mark is up builds stacks — boosting his spell save DC for Spike Growth and Ensnaring Strike.

If the psychic damage is classified as weapon damage (which it may be, since it procs from a weapon attack), the helmet never stacks and is essentially worthless on Hank. Neither item's entry cross-references the other, and there is no note explaining why an archer needs a caster helmet.

This interaction is exactly the kind of thing that gets patched without announcement.

**Action required:** Verify on bg3.wiki whether Strange Conduit Ring's damage is classified as spell or weapon damage. If the interaction works, add cross-reference notes to both items. If it doesn't work, replace the Helmet of Arcane Acuity with an Act 2 alternative (e.g. Covert Cowl from the Last Light Inn cellar — verify it is not exclusively Sheila's source).

### Boots of Stormy Clamour conflict with Bobby's open gap

`cartoon/item-overlap.md` notes Bobby's Act 3 boots slot is unresolved and lists Boots of Stormy Clamour as a candidate. Hank's file claims them. These are sold by Omeluum in Act 3 — likely single-stock. If Hank takes them, Bobby's candidate is eliminated.

**Action required:** Decide the Boots of Stormy Clamour assignment and update `item-overlap.md`. If Hank keeps them, find a Bobby alternative (Bonespike Boots, Boots of Psionic Movement, or similar). If Bobby gets them, find Hank an Act 3 boots replacement.

---

## Already Correct

- Sharpshooter at Level 4: Correct and still community consensus
- 7 Ranger / 5 Rogue split is mechanically sound once Stalker's Flurry is acknowledged
- Titanstring + Hill Giant Strength elixirs: Sound strategy, well documented
- Haste Helm → Hank: Consistent with `item-overlap.md`
- Eversight Ring → Hank: Consistent with `item-overlap.md`
- Risky Ring `[-]`: Correctly skipped; Bobby takes it per `item-overlap.md`
- Disintegrating Night Walkers `[-]`: Correctly skipped; Sheila takes them
- The Whispering Promise: Not a conflict — multiple restockable vendors (Grat, Volo)
- Act 2 empty cloak: Acknowledged and explained in file
- Cloak of Displacement, Armour of Agility, Mask of Soul Perception: All consistent with `item-overlap.md`

---

## Patch 8 Note

Patch 8 (early 2025) added new subclasses but did not change Gloom Stalker, Thief Rogue, Sharpshooter, or the Archery fighting style. No patch-sensitive regressions in the core build design. Titanstring Bow scaling with STR (not DEX) is unchanged.

---

## Priority Order for Fixes

1. **Level 11 entry** — replace Lightning Arrow with Stalker's Flurry documentation
2. **Helmet of Arcane Acuity** — verify the Strange Conduit interaction on bg3.wiki before assuming it works
3. **Boots of Stormy Clamour** — resolve the Bobby conflict in `item-overlap.md`
4. **Notes section** — add Stalker's Flurry as the stated reason for the 7th Ranger level
5. **DEX 17** — consider correcting to 16; no in-game impact until respec
