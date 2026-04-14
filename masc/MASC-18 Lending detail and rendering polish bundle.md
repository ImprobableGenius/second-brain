---
title: "MASC-18 Lending detail and rendering polish bundle"
---

## Purpose
- Handle the lending-page visual, formatting, and link-polish items that were grouped from intake.

## Scope
- This bundle covers the contained lending-detail cleanup lane.
- Target size: `6h`

## Checklist
- [ ] Reorient the photo so the woman's face is not cut off and the crop focuses on what she is holding or at least shows her eyes.
- [ ] Fix loan maximum formatting so it shows `$5,750,000`.
- [ ] Add a `View Lending Rates` link.
- [ ] Update the Young Farmer Rebate value from `$400000` to `$400,000`.
- [ ] Change Young Farmer Rebate wording from `2 per cent` to `two per cent`.
- [ ] Change `5 years of the loan` to `five years of the loan`.
- [ ] Move the header or paragraph upward so it aligns with the top of the video.
- [ ] Fix the broken table link to the Stocker Loans page.
- [ ] Change `Support for Young Farmers` icon or link text to `Support for Next Generation`.

## Discussion
- [ ] Confirm whether the lending-value formatting items can be handled in the theme rendering layer or require dataset-level changes first.

## Launch Note - 2026-04-13
- `b0a598d` introduced a sitewide currency-formatting module on `main`, which gives this bundle a real theme-layer path for rendering dollar amounts instead of leaving the value-formatting question fully open.
- This should reduce uncertainty around the loan-maximum and Young Farmer Rebate formatting subset, but the launched formatter still needs page-level QA before those checklist items can be treated as fully closed.
- Remaining likely scope is still the link, wording, photo, layout-alignment, and broken-link follow-through.

## Dependencies
- Some items may be backend-dataset-driven.
- Photo direction may need design review if the crop change looks awkward.

## Definition of Done
- The contained lending page fixes render correctly.
- Formatting and wording changes are visible on-page.
- Link and photo issues are resolved or explicitly re-scoped.

## Related Links
- [[masc/masc-board|MASC Board]]
- [[masc/MASC Bundle Creation Definitions|MASC Bundle Creation Definitions]]
- [[masc/masc-board#Later Sync Flag - backend-driven lending values|Backend-driven lending values]]
