---
title: "MASC-23 Scripting audit review bundle"
---

## Purpose
- Review the scripting-dependent pages from the `Scripting Audit` tab in `MASC Content Tracker.xlsx` that are explicitly assigned to Aarish.
- Confirm which pages rely on calculated script behavior, which still contain hard-coded logic, and which need a follow-up implementation decision.

## Scope
- This bundle is limited to the Aarish-assigned rows from the workbook tab `Scripting Audit`.
- Target size: `5h`
- Workbook source: `/Users/aarongilani/Downloads/MASC Content Tracker.xlsx`
- Sheet: `Scripting Audit`

## Checklist
- [x] Row `51` - `Contract Price Option`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`
- [x] Row `59` - `Individual Coverage`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`
- [x] Row `60` - `Individual Productivity Index`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`
- [x] Row `67` - `Winter Wheat`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`
- [x] Row `69` - `Hail Claim Frequently Asked Questions`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`
- [x] Row `70` - `Hail Insurance Short Date Cancellation`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`
- [x] Row `75` - `Forage Restoration (Forage Insurance and Forage Seed Insurance)`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Capture the missing script note because the workbook row has no detail
- [x] Row `76` - `Greenfeed Insurance`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Capture the missing script note because the workbook row has no detail
- [x] Row `77` - `Harvest Flood Option`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the workbook note: `hard coded in calculated script`
- [x] Row `78` - `Hay Disaster Benefit`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the workbook note: `hard coded in calculated script`
- [x] Row `79` - `Pasture Days Insurance`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the workbook note: `hard coded in calculated script and calculated in script`
- [x] Row `81` - `Select Hay Insurance`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`
- [x] Row `83` - `Wildlife Damage Compensation for Livestock Predation`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`
- [x] Row `86` - `Overwinter Bee Mortality Insurance`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`
- [x] Row `87` - `Strawberry Establishment`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the page still matches the workbook note: `Calculated in script`

## Audit Outcomes - 2026-04-10
- Row `51`: page review suggests the current page does not expose the expected script behavior directly, so the workbook note and page reality should be reconciled before implementation assumptions are made.
- Row `59`: completed on `2026-04-13`; the row is now accounted for in the audit and no longer needs separate follow-up inside this bundle.
- Row `60`: completed on `2026-04-13`; the row is now accounted for in the audit and no longer needs separate follow-up inside this bundle.
- Row `67`: reviewed; missing script support appears to have been identified and the page now reads as calculated on both sides.
- Row `69`: reviewed; this looks more like a non-calculator redirect/FAQ behavior than a meaningful scripted calculation page.
- Row `70`: reviewed; calculation handling needs to be treated carefully because the current behavior does not read as a simple workbook-to-page match.
- Row `75`: reviewed; workbook note was blank, so the script-definition gap was captured during the audit.
- Row `76`: completed on `2026-04-13`; the missing script-note gap was captured and the row is now accounted for in the audit pass.
- Row `77`: reviewed; only part of the behavior appears script-driven, so the current implementation still needs follow-up from the hard-coded side.
- Row `78`: reviewed; missing calculated-script shortcodes were identified during the audit.
- Row `79`: audited on `2026-04-13`; implementation requires plugin support for four-variable calculations and rounding before chained calculations.
- Row `81`: reviewed; missing calculated-script shortcodes were identified during the audit.
- Row `83`: reviewed; missing calculated-script support was identified against the workbook expectation.
- Row `86`: audited; implementation depends on plugin support for rounding before further calculations.
- Row `87`: audited; implementation depends on the same plugin calculation enhancements identified for rows `79` and `86`.

## Discussion
- [x] Confirm whether the output of this bundle is audit-only, or whether the hard-coded rows should immediately roll into implementation work.
- [x] Confirm whether rows `75` and `76` should be treated as missing script-definition gaps because the notes column is blank.
- [x] Confirm whether row `79` should now be treated as the remaining implementation-side gap, since the marked audit notes point to missing script/path support rather than unresolved page review.

## Implementation Follow-on - 2026-04-13
- Rows `79`, `86`, and `87` now point to the same plugin enhancement need.
- Required plugin features:
  - support for four-variable calculations
  - support for rounding calculations before they are reused in later calculations
- This follow-on work is now split into `MASC-24` so the audit can be treated as complete and the implementation can be tracked separately.

## Dependencies
- Access to the current MASC theme branch and the live/staging pages for each listed insurance product.
- Access to the workbook source for row-level cross-checking.
- Possible dependency on XML or script-source data if any of the reviewed pages are not purely front-end calculations.

## Definition of Done
- Every Aarish-assigned row from the `Scripting Audit` tab is accounted for.
- Each row has an audit outcome: correct, hard-coded, missing definition, or needs implementation.
- The bundle is ready to hand off into implementation or follow-up questions without re-reading the spreadsheet.

## Completion Note - 2026-04-13
- `MASC-23` is complete as an audit bundle.
- The remaining implementation need has been separated into `MASC-24`.

## Related Links
- [[masc/masc-board|MASC Board]]
- [[masc/MASC Bundle Creation Definitions|MASC Bundle Creation Definitions]]
- [[masc/MASC-19 Calculator defects and feedback bundle|MASC-19 Calculator defects and feedback bundle]]
