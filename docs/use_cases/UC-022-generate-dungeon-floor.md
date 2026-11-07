# Use Case: Generate Dungeon Floor

## Overview

**Use Case ID:** UC-022  
**Use Case Name:** Generate Dungeon Floor  
**Primary Actor:** Player  
**Goal:** A playable dungeon floor is ready for the party.  
**Trigger:** A dungeon run starts, a delve starts, or the party takes the stairs down to a new floor.  
**Status:** Draft  

**Requirements:** [FR-002, FR-023, FR-030](../requirements.md)

## Preconditions

- A floor is needed for a dungeon run, a delve, or the next level.

## Main Success Scenario

1. System draws a floor of 18 by 12 hexes with rooms joined by corridors.
2. System places doors, secret doors, furniture, traps, and chests.
3. System places the stairs: on floors one and two, stairs down in the room farthest from the entry; on floor three, the way out in the entry room.
4. System places the party in the entry room.
5. System places the floor's enemies from its pool. Floor three holds an ogre or a troll.
6. System checks the layout against its validity rules, and tries again until it passes or 60 attempts have failed.

## Alternative Flows

### A1: Layout Never Passes

**Trigger:** All 60 attempts fail validation (step 6)  
**Flow:**

1. System uses the fixed Ridge Road map, with a stairs tile added, and logs that generation failed (see OQ-006).
2. Use case ends.

## Postconditions

### Success Postconditions

- The floor is ready, with the party in its entry room and the stairs placed.

### Failure Postconditions

- The party never enters a floor that failed validation.

## Business Rules

### BR-001: Attempt Limit

A floor gets up to 60 attempts to pass validation.

### BR-002: Floor Pools

Floor 1 enemies: goblin, kobold, skeleton, zombie. Floor 2: hobgoblin, orc, war dog. Floor 3: ogre, troll.
