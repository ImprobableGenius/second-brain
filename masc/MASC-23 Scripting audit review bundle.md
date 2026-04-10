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
- [ ] Row `51` - `Contract Price Option`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`
- [ ] Row `59` - `Individual Coverage`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`
- [ ] Row `60` - `Individual Productivity Index`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`
- [ ] Row `67` - `Winter Wheat`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`
- [ ] Row `69` - `Hail Claim Frequently Asked Questions`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`
- [ ] Row `70` - `Hail Insurance Short Date Cancellation`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`
- [ ] Row `75` - `Forage Restoration (Forage Insurance and Forage Seed Insurance)`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Capture the missing script note because the workbook row has no detail
- [ ] Row `76` - `Greenfeed Insurance`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Capture the missing script note because the workbook row has no detail
- [ ] Row `77` - `Harvest Flood Option`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the workbook note: `hard coded in calculated script`
- [ ] Row `78` - `Hay Disaster Benefit`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the workbook note: `hard coded in calculated script`
- [ ] Row `79` - `Pasture Days Insurance`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the workbook note: `hard coded in calculated script and calculated in script`
- [ ] Row `81` - `Select Hay Insurance`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`
- [ ] Row `83` - `Wildlife Damage Compensation for Livestock Predation`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`
- [ ] Row `86` - `Overwinter Bee Mortality Insurance`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`
- [ ] Row `87` - `Strawberry Establishment`
  - [ ] Review the current English script behavior
  - [ ] Review the current French script behavior
  - [ ] Confirm the page still matches the workbook note: `Calculated in script`

## Discussion
- [ ] Confirm whether the output of this bundle is audit-only, or whether the hard-coded rows should immediately roll into implementation work.
- [ ] Confirm whether rows `75` and `76` should be treated as missing script-definition gaps because the notes column is blank.

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
