# Layout requirements

Requirement type: layout. This file is the governing spec for how the game view is arranged on screen. The header contract in `index.html` points here (R53); rules about what the controls do live in `rules.md`.

Status: CURRENT, 2026-11-03. Basis: operator messages of 2026-11-03 (split row below the map, log to the right, extra actions beside the radial, the game always fits, no scrollbars).

Scope: the game view (map, turn status, unit statistics, actions, log, legend, credits, map selector and buttons). The campaign town screen is outside the no-scroll rule (LAY-9).

## Fit

- **LAY-1 Always fits.** The game view SHALL fit the window with no scrollbar at every viewport size. Reference sizes that must pass: 1280x800 (desktop), 1036x647 (short laptop), 390x844 (phone).
- **LAY-2 No internal scrolling.** No map, panel, log or action list SHALL show a scrollbar. Content that would overflow is clipped, not scrolled. The log shows its newest entries first. On phones the log is a short strip, so only its newest lines are visible; the full log is not reachable on a phone.

## Desktop arrangement (window wider than 640px)

- **LAY-3 Column order.** The map sits at the top of the left column. Turn status sits directly below the map. Below turn status is a row: unit statistics on the left, the action radial on the right. The game log is a column to the right of the left column, full height.
- **LAY-4 Extra actions beside the radial.** Actions beyond the six radial slots (Stop moving, Loot, submenu items, Back and the like) SHALL sit to the right of the radial, never below it.
- **LAY-5 Legend and credits.** The legend and credits sit under the game log in the right column.
- **LAY-6 Controls.** The map selector and the buttons sit in a fixed row below the game view.

## Phone arrangement (window 640px wide or narrower)

- **LAY-7 Single column.** Map, turn status, unit statistics, actions, log, then controls, in that order, one column at full width.
- **LAY-8 Phone reductions.** The legend and credits are hidden on phones. The log is a short strip. The radial scales to 60%, keeping touch targets at least 44px.

## Fixed heights and fitting

- **LAY-9 Fixed panel heights.** Turn status, unit statistics and actions keep the same height across unit selection, menus, move previews and phases. Only the map area changes size, and it does so only with the window.
- **LAY-10 Map scale.** The hex size SHALL be the largest that shows the whole map inside the map area, clamped to 10 to 22 px. On phones (window 640px wide or narrower) the lower bound is 9 px: the phone map area cannot show the full text of the turn status, stats and actions at 10 px, and this trade is taken deliberately. Resizing the window re-fits the map.
- **LAY-11 Radial scale.** The radial SHALL scale to the actions panel height, between 50% and 80%.
- **LAY-12 Stairs on screen.** Because the whole map is visible (LAY-10), the stairs are always on screen. The map does not scroll to the stairs.

## Campaign town

- **LAY-13 Town exception.** While the campaign town screen is shown, the game view is hidden. The town screen MAY scroll inside itself.

## How this is checked

- Browser at each reference size: the document and every game panel have no vertical or horizontal overflow (scroll height not greater than client height).
- The map's full rectangle lies inside the map area at each size.
- Panel heights for turn status, unit statistics and actions are the same after selecting a second unit, opening a submenu, previewing a move, and in search phase.
- Desktop: the log is right of the map column, and extra actions are right of the radial.
- Phone: one column in the order of LAY-7.
