---
title: "MASC-20A News archive remediation bundle"
---

- Last updated: `2026-04-09`
- Status: Complete
- Completed: `2026-04-09`

## Purpose
- Handle the News archive and News item cleanup items from intake.

## Scope
- This bundle covers the current News archive and News item behavior.
- Target size: `5h`

## Checklist
- [x] Delete News items without a photo if they are old XML items or erroneous duplicates.
- [x] Fix duplicated `News > News` breadcrumbs on News items.
- [x] Stop individual News items from opening in a new tab.
- [x] Confirm whether `Category` should be removed because the Search News bar is enough.
- [x] Confirm whether to add a `Category` filter with `Strategic Plan` and `Annual Reports`.
- [x] Change the `View Annual Report` button on the strategic plan item to `View Strategic Plan`.

## Discussion
- [x] Decide whether the News experience should simplify around search-only filtering or expand into a richer category model.

## Dependencies
- Category behavior needs a product or UX decision before the final remediation path is locked.

## Branch Reconciliation Note
- `0b60573` removes category filtering from the News section.
- `b533bc6` removes the repeated category breadcrumb layer from post breadcrumbs, which addresses the `News > News` duplication path.
- `7cef678`, `de2760c`, and `5e3e29a` add the Reports and Publications category model and the `View Strategic Plan` button treatment.

## Completion Note
- `MASC-20A` was marked complete on `2026-04-09`.
- Remaining umbrella scope for `MASC-20` now sits only in [[masc/MASC-20B Knowledge Centre and video filter bundle|MASC-20B]].

## Definition of Done
- News archive duplicates and behavior issues are resolved.
- The category direction is either implemented or clearly decided and documented.

## Related Links
- [[masc/masc-board|MASC Board]]
- [[masc/MASC Bundle Creation Definitions|MASC Bundle Creation Definitions]]
- [[masc/masc-discussion-points|MASC Discussion Points]]
