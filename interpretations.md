# CURRENT — Campaign redesign interpretations

## Current stairs, search and wanderer decision (2026-11-02)

- **Floor ends only at the stairs.** Operator, 2026-11-02: "Stairs only." A cleared dungeon floor stays open for searching, and only taking the floor's stairs ends it. Opening the last chest no longer ends the floor. Basis: the operator's own words ("all treasure has been cleared or I decide to go to next level by going to stairs").
- **Wandering check cadence.** After every second search round, roll 1d6; a 1 brings 1d3 wanderers. Basis: Moldvay's check is every 2 turns (`DnD_Basic_Rules_Moldvay.md` near line 4921). Alternative kept open: a 1-in-6 check every round, a one-constant change, which Moldvay also allows in dangerous areas. Odds: about 31-42% for a 4-6 round sweep, 84% by round 20.
- **Chest scaling.** Floor N chests hold N gold rolls of 2d6 x 5 and N items. Basis: Moldvay's unguarded treasure scales by level, but a straight 10x would give floor-two chests about 350 gp, so this uses the ×N scale instead. House rule; no balance run.
- **Overlays.** 2026-11-03 operator decision: the translucent overlays were rejected (superseded). The current layout is a split row below the map: turn status (round, phase, objective, guidance) sits below the map, unit statistics are on the left of the split row and the action radial on the right. The game log is a column to the right of the whole map and action area. Extra actions (Move, Stop moving, Loot, Use item and the like) sit beside the radial, to its right, never below it. All panels have fixed heights, and the whole screen fits an 800px-tall window. Phones (640px or less) stack everything in one column at full width, with the radial at 60%. The screen arrangement is now governed by `layout.md` (requirement type: layout). Basis: operator messages 2026-11-03.
- **Stairs visibility.** On a random floor the stairs were off-screen (measured: the stairs tile at y about 370 of a 496px map in a 384px view). The map is now scaled to fit the window, so the stairs are always on screen, and the stairs tile is outlined. The earlier once-per-floor scroll was removed. Basis: operator report 2026-11-03 ("never found the stairs at the end of the match for the 1st dungeon") and the operator instruction that the game should always fit with no scrollbars.
- **Floor words.** Campaign uses "level N of 3"; standalone uses "floor N of 3" (DEC-02 default, operator to confirm).
- **Layout requirement type.** Screen arrangement, fixed heights and the no-scroll rule now live in layout.md, a separate requirement file, not in the header contract. Basis: operator message 2026-11-03.

## Current movement-reaction decision (2026-11-01)

- **“entering covered enemy areas (i.e. attacks of opportunity)”** means crossing into an awake, non-fleeing opposing unit's legal melee reach during a committed movement.
- Each opposing unit gets at most one reaction per movement, shared by entry and exit. Entry uses one normal melee strike with no extra +2; existing rear, weapon and elevation modifiers still apply. Leaving legal melee reach retains the existing +2 parting attack.
- A mover downed by an entry reaction remains on the entered hex and cannot continue the route. Movement previews list visible entry/exit reactions without changing state or RNG.
- Basis: the user's stated preference to make entering covered areas provoke attacks, combined with the existing +2 reaction when leaving adjacency. The once-per-movement cap and no extra entry bonus are defaults that limit duplicate retaliation while preserving the existing exit rule.

## Current adjacent-casting decision (2026-11-01)

- Casting while adjacent to a living enemy requires d20 + caster level + MIND modifier + steady-ground bonus against DC 15 + spell level; Combat Casting adds +4.
- A failed check spends the spell HP cost and action but produces no spell effect. Without an adjacent living enemy, no check is made.
- Moving away uses the existing movement rule and can provoke its +2 parting attack when the adjacent enemy has line of sight.
- Basis: the user's requirement that casters can move, but adjacency at minimum imposes a penalty, and the user's preference that withdrawing can invite a parting attack; the feat allows specialization in casting under pressure.

## Current elevation forms and table break rule (2026-11-01)

- Z -1 is a pit or connected channel; when a pit trap springs, its tile becomes the same open depression while the sprung trap remains separately recorded. +1 uses traversable table or barrel platforms; +2 uses a traversable raised ledge and retains the Physical + STR DC 20 Climb requirement. Bookshelves remain furniture, not standable elevation.
- An adjacent hero can spend an action to break a table platform with d20 + Physical rank + STR modifier + steady-ground bonus vs DC 12. Success lowers the tile to ground; a unit on the platform takes 1 HP falling damage. Failure leaves the table intact.
- Barrels are not breakable under the table-only action; connected -1 cells are visually drawn as one channel and retain the existing movement rules. A spear's ability to reach a bookshelf as an object does not establish that a hero can stand on it or change the polearm's two-level reach limit.
- The previous 3px line-marker decision is superseded by the user's latest preference for recognizable terrain forms; its details are retained in `.tmp/interpretations-history-2026-10-31.md`.
- Basis: the user's latest terrain-form proposal. DC 12 and one-point fall damage are selected defaults because the user did not specify table durability or the fall consequence; table-only breakability preserves the explicit table rule without extending it to barrels.

## Current z-level decision — 2026-10-31

- Local elevation is separate from dungeon-floor progression and traps; +1 is traversable, while +2 boundary bands require Physical skill and a Physical + STR DC 20 Climb check; no skill or a failed check causes 2 HP fall damage.
- Vertical weapon rules follow the user's specific ruling: ordinary melee equal-z only; polearms reach one level and gain +1 downward; crossbows reach two levels with +/-1 per level; short bows reach one level without modifier; longbows reach two, cap downward bonus at +1, and take -1 per level upward.
- Superseded visual decision: line markers were replaced on 2026-11-01 by the recognizable terrain forms above; details are retained in `.tmp/interpretations-history-2026-10-31.md`.
- Basis: user's latest explicit mechanical and visual decisions; Pathfinder-LITE supplies the Climb check, while weapon modifiers remain game-specific rules.

Older provisional z-level summaries are superseded and preserved in `.tmp/interpretations-history-2026-10-31.md`.

- 2026-10-31: Use four active and four reserve pre-generated heroes; basis: the user's Jagged Alliance roster example and current four-person battle capacity.
- 2026-10-31: Run three consecutive dungeon victories before town services; defeat returns to town; basis: the user's three-level option and dungeon/town division.
- 2026-10-31: Carry HP and spell HP debt between levels; town rest clears them; basis: spell casting already spends HP and the existing town rest already restores debt.
- 2026-10-31: Keep ordinary equipment and arrows in town; make consumables and spell scrolls dungeon finds; basis: the requested split between basic resupply and magical treasure.
- 2026-10-31: Keep checkpoint advancement as the gate for spell picks; a class teacher must be present, while a found scroll bypasses XP but not class, caster-cap, or teacher checks; basis: preserve existing progression and add the user's teacher availability condition.
- 2026-10-31: Reconcile the restored UX review using only relevant laws and the observation/law/hypothesis/change/validation format; basis: ux-law/SKILL.md.
- Earlier tactical and repair interpretations are preserved in `.tmp/interpretations-tactics-2026-10-31.md`; this file now tracks campaign decisions.
