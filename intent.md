# Design intent

Operator's intent for how the game should grow. The rules in `rules.md` are the current state; this file records where the design is going and why. Where the two disagree, the spec files say what is built and this file says what was meant.

## Advancement: pre-fab levels distilled into feats

- **Levels as the reference points.** The game should keep the feel of a Microlite-style campaign at book levels **3, 5 and 8**. Each checkpoint is a moment of growth for a hero, not a stat table.
- **Distill the differences.** At each of those levels, compare the characters the books would produce. Separate what comes from race (stat buffs) from what comes from class (which stats a class leans on, and what it gains). Stats come before class: a class benefits from some stats more than others.
- **Turn the differences into feats, not levels.** Each distilled delta becomes a feat, instead of a raw "greater HP" step. A feat is a choice card, closer to a Magic: The Gathering card than to a stat line.
- **Flavour through feats.** A feat can carry effects beyond numbers. Example from the operator: **a temporary bonus to HP while the feat is active.**
- **Offer more than you take.** Up to **five options** are offered at each advancement; the hero takes **three**. A player picks, or the choice can be random.

### Generic option vectors (loose, not a fixed list)

These were examples, not the limit of the design:

- +1 attack
- +1 hit points (or a temporary hit-point bonus while the feat is active)
- +1 skill (Pathfinder LITE approach to skills, see [inspirations.md](./inspirations.md))
- +1 dodge (may be folded into specific skills instead)
- +1 spell

Attack and dodge can be collapsed into named skills if that fits the skill system better. The operator explicitly did not want the list limited: any vector that makes a choice more flavourful is in scope.

## What this intent does not yet settle

- **Power scale (operator, 2026-11-06).** Level 3 and 5 are novice heroes. Level 8 is minor-league local hero, not superhero status. Level 13 is major league. Level 21 is Olympian. Checkpoint 13 stays. The game has no checkpoint or turn-table row at 21; the turn table stops at level 20.
- **Current code versus intent.** The code's advancement options (`OPTIONS`, `offerFor`) use the older option set and do not yet build feats as the distilled deltas described here.
- **Turn Undead.** Uses per battle follow caster level, the checkpoint level a hero reaches (see `docs/use_cases/UC-004-turn-undead.md`). The reload code still uses attack bonus; that gap is a code defect, not a design choice.
