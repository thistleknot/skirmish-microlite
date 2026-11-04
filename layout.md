# Layout requirements

Requirement type: layout. This file is the governing spec for how the game view is arranged on screen. The header contract in `index.html` points here (R53); rules about what the controls do live in `rules.md`.

Status: CURRENT, 2026-11-03. Basis: operator messages of 2026-11-03. The operator set two hard rules and said everything else may move, in widescreen or portrait.

Scope: the game view (map, turn status, unit statistics, action radial, log, legend, credits, map selector and buttons). The campaign town screen is outside the no-scroll rule (LAY-9).

## Hard rules

- **LAY-1 Map above unit and radial.** The map sits in one area. Directly below it, in a similar-sized area, unit statistics sit on the left and the action radial on the right. This holds in every orientation.
- **LAY-2 Always fits, no scrolling.** The game view SHALL fit the window with no scrollbar and no clipped map at every viewport size. Panels that cannot show all their text clip it; they never scroll. Reference sizes: 1280x800 (desktop), 1036x647 (short laptop), 390x844 (phone).

## Everything else is movable

Turn status, the log, legend, credits, the map selector and the buttons may sit anywhere the hard rules allow: beside the map, below the unit row, or in a column. The arrangement may differ between widescreen and portrait.

## Current arrangement

- **Widescreen desktop (wider than 640px and taller than 500px):** map, turn status and the unit/radial row in the left column; log, legend and credits in the right column; buttons below.
- **Portrait phone (640px wide or narrower):** map, then unit and radial side by side, then turn status, then the log strip, then buttons.
- **Short landscape (wider than 640px and 500px or shorter):** map and the unit/radial row in the left column; turn status and the log in the right column. Legend and credits are hidden. The map and row need a viewport about 400px tall to fit the 9px hex floor (LAY-3). Below that the map clips.

## Sizing

- **LAY-3 Map scale.** The hex size SHALL be the largest that shows the whole map inside the map area, clamped to 10 to 22 px. On phones (window 640px wide or narrower) or windows 500px tall or shorter, the lower bound is 9 px, a deliberate trade for fit. Resizing the window re-fits the map.
- **LAY-4 Radial scale.** The radial SHALL scale to its panel height, between 50% and 80%. At the 50% floor the radial is about 125px tall; a shorter panel clips its outer slots.
- **LAY-5 Fixed panel heights.** Turn status, unit statistics and actions keep the same height across unit selection, menus, move previews and phases. Only the map area changes size, and it does so only with the window.
- **LAY-6 Stairs on screen.** Because the whole map is visible, the stairs are always on screen. The map does not scroll to the stairs.

## Campaign town

- **LAY-7 Town exception.** While the campaign town screen is shown, the game view is hidden. The town screen MAY scroll inside itself.

## How this is checked

- Browser at each reference size: the document and every game panel have no vertical or horizontal overflow (scroll height not greater than client height).
- The map's full rectangle lies inside the map area at each size.
- The unit and radial areas sit directly below the map, unit left, radial right.
- Panel heights for turn status, unit statistics and actions are the same after selecting a second unit, opening a submenu, previewing a move, and in search phase.
