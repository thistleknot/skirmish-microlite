# Microlite Tactics: Player Rules

This is the player-facing reference for the rules the game currently enforces. It follows the game contract in `microlite-tactics-skirmish.html`. A rule marked **House rule** is specific to this game. A note under **Not implemented** describes a proposal or source rule that the game does not currently use. See [Inspirations](./inspirations.md) for what the game borrowed or adapted from other systems and which sources informed design without supplying a current rule.

## Objective and turns

- Win a standalone skirmish by defeating the enemy or completing the map objective. In a random dungeon, clear three floors by taking each floor's stairs; clearing a floor's enemies is not enough, and leaving the third floor by its way out is the final victory.
- On your turn, activate ready heroes in any order. Each hero gets one move and one action. You can switch to another ready hero at any time.
- A committed weapon attack uses the hero's whole activation, so that hero cannot move afterward. Spells, items, searches and other skills use the action and leave unused movement available.
- End a hero's activation when you are done. When the party has no remaining actions, enemies move and attack.

## Movement and facing

- Heroes have 6 movement points, plus any feat bonus. Plain ground costs 1; rubble costs 2; brush costs 2, or 1 for a ranger.
- Movement is previewed before it is committed. A preview shows the route, cost, remaining movement and visible parting/entry reaction threats.
- A hero may spend movement in steps, then act or continue moving with the remaining points. Stop moving to give up the remainder.
- Movement sets facing toward the side the hero entered from.
- **House rule:** Entering a hex within an awake enemy's legal melee reach provokes one free normal melee attack from that enemy during the committed movement. Fleeing or turned enemies do not react. Each enemy can react once per movement; the entry attack gets no extra parting bonus. Existing rear, weapon and elevation modifiers still apply.
- If an entry reaction knocks a hero down, the hero remains on the entered hex and stops moving.
- **House rule:** Leaving an enemy's legal melee reach triggers a +2 melee parting attack before the step. The same once-per-movement limit applies to each enemy across entry and exit reactions.
- A hero cannot move through rock, furniture, a closed door or an enemy, and cannot end movement on another unit. A hero may pass through an ally. Open doors do not block movement.

## Attacks and line of sight

- Adjacent enemies can be attacked in melee. Ranged attacks use the weapon's range increments and ammunition rules.
- Rock, furniture and closed doors block line of sight. Targeted attacks and spells beyond adjacency require clear line of sight.
- A natural 1 misses. A natural 20 hits.
- Melee from behind gives +2, except a rogue's sneak attack uses its own rule.

## Elevation and weapon reach

Elevation is local to the current dungeon floor. It does not describe which dungeon floor the party is on.

- A visible pit or connected channel marks -1 elevation; a table or barrel marks +1; a raised wall ledge marks +2. Bookshelves are furniture, not walkable high ground. A sprung pit trap becomes an open -1 depression, while its trap state remains recorded separately.
- Table and barrel platforms are traversable. A hero adjacent to a table can spend an action to break it with d20 + Physical rank + STR modifier + steady-ground bonus against DC 12. Failure leaves it intact. Success lowers it to ground; a unit on it takes 1 HP falling damage. Barrels are not breakable under this rule.
- +2 raised ledges require the Physical skill and a Climb check: d20 + Physical rank + STR modifier against DC 20. A hero without Physical skill or who fails stays below and takes 2 HP damage.
- Ordinary melee weapons require equal elevation. Polearms can reach one elevation level and get +1 attack when striking down; they cannot reach across two levels.
- Crossbows can reach two elevation levels: +1 attack per level when firing down and -1 per level when firing up.
- Short bows can reach one elevation level without a vertical modifier.
- Longbows can reach two elevation levels: at most +1 when firing down and -1 per level when firing up.
- Horizontal range and line of sight still apply to ranged attacks.

## Spells

