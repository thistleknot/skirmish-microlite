# Use Case: Finish Knocked-Out Enemy

## Overview

**Use Case ID:** UC-026  
**Use Case Name:** Finish Knocked-Out Enemy  
**Primary Actor:** Player  
**Goal:** The party kills a knocked-out enemy so that it can no longer rise.  
**Trigger:** Player selects Coup de grace for a ready hero next to a knocked-out enemy.  
**Status:** Draft  

**Requirements:** [FR-044, FR-043](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The hero is ready and has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero standing next to a knocked-out enemy.
2. Player selects Coup de grace.
3. System kills the enemy.
4. System spends the hero's whole activation.

## Alternative Flows

### A1: No Knocked-Out Enemy Adjacent

**Trigger:** No knocked-out enemy is next to the hero (step 1)  
**Flow:**

1. System refuses the action.
2. Use case ends.

## Postconditions

### Success Postconditions

- The enemy is dead and cannot act or be aided.

### Failure Postconditions

- A refused coup de grace changes no state of any enemy.

## Business Rules

### BR-001: Knocked Out Is Not Dead

An enemy at 0 HP is knocked out, not dead. It cannot act until it is finished, and it is not counted as defeated until then.

### BR-002: Enemy Mutual Aid

An awake enemy next to a knocked-out ally may stand it up at 1 HP. An enemy separated from the ally does not.
