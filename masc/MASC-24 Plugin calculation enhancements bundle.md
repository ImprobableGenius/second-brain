---
title: "MASC-24 Plugin calculation enhancements bundle"
---

## Purpose
- Add the plugin-side calculation features needed to finish the remaining scripting-audit rows that cannot be completed by content or theme changes alone.

## Scope
- This bundle covers the shared plugin enhancements identified during `MASC-23`.
- Target size: `5h`
- Trigger rows: `79`, `86`, `87`

## Checklist
- [ ] Add support for four-variable calculations in the plugin calculation flow.
- [ ] Add support for rounding calculation results before they are reused in later calculations.
- [ ] Validate row `79` (`Pasture Days Insurance`) against the new plugin behavior.
- [ ] Validate row `86` (`Overwinter Bee Mortality Insurance`) against the new plugin behavior.
- [ ] Validate row `87` (`Strawberry Establishment`) against the new plugin behavior.
- [ ] Confirm English and French output remain aligned after the calculation changes.

## Discussion
- [ ] Confirm whether the new calculation support should be implemented as a narrow fix for these rows only, or generalized for future scripting-audit rows.

## Dependencies
- Access to the current MASC plugin codepath handling calculated values.
- Audit outcomes from `MASC-23`.
- Enough representative data to verify the rounded and four-variable paths on all three rows.

## Definition of Done
- The plugin supports four-variable calculations where needed.
- The plugin can round intermediate results before further calculations.
- Rows `79`, `86`, and `87` no longer require manual script-workaround notes to explain their output.

## Related Links
- [[masc/masc-board|MASC Board]]
- [[masc/MASC-23 Scripting audit review bundle|MASC-23 Scripting audit review bundle]]
- [[masc/MASC-19 Calculator defects and feedback bundle|MASC-19 Calculator defects and feedback bundle]]
