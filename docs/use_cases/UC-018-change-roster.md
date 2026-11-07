# Use Case: Change Roster

## Overview

**Use Case ID:** UC-018  
**Use Case Name:** Change Roster  
**Primary Actor:** Player  
**Goal:** The party is changed to suit the next delve.  
**Trigger:** Player selects a reserve hero to swap with a party hero in town.  
**Status:** Draft  

**Requirements:** [FR-040](../requirements.md)

## Preconditions

- The party is in town.
- No delve is running.

## Main Success Scenario

1. Player selects a party hero to leave the party.
2. Player selects a reserve hero to join the party.
3. System swaps the two heroes between the party and the reserve.
4. System saves the campaign.

## Alternative Flows

### A1: Invalid Selection

**Trigger:** The selected hero is not in the party or the reserve (step 1 or step 2)  
**Flow:**

1. System refuses the swap.
2. Use case ends.

### A2: Delve Running

**Trigger:** A delve is running (step 1)  
**Flow:**

1. System refuses the swap.
2. Use case ends.

## Postconditions

### Success Postconditions

- The party and the reserve hold the swapped heroes.

### Failure Postconditions

- A refused swap leaves the roster unchanged.

## Business Rules

### BR-001: Roster Sizes

The party holds four heroes and the reserve holds four.
