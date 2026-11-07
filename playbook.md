# Playbook: Stairs, wandering monsters, map overlays
> Superseded 2026-11-06: its open T7 (overlay end-to-end check) is replaced by the downed-heroes, items and camping playbook at `.tmp/plans/structured-leaping-karp.md`.
Source: .tmp/plans/look-i-d-like-stats-jaunty-hearth.md (approved 2026-11-02); working copy .tmp/plan.md
Executed under DEC-04 (a): Leader writes .playbook/T<n>.subplan.md; one fresh doer per task. Parallel-layer lessons are written here by the Leader.

Objective (operator): the screen stays one size with stats bottom-left and the radial top-right as
translucent map overlays; a floor changes only when the party takes the stairs, so it can keep searching;
lingering risks wandering monsters; three floors per adventure with progressive monsters and treasure.

Baseline (BASE-02, 2026-11-03): browser suite 147/148 before any edit. Failing: "UX: fixed radial menu does not cover the unit stats window" at viewport 1036x647 (dial and stats overlap). Served by .tmp/static-serve.js on 127.0.0.1:8791 (process row in .tmp/processes.md).

## Layer 1 - sequential
- [DONE] T1 Rewrite the floor-end and layout contract in the game header
  _Files:_ index.html (header comment)
  _Verify:_ rg -n "R62|R63" finds rule lines at header 182 and 188; rg -n "automatically settle|unopened chests|scroll inside the panel" finds nothing in the header; R11, R46, R47, R51, R54 each mention stairs; node parse of the engine block passes
  _Lessons:_ header-only edits applied cleanly with exact old strings; the Leader re-checked them. Oracle F1: R11 and R51 lacked the word "stairs", and R62 said "floor's band" where it meant the monster pool; fixed to "floor pool" and "stairs".

- [DONE] T2 Engine: search-on-clear, stairs, wandering checks, progressive chests, gates
  _Files:_ index.html (engine script)
  _Subplan:_ .playbook/T2.subplan.md
  _Verify:_ node .tmp/run-gates.js (script in the subplan) prints failed: [] and total: 404, and the gate names listed in the subplan are present
  _Blocks:_ T3 starts only after this verify passes
  _Lessons:_ a floor that ends only at its stairs turns every auto-play driver into a stall unless the driver takes the stairs; the smoke driver (gate "smoke: seed 99") now walks to the stairs and calls doStairs. Gate titles "stairs refused" and "stairs placement" are as the doer named them. Contracts that change the terminal condition must list the drivers that depend on it.

- [DONE] T3 UI: stage overlays, stairs control, banner, board marker, legend
  _Files:_ index.html (style, body, UI script)
  _Subplan:_ .playbook/T3.subplan.md
  _Verify:_ node .tmp/run-gates.js still prints failed: [] and total: 404; rg -n 'id="stage"|id="hud"|overlay-info' finds the new markup; rg -n "descendDungeon\(\)" shows no call inside render(); both script blocks pass node --check. No browser run here.
  _Lessons:_ subplan line numbers were stale (UI script starts near line 3808, not 3577); unique old-string anchors worked with no mismatch, so rg line numbers only served as a sanity check. Leader re-ran gates (404/404), rg checks and node parse of both blocks: pass.

## Layer 2 - parallel (disjoint files; Leader writes lessons from their reports)
- [DONE] T4 Player rules: dungeon floors and loot, interface
  _Files:_ rules.md
  _Subplan:_ .playbook/T4.subplan.md
  _Lessons:_ verbatim old strings from the file applied on the first Edit; Leader re-ran the rg checks (stale phrases: none; new terms present; Moldvay gone from Reviewed section).
  _Verify:_ rg -n "scroll inside the panel|fixed to the screen|clearing a floor is not the final victory|opens an adjacent chest" rules.md shows no old wording; rg -n "Moldvay|wandering|stairs" rules.md shows the new bullets

- [DONE] T5 Decision records and source credit
  _Files:_ interpretations.md, inspirations.md
  _Subplan:_ .playbook/T5.subplan.md
  _Lessons:_ two parallel Edits on separate files ran cleanly; the Moldvay deletion from the Reviewed section is confirmed by an awk check that prints nothing.
  _Verify:_ rg -n "2026-11-02" interpretations.md shows the new section; rg -n "Moldvay" inspirations.md shows the new subsection and no line under "Reviewed, with no specific current rule attributed"; rg -n "stairs glyphs" inspirations.md returns one line

- [DONE] T6 Browser assertions for stairs, wanderers, and the no-scroll layout (1280x800: 166/166; 1036x647: 166/166; 390x844: 165/165; see critique R-50)
  _Files:_ .tmp/verify-browser.js
  _Verify:_ served page (http://127.0.0.1:8791/index.html) with .tmp/verify-browser.js evaluated via indirect eval returns failed: [] and total equal to the count written in T6's report. Old descend and fixed-dial assertions are replaced, not deleted.
  _Blocks:_ depends on T3 (needs #stage and #hud)

## Layer 3 - sequential
- [OPEN] T7 End-to-end verification; reconcile current disposition
  _Files:_ .tmp/plan.md, .tmp/critique.md, .tmp/critique-todo.md
  _Verify:_ run-gates.js (404, failed []); verify-browser.js at 1036x647, 1280x800 and 390x844 (failed []); rg for each receipt's Done-when; screenshots at 1280x800 and 390x844 (main dial, skill submenu, search phase with stairs) viewed and their raw evidence quoted in the report; process row for port 8791 stopped

## Oracle review (DEC-03, 2026-11-03)
Verdict "fix first". Findings F1 to F8 were checked against the files. All accepted; the corrections are in the subplans and plan.md (see critique.md receipts). F1: T1 header fixed. F2: T3 verify is structural and gate-based; the browser moves to T6/T7. F3: T2 verify is a command with expected total 404 and gate names. F4: arrival counter is global; no free tile means no spawn. F5: morale is judged per band. F6: chest rolls are N independent rolls summed. F7: stairs placed after elevation writes, excluded from P/E/doors/furn/traps. F8: stairs accept any living party member on them; campaign floors 1-2 say "level" ("Take stairs to level N+1 of 3").
