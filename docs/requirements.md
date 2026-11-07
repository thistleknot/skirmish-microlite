# Requirements

Derived from the player rules (`rules.md`), the screen layout rules (`layout.md`), the decision record (`interpretations.md`), the design review (`features.md`), and the behavior of `index.html` as of 2026-11-03. No vision document exists yet; these sources stand in for one. Terms follow [glossary](glossary.md).

Every functional requirement is written as a player's user story, because the player is the only role that asks the game for something. Enemy and dungeon behavior appears as what the player experiences.

## Functional Requirements

| ID     | Title                     | User Story                                                                                                                                  | Priority | Status |
|--------|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|----------|--------|
| FR-001 | Start Skirmish            | As a player, I want to start a battle on a classic map or the altar map so that I can play a short tactical fight.                          | High     | Open   |
| FR-002 | Start Dungeon Run         | As a player, I want to start a random three-floor dungeon run so that I can face a longer challenge.                                        | High     | Open   |
| FR-003 | Preview Hero Move         | As a player, I want to preview a hero's route and its cost before I commit so that I can position heroes deliberately.                      | High     | Open   |
| FR-004 | Melee Attack              | As a player, I want an adjacent hero to attack an enemy in melee so that I can wear the enemy down.                                         | High     | Open   |
| FR-005 | Ranged Attack             | As a player, I want heroes to shoot or throw at enemies within weapon range and line of sight so that they can attack from a distance.      | High     | Open   |
| FR-006 | Throw Grenade             | As a player, I want to throw oil or holy water at an enemy so that I can deal damage without a weapon.                                      | Medium   | Open   |
| FR-007 | Cast Spell                | As a player, I want my caster to cast spells by paying HP so that magic has a real cost.                                                    | High     | Open   |
| FR-008 | Focus Check               | As a player, I want casting next to an enemy to require a focus check so that melee fighting disrupts spellcasting.                         | Medium   | Open   |
| FR-009 | Maneuver Enemy            | As a player, I want to trip, push or disarm an enemy so that I can control its position or its weapon.                                     | Medium   | Open   |
| FR-010 | Charge Enemy              | As a player, I want a hero to charge along a straight clear line so that it can close in and strike in one activation.                     | Medium   | Open   |
| FR-011 | Turn Undead               | As a player, I want my cleric to turn undead so that undead enemies can be driven off or destroyed.                                        | Medium   | Open   |
| FR-012 | Drink Healing Potion      | As a player, I want to drink a healing potion so that a hero recovers HP in the middle of a battle.                                        | Medium   | Open   |
| FR-013 | Sneak Attack              | As a player, I want a rogue to sneak attack an enemy it flanks or strikes from behind so that positioning rewards rogues.                  | Medium   | Open   |
| FR-014 | Enemy Reactions           | As a player, I want enemies to strike back when my hero enters or leaves their reach so that every route carries a risk.                   | High     | Open   |
| FR-015 | Climb Raised Ledge        | As a player, I want a hero with the Physical skill to climb onto a raised ledge with a Climb check so that high ground is open to skilled heroes. | Medium | Open   |
| FR-016 | Break Table               | As a player, I want an adjacent hero to break a table platform so that the table no longer gives high ground.                              | Low      | Open   |
| FR-017 | Search for Hidden Things  | As a player, I want my heroes to search their surroundings and their room so that hidden traps and secret doors are revealed.               | High     | Open   |
| FR-018 | Disarm Trap               | As a player, I want an adjacent hero to disarm a revealed trap so that it stops threatening the party.                                      | Medium   | Open   |
| FR-019 | Open Chest                | As a player, I want heroes to open an adjacent chest for gold and items so that each floor rewards exploration.                             | High     | Open   |
| FR-020 | Recover Fallen Ally       | As a player, I want a hero to take a fallen ally's pack and gear so that the party keeps its supplies.                                      | Medium   | Open   |
| FR-021 | Claim Altar               | As a player, I want a hero to claim the altar and hold it through an enemy phase so that I can win an altar map.                           | Medium   | Open   |
| FR-022 | Recover at Shrine         | As a player, I want a hero on a shrine to recover up to 4 HP so that the party can heal in place while the shrine has a charge.            | Medium   | Open   |
| FR-023 | Take Stairs               | As a player, I want to take the stairs once a floor's enemies are defeated so that I can move on or leave the dungeon.                      | High     | Open   |
| FR-024 | Keep Floor Open           | As a player, I want a cleared floor to stay open for searching until I take its stairs so that I decide when to leave.                      | High     | Open   |
| FR-025 | Wanderers Arrive          | As a player, I want wanderers to sometimes arrive during long searches so that lingering on a floor has a risk.                             | Medium   | Open   |
| FR-026 | Enemy Turn                | As a player, I want the enemies to act once my party has finished its activations so that the battle moves forward.                        | High     | Open   |
| FR-027 | Enemy Morale              | As a player, I want an enemy band to break and flee when it is hurt or half down so that a fight can end before every enemy dies.          | Medium   | Open   |
| FR-028 | Battle Result             | As a player, I want the battle to end in victory or defeat as soon as its end condition is met so that I know the result.                  | High     | Open   |
| FR-029 | Gold Reward               | As a player, I want defeated enemies to yield gold so that I can afford gear and supplies.                                                 | Medium   | Open   |
| FR-030 | Start Delve               | As a player, I want to start a delve from town with my party so that the campaign advances.                                                | High     | Open   |
| FR-031 | Continue Campaign         | As a player, I want my campaign restored when I reopen the game so that my progress is kept.                                               | High     | Open   |
| FR-032 | Autosave Campaign         | As a player, I want every campaign change saved in this browser so that closing the tab never costs me progress.                           | High     | Open   |
| FR-033 | Advancement at Checkpoint | As a player, I want each hero to receive advancement picks at every checkpoint so that heroes grow over the campaign.                      | High     | Open   |
| FR-034 | Teacher Required          | As a player, I want a checkpoint spell pick to need its class teacher in town so that spells are learned from the teachers who are there.   | Medium   | Open   |
| FR-035 | Learn Spell from Scroll   | As a player, I want a spell scroll to teach an eligible unknown spell in town so that dungeon finds keep their value.                      | Medium   | Open   |
| FR-036 | Buy Gear                  | As a player, I want to buy basic gear and ammunition in town so that heroes can be equipped and resupplied.                                | High     | Open   |
| FR-037 | Sell Items                | As a player, I want to sell stash items for half their price so that spare items turn into gold.                                           | Low      | Open   |
| FR-038 | Equip and Assign          | As a player, I want to equip gear and hand items to heroes in town so that each hero is ready for the next delve.                         | High     | Open   |
| FR-039 | Rest in Town              | As a player, I want to rest in town to restore HP, spell debt and drained Strength so that heroes start a delve fully ready.                | High     | Open   |
| FR-040 | Change Roster             | As a player, I want to move a reserve hero into the party in town so that I can adapt the party to the next delve.                         | High     | Open   |
| FR-041 | Return to Town            | As a player, I want the campaign to return me to town after a delve or a defeat so that I can recover and prepare.                         | High     | Open   |
| FR-042 | Aid Downed Ally           | As a player, I want to aid an adjacent downed hero so that it can be brought back to 1 HP before it dies.                                   | High     | Open   |
| FR-043 | Knock Out Enemy           | As a player, I want an enemy that reaches 0 HP to fall unconscious rather than die so that I can choose to finish it or leave it.           | High     | Open   |
| FR-044 | Coup de Grace             | As a player, I want to finish a knocked-out enemy with one action so that it can no longer rise.                                            | High     | Open   |
| FR-045 | Starting and Found Items  | As a player, I want my heroes to start with healing potions, enemies to carry items, and floor one to hold a magic item so that every floor offers new options. | High | Open |
| FR-046 | Use Item From Radial      | As a player, I want to use any item in a hero's pack from the action radial so that items are part of every battle.                         | High     | Open   |
| FR-047 | Camp for the Night        | As a player, I want my party to camp on a cleared floor to recover half its lost HP, with a one-in-six chance of interruption, so that I can recover mid-dungeon. | Medium | Open |

