# Use Case: Attack Enemy

## Overview

**Use Case ID:** UC-002  
**Use Case Name:** Attack Enemy  
**Primary Actor:** Player  
**Goal:** The player wears an enemy down with a melee, ranged, flask or charge attack.  
**Trigger:** Player selects an enemy as the target of a ready hero's attack.  
**Status:** Draft  

**Requirements:** [FR-004, FR-005, FR-006, FR-010, FR-013](../requirements.md)

## Preconditions

- The battle is in a player phase.
- The hero has not yet used its action.

## Main Success Scenario

1. Player selects a ready hero.
2. Player selects an enemy within the hero's melee reach, or within its ranged weapon's range with a clear line of sight.
3. System rolls the attack against the enemy's armor class and reports the result.
4. System applies the damage to the enemy and marks it defeated when its hit points reach 0.
5. System ends the hero's activation, so the hero cannot move afterwards.

## Alternative Flows

### A1: Target Out of Reach

**Trigger:** The enemy is outside melee reach, or outside range or without a clear line of sight (step 2)  
**Flow:**

1. System refuses the attack and states the reason.
2. Use case continues at step 2.

### A2: No Ammunition

**Trigger:** The hero's ranged weapon has no ammunition left (step 2)  
**Flow:**

1. System refuses the attack.
2. Use case continues at step 2.

### A3: Thrown Flask

**Trigger:** Player throws oil or holy water instead of attacking with a weapon (step 2)  
**Flow:**

1. System rolls the throw against the enemy's armor class, and on a hit deals 1d6 damage.
2. Use case continues at step 4.

### A4: Charge

**Trigger:** Player chooses a charge against a distant enemy (step 2)  
**Flow:**

1. System moves the hero along a straight, clear line of approach that ends beside the enemy.
2. System resolves the attack from that tile.
3. Use case continues at step 4.

### A5: Sneak Attack

**Trigger:** A rogue strikes an enemy from behind, or with an ally on the far side of it (step 3)  
**Flow:**

1. System makes a sneak attack roll in place of the normal attack roll.
2. Use case continues at step 4.

## Postconditions

### Success Postconditions

- The enemy has fewer hit points, or it is defeated.
- The hero has used its whole activation.

### Failure Postconditions

- A refused attack changes no hit points and spends no activation.

## Business Rules

### BR-001: Natural Rolls

A natural 1 misses and a natural 20 hits.

### BR-002: Attack From Behind

An attack from behind the enemy gets +2. A rogue's sneak attack uses its own rule instead.

### BR-003: Activation Cost

A committed weapon attack uses the hero's whole activation, so the hero cannot move afterwards.

### BR-004: Ammunition

Ammunition limits the shots of a ranged weapon. Reusable weapons (dagger, javelin) have no limit.
