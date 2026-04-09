---
title: "MASC-20B Knowledge Centre and video filter bundle"
---

## Purpose
- Handle Knowledge Centre, video-library, and filter cleanup items from intake.

## Scope
- This bundle covers title-only pages, video-list inconsistencies, quick-link issues, and filter-label cleanup.
- Target size: `5h`

## Checklist
- [x] Resolve the title-only page at `https://mascag.wpenginepowered.com/knowledge-centre/explaining-polycrop-establishment-insurance/`.
- [x] Resolve the title-only page at `https://mascag.wpenginepowered.com/knowledge-centre/agristability-and-mymasc/`.
- [ ] Fix cases where `Seeding deadline` in quick links points to `Program Deadlines`.
- [x] Fix the video-pagination issue where Page 2 only has `11` videos instead of `12`.
- [x] Remove the red boundary on the `Report Your Forage Harvest Production` video thumbnail play button.
- [x] Rename the `Media` filter to `Content Type`.
- [x] Apply italics to `my` in `myMASC` inside the Category filter dropdown, selected state, and content filters.
- [ ] Confirm whether applied filters should be colour-coded to match content-piece treatments.

## Discussion
- [x] Decide whether the title-only pages should be unpublished, redirected, or completed with content.
- [ ] Decide whether applied-filter colour coding belongs in the approved design.

## Dependencies
- The title-only pages may need content or redirect decisions rather than a simple dev fix.
- Filter colour coding is design-dependent.

## Branch Reconciliation Note
- `7b5baa9` redirects singular Knowledge Centre items to the archive, which resolves the title-only page path by redirect rather than filling those pages with content.
- `b5a3f62` renames the `Media` filter to `Content Type`.
- `0e8474d` handles the dynamic italicizing of `myMASC` in the filter and related UI output.

## Definition of Done
- Title-only pages have a clear resolution path.
- Quick links and video listing issues are resolved.
- Filter naming and styling decisions are either implemented or explicitly parked.

## Related Links
- [[masc/masc-board|MASC Board]]
- [[masc/MASC Bundle Creation Definitions|MASC Bundle Creation Definitions]]
- [[masc/masc-discussion-points|MASC Discussion Points]]
