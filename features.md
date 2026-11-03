# NetHack feature inventory and fit for Microlite Tactics

## Source and scope

- **Source:** official [NetHack repository](https://github.com/NetHack/NetHack), release tag `NetHack-5.0.0_Released`, commit `16ff59115315917b93185d026aeefea06db9b0f4`.
- **Local clone:** `.tmp/nethack-source`, checked out detached at the release commit. The clone includes NetHack's own `dat/license`; its license applies to that source tree.
- **Evidence reviewed:** the release [Guidebook](https://github.com/NetHack/NetHack/blob/16ff59115315917b93185d026aeefea06db9b0f4/doc/Guidebook.txt), especially sections 2–8 and 10, plus the repository README. The code was not built or run for this inventory.
- **Scope:** this is a feature-family summary, not a complete list of NetHack objects, monsters, spells, commands, or level scripts. Observations describe NetHack; recommendations are design inferences for Microlite Tactics and are not implemented rules.

## Observed NetHack feature families

| Feature family | What NetHack provides | Guidebook evidence |
|---|---|---|
| Character identity | Roles and races have different abilities, starting gear, restrictions, and role quests; alignment affects play. | §§2, 7 |
| Dungeon structure | New dungeons combine generated levels with authored special levels, branches, stairs, portals, and role quests. | §§2, 5 |
| Exploration and navigation | The map records explored terrain; light, line of sight, remembered spaces, search, and travel commands shape exploration. | §§3–5 |
| Turn-consuming actions | Movement, combat, waiting, searching, item use, doors, and level travel are separate commands with different prompts and outcomes. | §4 |
| Hidden information | Traps and secret passages can be concealed, discovered through search or magic, and remembered on the map. | §5 |
| Tactical terrain and puzzles | Doors can be opened, locked, unlocked, trapped, or broken; pits and other traps affect movement. A Sokoban branch turns boulders, pits, and holes into a spatial puzzle. | §5 |
| Monsters and companions | Monsters have different senses, attacks, resistances, and reactions; some can be peaceful or tamed, and pets can follow the hero between levels. | §6 |
| Deep item system | Weapons, armor, tools, food, potions, scrolls, wands, containers, artifacts, and other objects support distinct actions and properties. | §7 |
| Uncertain item knowledge | Some item appearances are randomized per game; effects can reveal identity, and players can name unknown types for later reference. Items can also be blessed, uncursed, or cursed. | §7 |
| Equipment and encumbrance | Carried weight affects movement, reactions, and food use; equipment can be worn, wielded, damaged, repaired, or improved. | §7 |
| Survival pressure | Food, hunger, illness, poison, and other conditions create resource and time pressure. | §§6–7 |
| Religion and alignment | Prayer, sacrifice, altars, deities, and divine responses can help or harm depending on the character and situation. | §§2, 7 |
| Shops and economy | Shops price goods, trade with the hero, and react to theft and damage. | §§4, 7 |
| Optional conduct | The game tracks self-imposed challenges and records when an action breaks one. | §8 |
| Long-term objective and score | Treasure, the Amulet quest, escape/ascension, death, and end-of-game scoring frame a run beyond individual fights. | §§2, 10 |
| Accessibility and help | The guide describes symbol lookup, contextual command help, multiple display modes, and play with assistive output. | §§3–4 |

## Recommendations for Microlite Tactics

These are proposals, not borrowed rules. They are ranked by fit with the current four-hero, turn-based dungeon game.

### High fit: optional expedition conduct records

Track a few voluntary run challenges, such as **no hero downed**, **no healing items used**, or **all chests opened**. Show progress during a delve and award a small completion badge or campaign record. This adds replay goals without changing combat math; keep rewards cosmetic or modest so the challenges do not become required chores.

### High fit: a small set of terrain-object actions

Give a few existing props explicit tactical verbs: roll or push a barrel, topple a table, or use a boulder to block a passage or fill a pit. Each action should have a clear target preview, one stated cost, and a visible result. Start with one prop and one interaction so the board does not become a general physics simulation.

### Medium fit: optional branch objectives between floors

Offer a choice between the direct descent and one short side room with a puzzle, rescue, shrine, or extra treasure. This gives the existing three-floor run route choices without requiring NetHack-sized branches. Keep the main progression and descent path clear.

### Medium fit: identify and appraise magical finds

Let some loot arrive with a limited unknown property, then reveal it through a town service, a teacher, or safe use. The game already separates dungeon treasure from town services, so identification could give teachers another useful role. Start with one item category and avoid hidden effects that can permanently sabotage a hero.

### Defer: full survival and simulation layers

Hunger clocks, weight-based movement penalties, item erosion, broad curse interactions, pet AI, and permanent character death are rich NetHack systems, but together they would add tracking and failure costs to a game currently centered on short tactical encounters and a persistent roster. Add one only when play evidence shows that it serves the campaign loop.

## Attribution boundary

NetHack is a feature reference for this review, not a source of implemented Microlite Tactics mechanics. The recommendations above are inferred from the observed feature families and this game's existing structure. No NetHack source code or game text has been copied into the game.
