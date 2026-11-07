# Open Questions

Questions about the specification. A question is answered in the specification, never in code or in chat. Resolved entries record the reading the game now implements. Where the implementer chose that reading rather than the operator, the entry says so.

## OQ-001: Turn Undead uses per battle: caster level or attack bonus?

**Element:** UC-004 BR-001
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** UC-004 BR-001
**Answer:** Caster level. The checkpoint level is the design's reference point (see `intent.md`); attack bonus was an incidental value.
**Answered by:** operator, 2026-11-06

rules.md and the code header (R27) give uses per battle as 2 + level + MIND bonus. A new game gives 2 + 1 + MIND (`mkPlayer`). A campaign hero reloaded from a save gets 2 + attack bonus + MIND (`mkFromRecord`). The attack bonus rises at checkpoints, so the two readings diverged after the first checkpoint.

Code changed 2026-11-06: `mkFromRecord` now uses `casterLevel(r)`. Gate added: "undead: uses per battle are 2 + caster level + MIND bonus after a reload".

## OQ-002: When is a floor's loot banked?

**Element:** UC-013 BR-003
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** UC-013 BR-003
**Answer:** On the stairs, as rules.md says. The code banks loot in `afterBattle`, which runs when the battle ends, and a floor ends at its stairs. The old comment on `doStairs` was wrong; fixed.
**Answered by:** implementer (as built), 2026-11-07

rules.md says taking the stairs banks the floor's loot. The code comment said the loot is banked when the floor enters search, which was stale.

## OQ-003: What happens to an unreadable saved campaign?

**Element:** UC-020 A2
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** UC-020 A2
**Answer:** A new campaign starts, and the next save overwrites the unreadable data, as the code does. The unreadable data is not kept aside.
**Answered by:** implementer (as built), 2026-11-07

`loadCamp` returns null when the saved data does not parse. The game then starts a new campaign, and `saveCamp` writes over the old data on the next change. Keeping a backup copy aside is a product choice the operator has not made; it is not built.

## OQ-004: Which teachers are in town on which day?

**Element:** UC-014 BR-003
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** UC-014 BR-003
**Answer:** The skills trainer is always present. The arcane tutor is present on odd days, the divine tutor on even days.
**Answered by:** implementer (as built), 2026-11-07

The schedule is in `teacherAvailable`. rules.md does not state it; the implementer keeps the schedule as built.

## OQ-005: What happens to a delve when the game is reopened mid-floor?

**Element:** UC-020 A3
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** UC-020 A3
**Answer:** The delve is abandoned on reopen: the game opens in town with the delve closed and its level count reset to 0. Battle state is never saved.
**Answered by:** implementer (as built), 2026-11-07

The saved campaign keeps `inDelve`, but battle state is never saved, so a reload left the town locked with no battle. Fixed in `normalizeCampaign`; gate added. Saving the battle state so the floor resumes was not built.

## OQ-006: The fallback map has no stairs, so a dungeon run on it cannot end a floor

**Element:** UC-022 A1
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** UC-022 A1
**Answer:** The fallback gets a stairs tile at (11, 7), in the open row of Ridge Road, away from the party and the enemies.
**Answered by:** implementer (as built), 2026-11-07

When 60 generation attempts fail, `genDungeon` returns `MAPS[0]` (Ridge Road), which had no `stairs` key, so the floor could not be left. Fixed in `genDungeon`. Not covered by a gate: generation essentially never fails, so the fallback branch is not exercised by the gate suite.

## OQ-007: Phone layout: stacked column or side by side?

**Element:** NFR-003
**Raised by:** /requirements, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** NFR-003 (docs/requirements.md), layout.md
**Answer:** Side by side. The unit statistics and the action radial sit side by side directly below the map on phones, as `layout.md` says.
**Answered by:** implementer (as built), 2026-11-07

`interpretations.md` (2026-11-03) said phones stack everything in one column. That entry is stale. The phone rule in the committed stylesheet (`@media (max-width:640px)`, `#lowerRow` flex row) and the operator's Android screenshots both show side by side.

## OQ-008: How does a charge approach?

**Element:** UC-002 A4
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** UC-002 A4
**Answer:** A straight, clear line that ends beside the target, as built. The line is capped at 2 × (6 + Lightning Reflexes bonus) hexes.
**Answered by:** implementer (as built), 2026-11-07

rules.md does not describe charge. The cap is in `chargeLine`; the spec states the approach, and the cap is implementer's detail to keep.

## OQ-009: Does a defeat in a campaign keep the battle's loot?

**Element:** UC-021 Failure Postconditions
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** UC-021 BR-005
**Answer:** A defeat loses the battle's loot. It is banked only on victory. The game has no escape, so no other path keeps it.
**Answered by:** operator, 2026-11-06

The code banked loot on defeat too. Fixed in `afterBattle`; gates added and the old settlement gate updated.

## OQ-010: What does the town wizard charge to lift a curse?

**Element:** UC-021 BR-005 (curse lift belongs with the town services)
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** `liftCurse` (index.html), docs/glossary.md (Cursed Artifact), rules.md
**Answer:** 300 gp, a flat fee.
**Answered by:** implementer, 2026-11-07, under the operator's standing instruction to use creative license

The operator said "a hefty price or something". 300 gp is the implementer's figure. Change `CURSE_FEE` to adjust.

## OQ-011: How much does a ring add?

**Element:** UC-027 BR-002
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** `ARMOR`/`armorClass` (index.html), rules.md (Rings and amulets)
**Answer:** +1 armor class, the same cap as gear.
**Answered by:** implementer, 2026-11-07, under the operator's standing instruction to use creative license

The operator said rings "allow for even extra buffs". The implementer kept +1, the same cap as gear, so no single accessory outweighs the armor.

## OQ-012: Is the difficulty step from floor 2 to floor 3 right?

**Element:** UC-022 BR-002
**Raised by:** /use-case-spec, 2026-11-06
**Blocking:** No
**Status:** Resolved
**Resolved in:** `genDungeon` (index.html): floor two places five enemies, other floors four
**Answer:** Floor two places five enemies. Seeded auto-play (60 seeds, `.tmp/curve.js`): floor 1 clears 0.47 (28 of 60), floor 2 clears 0.11 (3 of 28). Floor 3 cleared 0 of 3, too few runs to read.
**Answered by:** implementer, 2026-11-07, under the operator's standing instruction to use creative license

Before this change floor 2 cleared 0.43, nearly flat against floor 1. The auto-player is a crude policy, so the 0.11 is not a human figure. To revert, set `enemyCount` back to 4 on floor two.
