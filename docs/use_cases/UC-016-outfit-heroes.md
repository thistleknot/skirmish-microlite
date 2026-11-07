# Use Case: Outfit Heroes

## Overview

**Use Case ID:** UC-016  
**Use Case Name:** Outfit Heroes  
**Primary Actor:** Player  
**Goal:** Heroes get the gear, ammunition and items they need from town.  
**Trigger:** Player opens the town market and selects an action.  
**Status:** Draft  

**Requirements:** [FR-036, FR-037, FR-038](../requirements.md)

## Preconditions

- The party is in town.
- No delve is running.

## Main Success Scenario

1. Player selects an action: buy an item, sell an item from the stash, give an item to a hero, or equip gear on a hero.
2. System checks the action against the gold, the hero's class, and the item's type, and performs it when all checks pass.
3. System updates the gold, the stash, and the hero's records.
4. System reports the result in the log.

## Alternative Flows

### A1: Buy Refused

**Trigger:** The gold does not cover the price, or the item is not sold in town (step 2)  
**Flow:**

1. System refuses the purchase and states the reason.
2. Use case ends.

### A2: Equip Refused

**Trigger:** The hero's class cannot use the gear in that slot (step 2)  
**Flow:**

1. System refuses the equip and states the reason.
2. Use case ends.

### A3: Sell

**Trigger:** Player sells an item from the stash (step 1)  
**Flow:**

1. System adds half the item's price, rounded down, to the gold.
2. Use case continues at step 3.

## Postconditions

### Success Postconditions

- The gold, the stash, and the hero's records match the action performed.

### Failure Postconditions

- A refused action changes neither the gold nor the stash.

## Business Rules

### BR-001: Town Stock

Oakmoor sells basic gear, arrows and crossbow bolts only.

### BR-002: Market Closed During a Delve

Buying, selling, giving and equipping are closed while a delve runs.

### BR-003: Class Limits

Armor and shields are limited by class. The off-hand weapon must be a light weapon, and only fighters and rogues may use one.
