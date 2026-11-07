# Use Case: Use Item

## Overview

**Use Case ID:** UC-027  
**Use Case Name:** Use Item  
**Primary Actor:** Player  
**Goal:** A hero uses an item from its pack for its effect in the battle.  
**Trigger:** Player selects Use item for a ready hero and chooses an item.  
**Status:** Draft  

**Requirements:** [FR-046, FR-045](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The hero is ready and carries at least one usable item.

## Main Success Scenario

1. Player selects a ready hero.
2. Player selects Use item, and the menu lists the items the hero carries that have a use.
3. Player chooses an item and a target when the item needs one.
4. System applies the item's effect and removes one use of it.
5. System spends the hero's action.

## Alternative Flows

### A1: No Usable Item

**Trigger:** The hero carries no item with a use (step 2)  
**Flow:**

1. System shows no entries under Use item.
2. Use case ends.

## Postconditions

### Success Postconditions

- The item's effect is applied and one use is spent.

### Failure Postconditions

- A refused use spends no item and no action.

## Business Rules

### BR-001: Charged Items

A charged item such as a wand loses one charge per use. At zero charges it is spent.

### BR-002: Magic Items

Potions of Strength and Regeneration, the Ring of Protection, the Wand of Magic Missile, the Scroll of Sleep and the Amulet of Health are usable from the action radial.
