# Use Case: Move Hero

## Overview

**Use Case ID:** UC-006  
**Use Case Name:** Move Hero  
**Primary Actor:** Player  
**Goal:** The player places a hero on a chosen hex, paying movement along the way.  
**Trigger:** Player selects a reachable hex for a ready hero.  
**Status:** Draft  

**Requirements:** [FR-003, FR-014, FR-015, FR-016, NFR-006](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The hero has movement left in this activation.

## Main Success Scenario

1. Player selects a reachable hex for the hero.
2. System shows the route, its cost, the movement left, and any visible enemy reactions on the route.
3. Player selects the same hex again to confirm.
4. System moves the hero along the route one hex at a time, and each enemy whose reach the hero enters or leaves reacts once for this move.
5. System shows the hero's remaining movement and ends the move.

## Alternative Flows

### A1: Player Cancels

**Trigger:** Player does not confirm the route (step 3)  
**Flow:**

1. System keeps the hero where it stands and changes no state.
2. Use case ends.

### A2: Hero Downed by a Reaction

**Trigger:** An enemy's entry reaction reduces the hero to 0 HP (step 4)  
**Flow:**

1. System stops the hero on the hex it entered.
2. Use case ends.

### A3: Climb a Raised Ledge

**Trigger:** The route enters a raised ledge (step 4)  
**Flow:**

1. System requires the Physical skill and rolls a Climb check of d20 + Physical rank + STR modifier against DC 20.
2. On success, use case continues at step 5.
3. On failure, the hero stays below the ledge and takes 2 HP damage.
4. Use case ends.

### A4: Break a Table

**Trigger:** Player chooses to break a table platform next to the hero (step 1)  
**Flow:**

1. System rolls d20 + Physical rank + STR modifier + stand-your-ground bonus against DC 10, and the hero's action is spent.
2. On success, the table lowers to ground, and a unit standing on it takes 1 HP falling damage.
3. On failure, the table stays intact.
4. Use case ends.

## Postconditions

### Success Postconditions

- The hero stands on the chosen hex.
- The hero's movement is reduced by the route's cost.

### Failure Postconditions

- A hero never ends a move on an occupied hex, inside rock or furniture, or in a closed door.

## Business Rules

### BR-001: Movement Points

A hero has 6 movement points, plus 1 with Lightning Reflexes. Plain ground costs 1. Rubble and brush cost 2, and brush costs 1 for a ranger.

### BR-002: Passing Units

A hero may pass through an ally, but not through an enemy. A closed door blocks movement, and an open door does not.

### BR-003: Enemy Reactions

Entering an enemy's melee reach gives that enemy one melee attack with no extra bonus. Leaving its reach gives it a +2 parting attack. Each enemy reacts at most once per move. Fleeing and turned enemies do not react.

### BR-004: Facing

A move turns the hero to face the side it entered from.
