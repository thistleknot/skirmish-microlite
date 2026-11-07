# Use Case: Collect Loot

## Overview

**Use Case ID:** UC-010  
**Use Case Name:** Collect Loot  
**Primary Actor:** Player  
**Goal:** The party takes the gold and items from a chest or from a fallen ally's gear.  
**Trigger:** Player selects Open for a chest, or Recover for a fallen ally, next to a ready hero.  
**Status:** Draft  

**Requirements:** [FR-019, FR-020, FR-029](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The hero has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero standing next to a chest or next to a fallen ally.
2. Player selects Open for the chest, or Recover for the ally.
3. System opens the chest, rolling its gold and drawing its items, or moves the fallen ally's pack and gear into the battle's loot.
4. System adds the gold and items to the battle's loot.
5. System spends the hero's action.

## Alternative Flows

### A1: Nothing Adjacent

**Trigger:** No chest or fallen ally is next to the hero (step 1)  
**Flow:**

1. System refuses the action.
2. Use case ends.

### A2: Ally Already Looted

**Trigger:** The fallen ally has already been looted (step 2)  
**Flow:**

1. System refuses the action.
2. Use case ends.

## Postconditions

### Success Postconditions

- The chest is opened, or the fallen ally's gear is in the battle's loot.
- The hero has spent its action.

### Failure Postconditions

- A refused action adds no gold or items to the loot.

## Business Rules

### BR-001: Chest Contents

On floor N a chest holds N rolls of 2d6 × 5 gold and N items. A handcrafted map counts as floor one.

### BR-002: Enemy Gold

A defeated enemy yields gold equal to d4 rolled once per hit die. The gold is paid when the floor's enemies are defeated, or when the battle is won.
