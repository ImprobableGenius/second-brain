---
title: "MASC-20A News archive remediation bundle"
---

## Purpose
- Handle the News archive and News item cleanup items from intake.

## Scope
- This bundle covers the current News archive and News item behavior.
- Target size: `5h`

## Checklist
- [ ] Delete News items without a photo if they are old XML items or erroneous duplicates.
- [ ] Fix duplicated `News > News` breadcrumbs on News items.
- [ ] Stop individual News items from opening in a new tab.
- [ ] Confirm whether `Category` should be removed because the Search News bar is enough.
- [ ] Confirm whether to add a `Category` filter with `Strategic Plan` and `Annual Reports`.
- [ ] Change the `View Annual Report` button on the strategic plan item to `View Strategic Plan`.

## Discussion
- [ ] Decide whether the News experience should simplify around search-only filtering or expand into a richer category model.

## Dependencies
- Category behavior needs a product or UX decision before the final remediation path is locked.

## Definition of Done
- News archive duplicates and behavior issues are resolved.
- The category direction is either implemented or clearly decided and documented.

## Related Links
- [[masc/masc-board|MASC Board]]
- [[masc/MASC Bundle Creation Definitions|MASC Bundle Creation Definitions]]
- [[masc/masc-discussion-points|MASC Discussion Points]]
