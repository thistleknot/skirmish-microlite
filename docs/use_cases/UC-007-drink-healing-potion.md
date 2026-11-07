# Use Case: Drink Healing Potion

## Overview

**Use Case ID:** UC-007  
**Use Case Name:** Drink Healing Potion  
**Primary Actor:** Player  
**Goal:** A hero recovers HP in the middle of a battle.  
**Trigger:** Player selects a healing potion from a ready hero's pack.  
**Status:** Draft  

**Requirements:** [FR-012](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The drinking hero has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero that carries a healing potion.
2. Player selects the potion and the party hero who drinks it.
3. System heals the hero by 1d8 + 1, up to its maximum HP minus its spell debt.
4. System removes one potion from the hero's pack.
5. System spends the hero's action.

## Alternative Flows

### A1: No Potion

**Trigger:** The selected hero carries no healing potion (step 1)  
**Flow:**

1. System refuses the drink.
2. Use case ends.

## Postconditions

### Success Postconditions

- The hero's HP has risen, and the hero carries one potion fewer.

### Failure Postconditions

- A refused drink removes no potion.

## Business Rules

### BR-001: Healing Cap

Healing never raises a hero's HP above its maximum minus its spell debt.

### BR-002: Potion Source

Potions are dungeon finds. Town does not sell them.
