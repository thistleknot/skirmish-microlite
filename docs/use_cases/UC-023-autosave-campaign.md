# Use Case: Autosave Campaign

## Overview

**Use Case ID:** UC-023  
**Use Case Name:** Autosave Campaign  
**Primary Actor:** Player  
**Secondary Actors:** Browser Storage  
**Goal:** Every campaign change is kept in this browser.  
**Trigger:** A campaign change is made: a delve starts or ends, a hero changes, gear or items are bought or moved, the party rests, or the roster changes.  
**Status:** Draft  

**Requirements:** [FR-032, NFR-008, C-003](../requirements.md)

## Preconditions

- A campaign is in progress.

## Main Success Scenario

1. System writes the whole campaign to Browser Storage under the campaign's one key.

## Alternative Flows

### A1: Storage Refuses the Write

**Trigger:** Browser Storage refuses the write (step 1)  
**Flow:**

1. System keeps the game running and states that the change is not saved in this browser.
2. Use case ends.

## Postconditions

### Success Postconditions

- Browser Storage holds the campaign as it was after the change.

### Failure Postconditions

- A refused write leaves the previously saved campaign as it was, and the game keeps running.

## Business Rules

### BR-001: One Save Slot

The whole campaign is stored under one key in this browser.

### BR-002: Battle State Is Not Saved

Only the campaign is saved. A battle in progress is not saved.