- Casting uses an action. Spell cost is paid in HP: 1 + twice the spell level, reduced by 1 for a signature spell. HP spent this way is spell debt and cannot be healed during the battle.
- A spell that allows a save uses DC 10 + caster level + MIND modifier.
- A hero must have enough current HP to pay the spell cost and remain conscious.
- **House rule:** Casting while adjacent to a living enemy requires a focus check: d20 + caster level + MIND modifier + steady-ground bonus against DC 15 + spell level. Combat Casting adds +4.
- A failed focus check spends the spell's HP cost and action, but the spell has no effect. Moving away first avoids the check, but leaving adjacency with line of sight can provoke the parting attack above.

## Skills, traps and treasure

- Searching checks within 2 hexes and the whole room the searcher occupies for hidden traps and secret doors. A visible enemy blocks a search.
- Only party members spring hidden traps. A discovered trap can be disarmed if its type permits it.
- A hero can open an adjacent chest using an action. **House rule:** on floor N a chest holds N rolls of 2d6 x 5 gold and N items; a handcrafted map counts as floor one.
- A hero next to a fallen ally can spend an action to move that ally's remaining pack and gear into the battle's loot.
- A pit trap deals 1 damage and leaves the hero in the pit until they spend movement to climb out. A sprung pit stays open.

## Dungeon floors and loot

- Random dungeon runs and campaign delves each have three floors.
- Floor 1 enemies: goblins, kobolds, skeletons and zombies. Floor 2: hobgoblins, orcs and war dogs. Floor 3: an ogre or troll boss.
- **House rule:** each floor has stairs. Floors one and two have stairs down (`>`) in the lair room, the room farthest from the entry. Floor three has its way out (`<`) in the entry room. The stairs are outlined on the map and are always visible, since the whole map fits the window.
- When the floor's enemies are defeated, the party enters a search phase. Heroes can keep moving, opening chests, searching and recovering. Search rounds do not advance enemy turns or timed effects.
- **Source-derived, adapted:** Moldvay's wandering-monster check, adapted to search rounds. After every second search round, roll 1d6. On a 1, 1d3 wandering monsters from the floor's band arrive out of every hero's line of sight, at about 2d6 x 2 hexes and no closer than 4 hexes. The party acts first in the next round; the arrivals act at the next enemy phase. A new arrival group has its own morale. The first search round never rolls, and nothing is rolled during combat.
- Taking the stairs ends the floor. Its loot is banked, and the party descends to the next floor. Leaving floor three by its way out ends the dungeon.
- Defeat ends the run at once, and the floor is not counted as cleared.
- Standalone dungeon loot accumulates across floors and is shown in the final result once.
- Campaign heroes carry HP, spell debt, equipment and items between floors. Town opens after the third floor or after defeat.

## Campaign and town

- The campaign has four active heroes and four reserve recruits. The active roster can be changed in town.
- Town sells ordinary equipment and ammunition. Potions, holy water, oil and spell scrolls are dungeon finds.
- Rest in town restores HP, spell debt and drained Strength.
- Checkpoint spell picks require the appropriate teacher to be available. A dungeon scroll can teach an eligible unknown spell in town when its class teacher is present.

## Map objectives and shrines

- On an altar map, a hero on the altar can spend an action to claim it. Hold through an enemy phase with no adjacent enemy to secure it. Leaving the altar, falling or being defeated loses the claim. Defeating all enemies also wins.
- A hero on a shrine can spend an action to recover up to 4 HP, if the shrine has a charge. Healing does not restore spell debt.

## Interface

- The arrangement of the screen is governed by `layout.md`.
- The stats panel clips overflow inside its fixed height; the game never shows a scrollbar (layout.md, LAY-2).
- Select a reachable hex once to preview movement and select it again to confirm.
- When standing on stairs, the stairs control appears. It is locked with a reason while enemies live, and takes the stairs once the floor is in search. The stairs are outlined on the map and are always visible, since the whole map fits the window; the banner says the stairs are marked on the map.
- The action log records attacks, movement, searches, treasure and other outcomes.
