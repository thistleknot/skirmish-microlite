# Use Case: Cast Spell

## Overview

**Use Case ID:** UC-005  
**Use Case Name:** Cast Spell  
**Primary Actor:** Player  
**Goal:** A caster hits an enemy, heals a hero, or protects a hero by paying HP.  
**Trigger:** Player selects a known spell for a ready caster.  
**Status:** Draft  

**Requirements:** [FR-007, FR-008](../requirements.md)

## Preconditions

- The caster knows the spell.
- The caster is conscious and has not yet used its action.

## Main Success Scenario

1. Player selects a ready caster and a known spell.
2. Player selects a target within the spell's range, or the caster itself.
3. System checks whether the caster stands next to a living enemy and, if so, makes the focus check.
4. System deducts the spell's HP cost from the caster and records it as spell debt.
5. System resolves the spell's effect on the target; a save uses the spell DC.
6. System spends the caster's action.

## Alternative Flows

### A1: Not Enough HP

**Trigger:** The caster's HP would not cover the cost and stay above 0 (step 1)  
**Flow:**

1. System refuses the spell.
2. Use case ends.

### A2: Target Out of Range

**Trigger:** The target is out of the spell's range or line of sight (step 2)  
**Flow:**

1. System refuses the spell.
2. Use case continues at step 2.

### A3: Focus Check Fails

**Trigger:** The caster is next to a living enemy and fails the focus check (step 3)  
**Flow:**

1. System deducts the HP cost and spends the action, and the spell has no effect.
2. Use case ends.

## Postconditions

### Success Postconditions

- The caster's spell debt has risen by the spell's HP cost.
- The caster has used its action.

### Failure Postconditions

- A refused spell spends no HP and no action.

## Business Rules

### BR-001: HP Cost

A spell costs 1 + 2 × spell level HP. A signature spell costs 1 HP less.

### BR-002: Spell DC

A spell that allows a save uses DC 10 + caster level + MIND bonus.

### BR-003: Focus Check

While next to a living enemy, a caster rolls d20 + caster level + MIND bonus + stand-your-ground bonus against 15 + spell level. The Combat Casting feat adds +4.

### BR-004: Spell Debt

Spell debt cannot be healed during the battle. Resting in town clears it.

### BR-005: Moving Away

Moving away from the enemy first avoids the focus check. The move can still draw the enemy's parting attack (UC-006).
