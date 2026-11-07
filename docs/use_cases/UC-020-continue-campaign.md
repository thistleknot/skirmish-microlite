# Use Case: Continue Campaign

## Overview

**Use Case ID:** UC-020  
**Use Case Name:** Continue Campaign  
**Primary Actor:** Player  
**Secondary Actors:** Browser Storage  
**Goal:** The player resumes the saved campaign.  
**Trigger:** Player opens the game page.  
**Status:** Draft  

**Requirements:** [FR-031, C-003](../requirements.md)

## Preconditions

- The game page is opened in this browser.

## Main Success Scenario

1. Player opens the game page.
2. System reads the saved campaign from Browser Storage.
3. System restores the roster, gold, stash, day count, and experience, and shows the town.

## Alternative Flows

### A1: No Saved Campaign

**Trigger:** No saved campaign exists (step 2)  
**Flow:**

1. System starts a new campaign with the pregenerated roster: four active heroes and four in reserve.
2. Use case continues at step 3.

### A2: Unreadable Saved Campaign

**Trigger:** The saved data cannot be read (step 2)  
**Flow:**

1. System starts a new campaign, and the next save replaces the unreadable data (see OQ-003).
2. Use case continues at step 3.

### A3: Delve Was Running

**Trigger:** The saved campaign shows a delve in progress (step 3)  
**Flow:**

1. System abandons the delve, opens the town with the delve closed, and logs that the delve was abandoned when the game closed (see OQ-005).
2. Use case ends.

## Postconditions

### Success Postconditions

- The campaign shown matches the last saved state, except that a delve in progress is abandoned.

### Failure Postconditions

- A missing or unreadable save never stops the game from opening.

## Business Rules

### BR-001: One Campaign Per Browser

The campaign is kept in this browser only. No server stores it.

### BR-002: Missing Fields

Saved campaigns from earlier versions gain the fields they lack, and their hero records are kept.
