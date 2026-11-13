# OLI Torus – Accessible Filter Redesign (slider version)

Interactive prototype of a redesigned filter system for the OLI Torus instructor dashboard:

- `index.html` — Overview → Students (Progress, Proficiency)
- `scored-pages.html` — Insights → Scored Pages (Student Progress, Avg Score, Total Attempts), with pagination

The top nav links the two pages. Scored Pages uses illustrative sample data.

The original per-filter dropdowns are replaced with a single **Advanced Search** dialog (Progress `≤ = ≥` + percentage slider, Proficiency checkboxes), with applied filters shown as removable chips.

## Keyboard & WCAG 2.2 AA
- Dialog: `role="dialog"`, `aria-modal`, focus moves in on open, Tab is contained, `Esc` closes, focus returns to the trigger; background is `inert`.
- Comparison (`≤ = ≥`) is a native radio group (arrow keys).
- Percentages use a native `<input type="range">` slider: snaps to 10% intervals matching the tick marks; ←/→ (or ↑/↓) and Page Up/Down move ±10, Home/End for 0/100; `aria-valuetext` announces "30%"; the value bubble is always visible (no hover-only content).
- Pointer users can click anywhere on the track instead of dragging (WCAG 2.5.7 Dragging Movements); the thumb is 26px (2.5.8 Target Size).
- Chip remove buttons have descriptive names; focus moves to the next chip after removal.
- Result counts are announced through a polite live region.
- Visible focus rings everywhere; control borders meet 3:1 non-text contrast; targets are at least 24×24px.

## Run
Open `index.html` (or `scored-pages.html`) in a browser — no build step.
