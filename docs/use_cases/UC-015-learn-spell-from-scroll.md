# Use Case: Learn Spell From Scroll

## Overview

**Use Case ID:** UC-015  
**Use Case Name:** Learn Spell From Scroll  
**Primary Actor:** Player  
**Goal:** A caster learns an unknown spell from a dungeon scroll.  
**Trigger:** Player selects a spell scroll from the stash for a caster in town.  
**Status:** Draft  

**Requirements:** [FR-035](../requirements.md)

## Preconditions

- The party is in town.
- The stash holds at least one spell scroll.

## Main Success Scenario

1. Player selects a caster in town.
2. Player selects a spell scroll and the spell it teaches.
3. System checks that the spell belongs to the caster's class, is within the caster's cap, is not already known, and that the class teacher is in town today.
4. System consumes one spell scroll from the stash.
5. System adds the spell to the caster's known spells.

## Alternative Flows

### A1: Study Refused

**Trigger:** A check in step 3 fails (step 3)  
**Flow:**

1. System refuses the study and states the reason.
2. Use case ends.

### A2: Delve Running

**Trigger:** A delve is running (step 1)  
**Flow:**

1. System refuses the study.
2. Use case ends.

## Postconditions

### Success Postconditions

- The stash holds one spell scroll fewer.
- The caster knows the spell.

### Failure Postconditions

- A refused study leaves the stash and the caster's spells unchanged.

## Business Rules

### BR-001: Class Match

A scroll teaches only a spell on the caster's class list.

### BR-002: Experience Not Required

A scroll bypasses experience, but not the class, caster cap, or teacher checks.
