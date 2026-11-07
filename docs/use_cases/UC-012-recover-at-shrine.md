# Use Case: Recover at Shrine

## Overview

**Use Case ID:** UC-012  
**Use Case Name:** Recover at Shrine  
**Primary Actor:** Player  
**Goal:** A hero recovers up to 4 HP at a shrine during the battle.  
**Trigger:** Player selects the shrine action for a ready hero standing on the shrine.  
**Status:** Draft  

**Requirements:** [FR-022](../requirements.md)

## Preconditions

- The battle is on a map with a shrine.
- The hero has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero standing on the shrine.
2. Player selects the shrine action.
3. System heals the hero by up to 4 HP, not above its maximum minus its spell debt.
4. System spends one charge of the shrine.
5. System spends the hero's action.

## Alternative Flows

### A1: Shrine Spent

**Trigger:** The shrine has no charge left (step 1)  
**Flow:**

1. System refuses the action.
2. Use case ends.

### A2: Already at Cap

**Trigger:** The hero is at its healing cap (step 1)  
**Flow:**

1. System refuses the action.
2. Use case ends.

## Postconditions

### Success Postconditions

- The hero has recovered up to 4 HP.
- The shrine has one charge fewer.

### Failure Postconditions

- A refused action spends no charge and changes no HP.

## Business Rules

### BR-001: Spell Debt Stays

Shrine healing never restores spell debt.

### BR-002: Charges

The shrine on the altar map holds one charge.
