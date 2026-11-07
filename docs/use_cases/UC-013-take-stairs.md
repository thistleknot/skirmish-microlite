# Use Case: Take Stairs

## Overview

**Use Case ID:** UC-013  
**Use Case Name:** Take Stairs  
**Primary Actor:** Player  
**Goal:** The party leaves a cleared floor, going deeper or leaving the dungeon.  
**Trigger:** Player selects the stairs with a living party hero standing on them.  
**Status:** Draft  

**Requirements:** [FR-023, FR-041](../requirements.md)

## Preconditions

- A dungeon run or a delve is in progress.
- The battle is in its search phase.

## Main Success Scenario

1. Player selects the stairs with a living party hero standing on them.
2. System checks that no enemy is alive on the floor.
3. System banks the floor's loot (see OQ-002).
4. System generates the next floor and places the party in its entry room, or on floor 3 ends the dungeon in victory.
5. In a campaign, System saves the campaign.

## Alternative Flows

### A1: Enemies Still Alive

**Trigger:** An enemy is still alive on the floor (step 2)  
**Flow:**

1. System keeps the stairs locked and states that enemies are still alive.
2. Use case ends.

## Postconditions

### Success Postconditions

- The party stands on the next floor, or the dungeon is won.
- On floor 3 the party is returned to town when it is a campaign delve.

### Failure Postconditions

- A refused use leaves the floor and the party unchanged.

## Business Rules

### BR-001: Stairs Placement

Floors one and two have stairs down in the room farthest from the entry. Floor three has the way out in the entry room.

### BR-002: No Action Cost

Taking the stairs costs no action, and any living party hero standing on the stairs may take them.

### BR-003: Loot Banking Point

Loot is banked on the stairs. The battle's loot reaches the campaign when the battle ends, and a floor ends at its stairs (see OQ-002).

### BR-004: Stairs Only

A cleared floor stays open for searching until the party takes its stairs.