## Non-Functional Requirements

| ID      | Title                       | Requirement                                                                                                                                          | Category        | Priority | Status |
|---------|-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|----------|--------|
| NFR-001 | No Scrolling                | The game view has no vertical or horizontal scrollbar and no clipped map at window sizes 1280x800, 1036x647 and 390x844.                            | Usability       | High     | Open   |
| NFR-002 | Whole Map Visible           | The whole map, including the stairs tile, lies inside the map area at window sizes 1280x800, 1036x647 and 390x844.                                  | Usability       | High     | Open   |
| NFR-003 | Phone Layout                | At 390x844 the unit statistics and the action radial sit side by side directly below the map.                                                        | Usability       | Medium   | Open   |
| NFR-004 | Hex Scale                   | The hex size is between 10 and 22 px, or between 9 and 22 px on phones (640 px wide or narrower) and windows 500 px tall or shorter.                | Usability       | Medium   | Open   |
| NFR-005 | Stable Panels               | Turn status, unit statistics and action panels have identical heights after selecting a second unit, opening a submenu, previewing a move, and in the search phase. | Usability | Medium | Open |
| NFR-006 | Preview Is Side-Effect Free | A movement preview changes the game state by 0 values and draws 0 random rolls.                                                                      | Maintainability | High     | Open   |
| NFR-007 | Automated Verification      | All 404 engine gates pass, and every browser assertion passes: 166 of 166 at 1280x800 and 1036x647, 165 of 165 at 390x844.                          | Maintainability | High     | Open   |
| NFR-008 | Storage Failure             | When browser storage refuses a write, play continues and no uncaught error reaches the player.                                                        | Availability    | Medium   | Open   |

## Constraints

| ID    | Title            | Constraint                                                                                                  | Category  | Priority | Status |
|-------|------------------|-------------------------------------------------------------------------------------------------------------|-----------|----------|--------|
| C-001 | Single File      | The game is one HTML file with its script and styles inline, and no build step.                             | Technical | High     | Open   |
| C-002 | Static Hosting   | The game is served as static files, and the published page is `index.html` on GitHub Pages.                  | Technical | High     | Open   |
| C-003 | Browser Storage  | Campaign saves live in the browser's local storage under one key. No server stores anything.                 | Technical | High     | Open   |
| C-004 | No Network Calls | The page loads no external script, stylesheet or image and makes no network request during play.             | Technical | High     | Open   |
