# Use Case: Advance Hero

## Overview

**Use Case ID:** UC-014  
**Use Case Name:** Advance Hero  
**Primary Actor:** Player  
**Goal:** Each hero takes the advancement picks it owes at its checkpoint.  
**Trigger:** A battle ends and a hero reaches a checkpoint, and Player opens the hero's picks in town.  
**Status:** Draft  

**Requirements:** [FR-033, FR-034](../requirements.md)

## Preconditions

- The party is in town.
- No delve is running.

## Main Success Scenario

1. System gives each hero that reached a checkpoint its three picks for that checkpoint.
2. Player selects a hero that owes picks.
3. System offers the options for that checkpoint.
4. Player selects an option and, where it needs one, its target.
5. System applies the option and reduces the hero's picks by one.
6. System repeats steps 3 to 5 until the hero owes no picks, and then ends the use case.

## Alternative Flows

### A1: Teacher Away

**Trigger:** Player selects the spell option, and the hero's class teacher is not in town today (step 4)  
**Flow:**

1. System keeps the spell option unavailable and leaves the other options open.
2. Use case continues at step 3.

### A2: Delve Running

**Trigger:** Player tries to take picks while a delve is running (step 2)  
**Flow:**

1. System refuses the picks.
2. Use case ends.

## Postconditions

### Success Postconditions

- The hero owes one pick fewer for each option taken.

### Failure Postconditions

- A refused option leaves the hero's options and picks unchanged.

## Business Rules

### BR-001: Checkpoints

Checkpoints are at 30, 100, 280 and 780 experience points. Each gives three picks.

### BR-002: Caster Level

A caster's level at each checkpoint is 1, 3, 5, 8 and 13.

### BR-003: Teacher Schedule

The skills trainer is always in town. The arcane tutor is in town on odd days, and the divine tutor on even days (see OQ-004).

### BR-004: Spell Cap

A spell option offers spells of the hero's class at or below half its caster level, rounded up.

### BR-005: Feats

A hero takes each feat once. Skill Focus gives +3 to the chosen skill.
