# Use Case: Claim Altar

## Overview

**Use Case ID:** UC-011  
**Use Case Name:** Claim Altar  
**Primary Actor:** Player  
**Goal:** The party holds the altar and wins the altar map.  
**Trigger:** Player selects Claim for a ready hero standing on the altar.  
**Status:** Draft  

**Requirements:** [FR-021](../requirements.md)

## Preconditions

- The battle is on the altar map.
- The hero has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero standing on the altar.
2. Player selects Claim.
3. System records the hero as the claimant.
4. At the end of the next enemy phase, System checks that the claimant is still alive and on the altar, and that no enemy stands next to it.
5. System secures the altar and ends the battle in victory.

## Alternative Flows

### A1: Claim Lost

**Trigger:** The claimant leaves the altar, falls, or is defeated before the enemy phase ends (step 4)  
**Flow:**

1. System clears the claim.
2. Use case ends.

### A2: Contested

**Trigger:** An enemy stands next to the claimant at the end of the enemy phase (step 4)  
**Flow:**

1. System keeps the claim but does not secure the altar.
2. Use case continues at step 4.

## Postconditions

### Success Postconditions

- The battle ends in victory.

### Failure Postconditions

- A contested, lost, or unconscious claim does not win the altar.

## Business Rules

### BR-001: Defeat Also Wins

Defeating every enemy wins the altar map as well.

### BR-002: Claim Ends

A claim ends when the claimant leaves the altar, falls, or is defeated.
