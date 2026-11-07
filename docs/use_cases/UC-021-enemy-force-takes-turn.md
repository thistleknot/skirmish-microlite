# Use Case: Enemy Force Takes Turn

## Overview

**Use Case ID:** UC-021  
**Use Case Name:** Enemy Force Takes Turn  
**Primary Actor:** Enemy Force  
**Goal:** The enemies move, strike, and test their morale, so that the battle moves forward.  
**Trigger:** Every ready party hero has used its move and its action.  
**Status:** Draft  

**Requirements:** [FR-026, FR-027, FR-028, FR-041](../requirements.md)

## Preconditions

- The battle is in its enemy phase.

## Main Success Scenario

1. System moves each living enemy toward the nearest party hero or the altar. A fled enemy moves away from the party instead.
2. System resolves each enemy's attack against a party hero within its reach or range. A hero reduced to 0 HP is marked down.
3. System checks morale for each enemy band that is hurt, or whose half is down.
4. System checks the end conditions: all enemies defeated, the altar held, or no party hero standing.
5. System starts the next player phase with the party's activations.

## Alternative Flows

### A1: Band Breaks

**Trigger:** A member of a band fails its morale roll (step 3)  
**Flow:**

1. System marks that enemy as fled, and it moves away on the next enemy phase.
2. Use case continues at step 4.

### A2: Hero Downed

**Trigger:** A party hero is reduced to 0 HP during the attacks (step 2)  
**Flow:**

1. System marks the hero down, and it can no longer act.
2. Use case continues at step 2.

### A3: Floor Cleared

**Trigger:** The last enemy of a dungeon floor is defeated (step 4)  
**Flow:**

1. System pays the enemies' gold and enters the search phase, so the floor stays open.
2. Use case ends.

## Postconditions

### Success Postconditions

- The battle has advanced one round.

### Failure Postconditions

- A defeat ends the battle at once. A floor lost in defeat is not counted as cleared.

## Business Rules

### BR-001: Morale Rolls

A band is checked when a member is hurt, or when half the band is down. Each member rolls 2d6 and flees if the roll is higher than its morale.

### BR-002: Morale 12

Members with morale 12 never flee. These are skeletons and zombies.

### BR-003: New Bands

Wanderers form a new band with its own morale.

### BR-004: Wanderer Timing

Wanderers act in the next enemy phase after they arrive.

### BR-005: Loot on Defeat

A defeat loses the battle's loot. Loot is banked only on victory, and the game has no escape that keeps it.
