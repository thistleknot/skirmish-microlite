# Use Case: Camp for the Night

## Overview

**Use Case ID:** UC-028  
**Use Case Name:** Camp for the Night  
**Primary Actor:** Player  
**Goal:** The party recovers part of its lost HP on a cleared floor.  
**Trigger:** Player selects Camp for the night during the search phase.  
**Status:** Draft  

**Requirements:** [FR-047](../requirements.md)

## Preconditions

- The floor is in its search phase.
- No enemy is alive.
- Every living hero stands in the same room.

## Main Success Scenario

1. Player selects Camp for the night.
2. System rolls 1d6 for the night.
3. On 2 to 6, System restores each living hero by half its lost HP, rounded down and at least 1. Spell debt is unchanged.
4. System ends the night and the search phase continues.

## Alternative Flows

### A1: Night Interrupted

**Trigger:** The roll is a 1 (step 2)  
**Flow:**

1. System restores no HP.
2. System rolls for wanderers and gives the party a full warning round.
3. Each hero is Weary: -1 to d20 rolls until the next night that is not interrupted.
4. Use case ends.

### A2: Enemy Alive or Heroes Apart

**Trigger:** An enemy is alive, or the heroes are not all in one room (step 1)  
**Flow:**

1. System refuses the camp.
2. Use case ends.

## Postconditions

### Success Postconditions

- Each living hero has recovered half its lost HP.

### Failure Postconditions

- A refused camp changes no HP and no state.

## Business Rules

### BR-001: Night Is Not a Search Round

A night does not advance the search round count, and does not roll the wanderer check for search rounds.

### BR-002: Spell Debt Stays

Camping never clears spell debt. Only resting in town does.
