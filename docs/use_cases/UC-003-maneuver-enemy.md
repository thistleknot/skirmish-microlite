# Use Case: Maneuver Enemy

## Overview

**Use Case ID:** UC-003  
**Use Case Name:** Maneuver Enemy  
**Primary Actor:** Player  
**Goal:** The player trips, pushes or disarms an adjacent enemy to control its position or its next attack.  
**Trigger:** Player selects trip, bull rush or disarm against an adjacent enemy.  
**Status:** Draft  

**Requirements:** [FR-009](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The hero has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero standing next to an enemy.
2. Player selects trip, bull rush or disarm.
3. System makes an opposed check for the hero and the enemy and compares the two results.
4. System applies the result: a trip knocks the enemy prone, a bull rush pushes it one tile away from the hero, and a disarm makes it lose its next attack.
5. System ends the hero's activation.

## Alternative Flows

### A1: Hero Loses the Check

**Trigger:** The hero's check does not beat the enemy's (step 3)  
**Flow:**

1. System reports the failed maneuver and leaves the enemy unchanged.
2. Use case continues at step 5.

### A2: Push Blocked

**Trigger:** The tile behind the enemy is rock, holds another unit, or differs in elevation by more than one level (step 4)  
**Flow:**

1. System reports that the enemy cannot be pushed and leaves it in place.
2. Use case continues at step 5.

## Postconditions

### Success Postconditions

- The enemy is prone, moved, or has lost its next attack, as the result states.
- The hero has used its whole activation.

### Failure Postconditions

- A failed maneuver leaves the enemy's position and its next attack unchanged.

## Business Rules

### BR-001: Opposed Check

Both sides roll d20 and add their maneuver bonus and their stand-your-ground bonus. The hero's total must beat the enemy's to succeed.

### BR-002: Activation Cost

A maneuver uses the hero's whole activation.
