# Use Case: Disarm Trap

## Overview

**Use Case ID:** UC-009  
**Use Case Name:** Disarm Trap  
**Primary Actor:** Player  
**Goal:** The party removes a revealed trap so that it cannot spring.  
**Trigger:** Player selects Disarm for a revealed trap next to a ready hero.  
**Status:** Draft  

**Requirements:** [FR-018](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The hero has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero standing next to a revealed trap that is still armed.
2. Player selects Disarm.
3. System rolls d20 + Subterfuge rank + DEX bonus + stand-your-ground bonus against the trap's disarm difficulty.
4. System disarms the trap when the roll is above the difficulty.
5. System spends the hero's action.

## Alternative Flows

### A1: Disarm Fails

**Trigger:** The roll is not above the disarm difficulty (step 4)  
**Flow:**

1. System reports the failure and leaves the trap armed.
2. Use case continues at step 5.

### A2: Trap Already Sprung

**Trigger:** The trap has already sprung (step 1)  
**Flow:**

1. System refuses the disarm.
2. Use case ends.

## Postconditions

### Success Postconditions

- The trap is disarmed and no longer springs.

### Failure Postconditions

- A failed disarm leaves the trap armed.

## Business Rules

### BR-001: Only Party Members Spring Traps

Traps spring only when a party member enters their tile. Enemies do not trigger them.
