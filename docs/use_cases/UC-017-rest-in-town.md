# Use Case: Rest in Town

## Overview

**Use Case ID:** UC-017  
**Use Case Name:** Rest in Town  
**Primary Actor:** Player  
**Goal:** The party starts the next delve with full HP, no spell debt, and full Strength.  
**Trigger:** Player selects Rest in town.  
**Status:** Draft  

**Requirements:** [FR-039](../requirements.md)

## Preconditions

- The party is in town.

## Main Success Scenario

1. Player selects Rest in town.
2. System sets each party hero's HP to its maximum, clears its spell debt, and restores its drained Strength.
3. System advances the day by one.
4. System records the rest in the campaign log.
5. System saves the campaign.

## Alternative Flows

### A1: Delve Running

**Trigger:** A delve is running (step 1)  
**Flow:**

1. System refuses the rest and states that the party must finish the delve first.
2. Use case ends.

## Postconditions

### Success Postconditions

- Every party hero has full HP, no spell debt, and full Strength.
- The day count has risen by one.

### Failure Postconditions

- A refused rest changes no hero and no day count.

## Business Rules

### BR-001: Party Only

Rest applies to the party heroes only. Reserve heroes keep their state.
