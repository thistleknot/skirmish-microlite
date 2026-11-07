# Use Case: Search Floor

## Overview

**Use Case ID:** UC-008  
**Use Case Name:** Search Floor  
**Primary Actor:** Player  
**Goal:** The player finds hidden traps and secret doors before moving on.  
**Trigger:** Player selects Search for a ready hero.  
**Status:** Draft  

**Requirements:** [FR-017, FR-024, FR-025](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The hero has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero to search.
2. System checks that no enemy is visible to the hero, and refuses the search if one is.
3. System makes a search check for each hidden trap and secret door within 2 hexes of the hero, and in the room the hero stands in.
4. System reveals every trap and secret door the check finds, and reports them.
5. System spends the hero's action.
6. System ends the round, and at the end of every second search round it rolls 1d6 for wanderers.

## Alternative Flows

### A1: Enemy in Sight

**Trigger:** An enemy is visible to the hero (step 2)  
**Flow:**

1. System refuses the search.
2. Use case ends.

### A2: Wanderers Arrive

**Trigger:** The wanderer roll is a 1 (step 6)  
**Flow:**

1. System places 1d3 wanderers out of sight of every party hero, about 2d6 × 2 hexes away and at least 4 hexes from the nearest hero.
2. Each side rolls 1d6 for surprise, and a 1 or 2 surprises that side. Surprised wanderers lose their first enemy phase. If the party is surprised, the wanderers take an enemy phase before the party's next round. Otherwise the party acts first in the next round, and the wanderers act in the next enemy phase.
3. Use case ends.

## Postconditions

### Success Postconditions

- Every trap and secret door the check found is revealed.
- The hero has spent its action.

### Failure Postconditions

- A search that finds nothing changes no trap or door.

## Business Rules

### BR-001: Search Area

A search covers the traps and secret doors within 2 hexes of the searcher and the whole room the searcher stands in.

### BR-002: Wanderer Check

After every second search round, the game rolls 1d6, and a 1 brings wanderers. No check happens in the first search round or during combat.

### BR-003: Wanderer Pool

Wanderers come from the enemy pool of the current floor.

### BR-004: Search Rounds Do Not Advance Time

A search round does not advance enemy turns or timed effects.
