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
- [ ] Row `76` - `Greenfeed Insurance`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Capture the missing script note because the workbook row has no detail
- [x] Row `77` - `Harvest Flood Option`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the workbook note: `hard coded in calculated script`
- [x] Row `78` - `Hay Disaster Benefit`
  - [x] Review the current English script behavior
  - [x] Review the current French script behavior
  - [x] Confirm the workbook note: `hard coded in calculated script`
- [ ] Row `79` - `Pasture Days Insurance`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the workbook note: `hard coded in calculated script and calculated in script`
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
- Row `59`: reviewed and flagged for follow-up because the script path or implementation context still needs more information.
- Row `60`: reviewed and flagged for follow-up because the behavior appears code-driven, but the implementation path still needs clarification.
- Row `67`: reviewed; missing script support appears to have been identified and the page now reads as calculated on both sides.
- Row `69`: reviewed; this looks more like a non-calculator redirect/FAQ behavior than a meaningful scripted calculation page.
- Row `70`: reviewed; calculation handling needs to be treated carefully because the current behavior does not read as a simple workbook-to-page match.
- Row `75`: reviewed; workbook note was blank, so the script-definition gap was captured during the audit.
- Row `77`: reviewed; only part of the behavior appears script-driven, so the current implementation still needs follow-up from the hard-coded side.
- Row `78`: reviewed; missing calculated-script shortcodes were identified during the audit.
- Row `79`: still open; the note indicates support for multiple path variables is needed before the audit can be treated as complete.
- Row `81`: reviewed; missing calculated-script shortcodes were identified during the audit.
- Row `83`: reviewed; missing calculated-script support was identified against the workbook expectation.
- Row `86`: reviewed; the current behavior likely needs rounding or value-format follow-up rather than a pure content correction.
- Row `87`: reviewed and accounted for in the audit pass.

## Discussion
- [ ] Confirm whether the output of this bundle is audit-only, or whether the hard-coded rows should immediately roll into implementation work.
- [ ] Confirm whether rows `75` and `76` should be treated as missing script-definition gaps because the notes column is blank.
- [ ] Confirm whether rows `76` and `79` should now be treated as the remaining implementation-side gaps, since the marked audit notes point to missing script/path support rather than unresolved page review.

## Dependencies
- Access to the current MASC theme branch and the live/staging pages for each listed insurance product.
- Access to the workbook source for row-level cross-checking.
- Possible dependency on XML or script-source data if any of the reviewed pages are not purely front-end calculations.

## Definition of Done
- Every Aarish-assigned row from the `Scripting Audit` tab is accounted for.
- Each row has an audit outcome: correct, hard-coded, missing definition, or needs implementation.
- The bundle is ready to hand off into implementation or follow-up questions without re-reading the spreadsheet.

## Related Links
- [[masc/masc-board|MASC Board]]
- [[masc/MASC Bundle Creation Definitions|MASC Bundle Creation Definitions]]
- [[masc/MASC-19 Calculator defects and feedback bundle|MASC-19 Calculator defects and feedback bundle]]
