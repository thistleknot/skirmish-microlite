# Use Case: Aid Downed Ally

## Overview

**Use Case ID:** UC-025  
**Use Case Name:** Aid Downed Ally  
**Primary Actor:** Player  
**Goal:** The party brings a downed hero back to 1 HP so it does not die.  
**Trigger:** Player selects Aid downed for a ready hero next to a downed ally.  
**Status:** Draft  

**Requirements:** [FR-042, FR-045](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The aiding hero is ready and has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero standing next to a downed ally.
2. Player selects Aid downed.
3. System rolls d20 + Survival rank + MIND bonus against DC 10.
4. System brings the ally to 1 HP and leaves it Wounded.
5. System spends the aiding hero's whole activation.

## Alternative Flows

### A1: Roll Fails

**Trigger:** The roll is below DC 10 (step 3)  
**Flow:**

1. System reports the failed aid and leaves the ally down.
2. Use case continues at step 5.

## Postconditions

### Success Postconditions

- The ally is alive at 1 HP.

### Failure Postconditions

- A failed aid changes no HP and no state of the ally.

## Business Rules

### BR-001: Downed Hits Kill

A further hit on a downed hero kills it outright. A downed hero defends at its base armor class.

### BR-002: Aid Uses the Whole Activation

Aid downed uses the aiding hero's whole activation.
