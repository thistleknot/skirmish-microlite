# Use Case: Turn Undead

## Overview

**Use Case ID:** UC-004  
**Use Case Name:** Turn Undead  
**Primary Actor:** Player  
**Goal:** A cleric drives back or destroys an undead enemy.  
**Trigger:** Player selects Turn on an undead enemy within the cleric's range.  
**Status:** Draft  

**Requirements:** [FR-011](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The cleric has not yet used its action.
- The cleric has turning uses left in this battle.

## Main Success Scenario

1. Player selects a ready cleric.
2. Player selects an undead enemy.
3. System uses one turning use and looks up the outcome from the cleric's level and the enemy's hit dice.
4. System resolves the outcome: nothing happens, the enemy is turned, or the enemy takes damage and is turned or destroyed.
5. System spends the cleric's action.

## Alternative Flows

### A1: Turning Fails

**Trigger:** The outcome needs a roll and the roll fails (step 4)  
**Flow:**

1. System reports the failed roll and blocks another turning attempt against this enemy until the cleric's next player phase.
2. Use case continues at step 5.

### A2: No Uses Left

**Trigger:** The cleric has no turning uses left (step 1)  
**Flow:**

1. System refuses the turn and states that no uses are left.
2. Use case ends.

## Postconditions

### Success Postconditions

- The cleric has used one turning use.
- The enemy is turned, damaged, or destroyed, as the outcome states.

### Failure Postconditions

- A failed turn changes the enemy's hit points by 0.

## Business Rules

### BR-001: Uses Per Battle

A cleric has 2 + caster level + MIND bonus turning uses in each battle. Caster level is the checkpoint level the hero has reached (see OQ-001).

### BR-002: Outcome Table

The outcome follows the Basic Fantasy cleric-versus-undead table: cleric level against enemy hit dice. The table gives nothing happens, an automatic turn, an automatic damage-and-turn, or a roll. A natural 20 always succeeds on a roll.

### BR-003: Damage on Destruction

Where the outcome deals damage, the amount is the cleric's level in d8. The enemy is destroyed when the damage reduces it to 0 hit points.
