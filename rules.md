# Microlite Tactics: Player Rules

This is the player-facing reference for the rules the game currently enforces. It follows the game contract in `index.html`. A rule marked **House rule** is specific to this game. A note under **Not implemented** describes a proposal or source rule that the game does not currently use. See [Inspirations](./inspirations.md) for what the game borrowed or adapted from other systems and which sources informed design without supplying a current rule.

## Difficulty scale

Every check names its difficulty from one ladder. A check's DC is the rung that matches its difficulty.

| DC | Rung | Example |
|---|---|---|
| 5 | Easy | Spot a person in a crowd who is not hiding |
| 10 | Average | Break a table; hear someone moving nearby |
| 15 | Tough | Set a trap or sabotage a device; spell focus check |
| 20 | Challenge | Climb a rough dungeon wall; secret-door search |
| 25 | Formidable | Figure out something obscure outside your expertise |
| 30 | Heroic | Bull rush through a reinforced, braced door |
| 40 | Nearly impossible | Track a squad across hard ground after rain |

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
- **House rule (Heroism):** each hero has Heroism points equal to its caster level, refilled each battle. Spending one as a free action adds +1 to every d20 the hero rolls until the next player phase. A hero has at most one spent point active at a time.
- **House rule (downed):** a hero at 0 HP is downed. A further hit kills it, and it defends at base AC only. An adjacent ally can use Aid downed (d20 + Survival rank + MIND bonus vs DC 10) to bring it to 1 HP, leaving it Wounded.
- **House rule (knock out):** an enemy at 0 HP is knocked out, not dead. It cannot act until a Coup de grace kills it, and an awake enemy next to a knocked-out ally may stand it up at 1 HP.
- **House rule (Wounded):** a party hero at half its maximum HP or less rolls at -2 on every d20 until healed above half. Dead Simple Fantasy's Wounded state, without its skill penalty.

## Elevation and weapon reach

Elevation is local to the current dungeon floor. It does not describe which dungeon floor the party is on.

- A visible pit or connected channel marks -1 elevation; a table or barrel marks +1; a raised wall ledge marks +2. Bookshelves are furniture, not walkable high ground. A sprung pit trap becomes an open -1 depression, while its trap state remains recorded separately.
- Table and barrel platforms are traversable. A hero adjacent to a table can spend an action to break it with d20 + Physical rank + STR modifier + steady-ground bonus against DC 10 (average). Failure leaves it intact. Success lowers it to ground; a unit on it takes 1 HP falling damage. Barrels are not breakable under this rule.
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

## Magic items, curses and camping

- **Temporary items:** potions and scrolls are used from the action radial (Use item). Potion of Strength (+2 STR for the battle), Potion of Regeneration (1 HP at each of your turns for 5 turns), Scroll of Sleep (sleeps an adjacent foe for 10 rounds at caster level 1), and Wand of Magic Missile (1d4+1 per charge, six charges).
- **Permanent gear:** worn armor adds to armor class. Magic gear is never sold in town; it is found in the dungeon. Studded Leather +1 (+1 over studded), Elven Chain Mail (+1 over chain mail), and Robe (town stock).
- **Rings and amulets:** a Ring of Protection adds +1 armor class while carried. An Amulet of Health stops poison while carried. Neither is listed on the radial.
- **Trapped gear:** Poison Oak Armor adds +1 over studded leather. While worn it poisons its wearer 1d3 each turn. It comes off freely in town (Take it off).
- **Cursed artifact:** Hollow Mail gives +5 armor class and +2 temporary HP each battle, and -1 to every d20 while worn. It cannot be taken off or swapped until a town wizard lifts the curse for 300 gp. The uncursed mail goes to the stash.
- **Camp for the night:** during the search phase, with no enemy alive and every living hero in one room, the party may camp. A roll of 1 interrupts: no healing, wanderers may arrive, and each hero is Weary (-1 on every d20 until a night that is not interrupted). A roll of 2-6 heals each living hero by half its lost HP, rounded down and at least 1. Spell debt is unchanged, and the search round count does not advance.
- **Downed and knocked out:** see the downed and knock out house rules under Attacks.

## Dungeon floors and loot

- Random dungeon runs and campaign delves each have three floors.
- Floor 1 enemies: goblins, kobolds, skeletons and zombies, four of them. Floor 2: hobgoblins, orcs and war dogs, five of them. Floor 3: an ogre or troll boss with three more.
- **House rule:** each floor has stairs. Floors one and two have stairs down (a down-stairs icon) in the lair room, the room farthest from the entry. Floor three has its way out (an up-stairs icon) in the entry room. The stairs are outlined on the map and are always visible, since the whole map fits the window.
- When the floor's enemies are defeated, the party enters a search phase. Heroes can keep moving, opening chests, searching and recovering. Search rounds do not advance enemy turns or timed effects.
- **Source-derived, adapted:** Moldvay's wandering-monster check, adapted to search rounds. After every second search round, roll 1d6. On a 1, 1d3 wandering monsters from the floor's band arrive out of every hero's line of sight, at about 2d6 x 2 hexes and no closer than 4 hexes. The party acts first in the next round; the arrivals act at the next enemy phase. Surprise, Moldvay's 1d6 rule: on arrival each side rolls 1d6, and a 1 or 2 surprises that side. Surprised arrivals lose their first enemy phase. A surprised party gets the arrivals' enemy phase before its own round. A new arrival group has its own morale. The first search round never rolls, and nothing is rolled during combat.
- Taking the stairs ends the floor. Its loot is banked, and the party descends to the next floor. Leaving floor three by its way out ends the dungeon.
- Defeat ends the run at once, and the floor is not counted as cleared.
- Standalone dungeon loot accumulates across floors and is shown in the final result once.
- **House rule (serious injury, from Mordheim's D66):** a hero that is out of action (0 HP) at the end of a battle rolls D66: tens die, then units die. 11-35 is dead. 36-66 recovers at 1 HP. The 56-66 scar result is narrative only; it has no mechanical effect yet. A hero killed outright (overflow damage drains Strength) is dead without a roll.
- Campaign heroes carry HP, spell debt, equipment and items between floors. Town opens after the third floor or after defeat.

## Campaign and town

- The campaign has four active heroes and four reserve recruits. The active roster can be changed in town.
- Town sells ordinary equipment and ammunition. Potions, holy water, oil and spell scrolls are dungeon finds.
- Rest in town restores HP, spell debt and drained Strength.
- **House rule (hirelings):** town hires a man-at-arms for 60 gp. Two may be hired at most. Each delve costs 10 gp per hireling at its start; a hireling the company cannot pay leaves. Hirelings join the active company or the reserve like any hero, but take no checkpoint picks. Mordheim and HeroQuest hirelings and Moldvay retainers; they do not earn half XP, since campaign XP is shared, not per hero.
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
