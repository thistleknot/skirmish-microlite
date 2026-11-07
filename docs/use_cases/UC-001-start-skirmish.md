# Use Case: Start Skirmish

## Overview

**Use Case ID:** UC-001  
**Use Case Name:** Start Skirmish  
**Primary Actor:** Player  
**Goal:** The player plays one battle on a classic or altar map to a victory or a defeat.  
**Trigger:** Player selects a skirmish map and starts the battle.  
**Status:** Draft  

**Requirements:** [FR-001, FR-028, NFR-001, NFR-002, NFR-003, NFR-004, NFR-005, C-001, C-004](../requirements.md)

## Preconditions

- The game page is open.
- No battle is running.

## Main Success Scenario

1. Player selects one of the classic maps (Ridge Road, The Fords, Broken Keep) or the altar map (Seize the Altar).
2. System places the four party heroes on the map's start tiles and the enemies on theirs.
3. System starts round 1 with the party's activations.
4. Player plays the battle through the movement, attack and action use cases until the battle ends.
5. System ends the battle in victory when every enemy is defeated, or in defeat when no party hero is left standing.

## Alternative Flows

### A1: Altar Held

**Trigger:** The party holds the altar through an enemy phase (step 4)  
**Flow:**

1. System ends the battle in victory.
2. Use case ends.

## Postconditions

### Success Postconditions

- The battle shows its outcome as victory or defeat.

### Failure Postconditions

- A skirmish changes no campaign record.

## Business Rules

### BR-001: Standalone Battle

A skirmish uses the four pregenerated heroes and no campaign. Nothing a skirmish does is saved.

### BR-002: Victory Conditions

The battle ends in victory when no enemy is alive. On the altar map, holding the altar through an enemy phase, with no adjacent enemy, also ends the battle in victory (see UC-011).

### BR-003: Fixed Maps

The classic maps and the altar map have the same layout and the same enemy placement at every start.
