---
title: "MASC-17B Print tables and controls bundle"
---

## Purpose
- Handle the print-table and print-control fixes from the processed MASC intake.

## Scope
- This bundle covers table formatting, table shading, print-hidden controls, and column-width issues.
- Target size: `5h`

## Checklist
- [ ] Format print-sheet tables more like the webpage so they take up less space.
- [ ] Remove shading from print-sheet tables.
- [ ] Remove table cell shading globally for printer-friendliness, keeping only light-grey header cells.
- [ ] Format formula tables more like the webpage, including pages like `Pasture Days Insurance`.
- [ ] Hide the `How to File a Report` button from the printed version of the factsheet.
- [ ] Adjust `Seeding Deadlines` column widths.

## Dependencies
- No explicit external blocker.
- If webpage-like table formatting requires large print-template restructuring, split that follow-up out.

## Definition of Done
- Print tables are visually lighter and more compact.
- Shading is removed except for approved header cells.
- Print-only controls do not leak into the output.
- The Seeding Deadlines table is readable without layout breakage.

## Related Links
- [[masc/masc-board|MASC Board]]
- [[masc/MASC Bundle Creation Definitions|MASC Bundle Creation Definitions]]
- [[masc/MASC-17A Print typography and spacing bundle|MASC-17A Print typography and spacing bundle]]
