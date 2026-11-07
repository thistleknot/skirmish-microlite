# Use Case: Start Campaign Delve

## Overview

**Use Case ID:** UC-019  
**Use Case Name:** Start Campaign Delve  
**Primary Actor:** Player  
**Goal:** The party begins a three-floor delve from town.  
**Trigger:** Player selects Start delve in town.  
**Status:** Draft  

**Requirements:** [FR-030](../requirements.md)

## Preconditions

- The party is in town with four active heroes.
- No delve is running.

## Main Success Scenario

1. Player selects Start delve in town.
2. System locks the town services for the delve: supplies, rest, roster changes, and scroll study are refused until the delve ends.
3. System generates floor 1 and places the party in its entry room.
4. System starts the battle on floor 1 as part of the campaign.
5. System saves the campaign.

## Alternative Flows

_None — starting a delve has no alternative flow; the delve's own outcomes are in UC-013 and UC-021._

## Postconditions

### Success Postconditions

- The campaign is in a delve, and the floor 1 battle is running.

### Failure Postconditions

- If the delve does not start, the town services stay open.

## Business Rules

### BR-001: Floor Pools

Floor 1 enemies are goblin, kobold, skeleton and zombie. Floor 2 enemies are hobgoblin, orc and war dog. Floor 3 enemies are ogre and troll.

### BR-002: Town Returns

Town opens after the third floor, or after a defeat.

### BR-003: Carry-Over

Heroes keep their HP, spell debt, gear and items between floors.
