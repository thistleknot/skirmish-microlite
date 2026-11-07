# Use Case: Start Dungeon Run

## Overview

**Use Case ID:** UC-024  
**Use Case Name:** Start Dungeon Run  
**Primary Actor:** Player  
**Goal:** The player plays a standalone three-floor dungeon run for loot.  
**Trigger:** Player selects the dungeon run option on the skirmish screen.  
**Status:** Draft  

**Requirements:** [FR-002, FR-028](../requirements.md)

## Preconditions

- The game page is open.
- No battle is running.

## Main Success Scenario

1. Player selects the dungeon run option.
2. System generates floor 1 and places the four pregenerated heroes in its entry room.
3. System starts the battle on floor 1.
4. Player plays the floor through the combat use cases until its enemies are defeated.
5. Player takes the floor's stairs to continue, until floor 3's way out ends the run in victory.

## Alternative Flows

### A1: Party Defeated

**Trigger:** The party is defeated on any floor (step 4)  
**Flow:**

1. System ends the run in defeat, and the lost floor is not counted as cleared.
2. Use case ends.

## Postconditions

### Success Postconditions

- The run ends in dungeon victory, with the loot shown once in the final result.

### Failure Postconditions

- A lost floor is not counted as cleared.

## Business Rules

### BR-001: Standalone Loot

Loot accumulates across floors and is shown once, in the final result.

### BR-002: No Campaign Effect

A dungeon run changes no campaign record.
