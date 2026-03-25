# MASC New Feedback Sort - 2026-03-23

## Rules Used
- Source scope: only the `NEW EDITS`, `NEW NOTE`, and `NOT FIXED` items pasted in Aaron's message on `2026-03-23`.
- Classification rule:
  - `Content-related` = copy, titles, naming, ordering, imagery, asset swaps, video metadata, or approval questions.
  - `Dev-related` = links, styling, spacing, layout, template behavior, calculators, dynamic data, XML-fed values, search, filters, print styles, and front-end logic.
- Planning rule:
  - dev work is split into small execution blocks of about `4h` to `5h`
  - the batches below are meant to be sprintable work blocks, not final release commitments
  - where a change needs both content approval and engineering work, it appears under content first and is referenced again in the matching dev sprint

## Content-Related Changes

### MASC-C01 Home / overview copy and imagery
- Home: replace the `Support for the Next Generation` copy with the supplied two-line version.
- Home: swap the `Support for the Next Generation` image to a young farming family.
- Lending Overview: restore the hero copy and revert the page hero label from `Borrowing with MASC` back to `Lending`.
- Lending Overview: rename `Stocker Loans` to `Livestock Loans` in content and navigation language.
- Lending Overview: update the `Borrowing with MASC` section copy and the `Lending Rates` toolbox copy.
- Young Farmer Supports Overview: decide whether `Young Farmer Lending Fee Credit` should land on the full fee-credit page instead of only the video.
- Young Farmer / lending pages: replace bridging-generations imagery with approved young farmer photography.

### MASC-C02 Lending detail content and page-shape decisions
- `Stocker Loans` / `Livestock Loans`: large-format page change to match the `Loan Guarantees` layout and new copy deck.
- `Borrowing with MASC`: rebuild as its own page rather than mirroring `Lending Overview`.
- `How to Apply for a Loan`: use the updated document list, copy edits, and removal notes.
- `Young Farmer Rebate` / `Loan Maximum`: apply approved wording and dollar-format changes.
- `Support for New Farmers`: confirm the rename from `Support for The Next Generation`.

### MASC-C02A Later Sync Flag - backend-driven lending values
- Flag for later sync: the following items should not be treated as simple copy cleanup because they are coming from the backend dataset and may require conditional rendering or formatter logic:
  - `Loan Maximum` comma formatting such as `$5,750,000`
  - `View Lending Rates` linkage where the rendered CTA is tied to dataset-driven output
  - `Young Farmer Rebate` value formatting such as `$400,000`
  - wording normalization like `two per cent` and `five years of the loan` when the rendered content is sourced from structured data
- Working implementation read:
  - likely needs formatter or transform logic in the rendering layer rather than static text edits
  - may need per-field rules so the same source data is not changed incorrectly in other templates
  - should be reviewed in sync before being folded into a sprint estimate

### MASC-C03 Insurance and factsheet content / data approvals
- Confirm `16 Risk Areas` language where older references still show `15`.
- Confirm XML-driven insurance values for `50/70/80/90` coverage references.
- Confirm weekend-flex rules for dates like `March 31`, `June 20`, and `June 22`.
- Confirm scenario-table corrections where the current values appear wrong or still show `N/A`.
- Confirm `2026` data refresh where tables or eligible-variety lists still appear to be on `2025`.
- Confirm `Other Insurance Programs` order changes.
- Confirm `Katie/Jeff` review items where the built page and copy deck diverge.

### MASC-C04 Claims, reporting, and image-swap content dependencies
- Provide replacement Manitoba field photo for `How to File a Claim`.
- Provide alternate photo for `LPI` section to replace the current cow image.
- Provide alternate photo for `Stocker / Livestock Loans` where the calves image should change.
- Confirm wording edits like `seven days to appeal`, `Updated May`, and other sentence-level copy changes.
- Confirm whether the collapsible / expandable claims-box behavior is desired product direction, not just a nice-to-have.

### MASC-C05 Corporate, news, reports, and policy copy changes
- News: replace all instances of `Alex Papineau` with `Michael Street`.
- News meeting flag: confirm whether the `Category` control should be deleted entirely and the search bar alone is enough for filtering.
- Governance: update `Leah Strong`, executive-management order, and org-chart placement notes.
- Reports and Publications: confirm the new `Category` filter options and naming convention for annual reports.
- Policies: confirm wording changes, per-cent style, and 2024 salary disclosure target.
- About MASC: apply approved wording updates and sentence cleanup.

### MASC-C06 Knowledge Centre, factsheets index, videos, icons, and new-page content
- Knowledge Centre: provide missing title and description for the `High Variance` video.
- Knowledge Centre: confirm renamed video title and description for `Handling Variances on a Harvested Production Report`.
- Knowledge Centre meeting flag: colour-coding applied filters to match content-piece treatments, `Program = green`, `Category = yellow`, `Media = grey`, is dev-feasible but not part of the current approved design and should be discussed before scheduling.
- Factsheets index: confirm the source-of-truth document for `Program` and `Category` filters.
- Factsheets index: confirm alphabetical ordering requirement and missing direct/livestock loan factsheets.
- Factsheets index: the requested move from a single current filter to `Program` + `Category` filters should be treated as significant tagging and categorization work, not just a front-end control swap.
- LPI: create or supply a new icon because sheep are not covered.
- `Insurance Contracts`: provide the content source from the current MASC site for the new page build.
- `Support for Young Farmers` icon/link text: confirm rename to `Support for Next Generation`.

## Dev-Related Sprint Plan

### MASC-D01 Home page, footer, and global link-target cleanup `[4.5h]`
- Fix the `Seeding Deadlines` homepage link.
- Normalize internal-link behavior so internal routes open in the same tab unless intentionally external.
- Fix the homepage search bar input issue.
- Fix the misleading homepage calculator flow where users enter data twice.
- Make footer `News` styling match `About` and `Careers`.
- Normalize homepage spacing between `Insurance`, `Lending`, `FSTR`, `Resources`, `Careers`, and `Contact Us`.
- Dependency: `MASC-C01` image and copy decisions.
- Status update on `2026-03-24`: completed.

### MASC-D02 Overview-page remediation pass `[4.5h]`
- `Insurance Overview`: align insurance CTA buttons, fix `Seeding Deadlines` links, fit `View Land Parcel Info` on one line, correct the `Rates and Coverage` link target, and fix `Seedling` -> `Seeding`.
- `Young Farmer Supports Overview`: fix the video link, align the `Borrowing with MASC Video` header with the video, fix the `Seeding Deadlines` resource link, and apply the approved fee-credit destination.
- Dependency: `MASC-C01` and `MASC-C02`.
- Status update on `2026-03-24`: completed.

### MASC-D03 Lending landing pages and IA cleanup `[5h]`
- `Lending Overview`: restore the approved hero copy and structure, rename `Stocker Loans` -> `Livestock Loans`, update the main nav label, keep `Lending Rates` in the same tab, and align the two footer CTA rows visually.
- Separate `Borrowing with MASC` from `Lending Overview`.
- Apply approved image swaps on the lending landing pages once available.
- Dependency: `MASC-C01` and `MASC-C02`.
- Status note on `2026-03-25`: this batch now needs a quick sync on the `Lending Overview` point before implementation continues.

### MASC-D04 Global factsheet template pass `[5h]`
- Systemically fix repeated factsheet issues where possible:
  - bullet alignment and bullet removal patterns
  - breadcrumb / header spacing
  - contact-link banner behavior
  - common title ordering and section spacing
  - recurring `myMASC` / quick-link label cleanup
- Use this pass to reduce page-by-page duplication before deeper factsheet cleanup.

### MASC-D05 Print stylesheet global pass `[5h]`
- High-priority QA fix: make white text readable on print.
- High-priority QA fix: remove table cell shading for printer-friendliness, keeping only light grey header-cell styling and leaving the rest of the table white.
- Reformat formula tables to better match the web layout.
- Fix secondary page title order and print-title sizing.
- Normalize print header / footer spacing and section spacing.
- Reduce bullet size / spacing and apply the main-bullet vs sub-bullet rules consistently.
- Stop buttons or inappropriate interactive elements from leaking into print.
- Priority note: the white-text and table-shading print issues should be treated as print breakage to complete as soon as possible, not optional print polish.

### MASC-D06 Insurance dynamic-data and deadline logic `[5h]`
- `AgriInsurance`: fix `Seeding Deadlines` link, `16 Risk Areas`, XML-driven `50/70/80/90` values, and weekend-flex date logic.
- `Corn Insurance`: fix the seeding-table text and map-link behavior, remove the extra bullets, and apply the requested bolding.
- `Crop Coverage Plus`: fix scenario values, remove `N/A` in indemnity columns, and clean up the asterisk handling.
- This sprint is the main data-logic pass rather than just page copy cleanup.

### MASC-D07 Insurance factsheets set A `[4.5h]`
- Fix the remaining structural issues on:
  - `Contract Price Option`
  - `Excess Moisture Insurance`
  - `Forage Seed Insurance`
  - `Grain Contaminated with Faeces`
  - `Individual Coverage`
  - `Individual Productivity Index`
- Main work types: bullet structure, bold treatment, section order, table cleanup, and layout fixes.
- Dependency: `MASC-C03` where data confirmation is needed.

### MASC-D08 Insurance factsheets set B `[4.5h]`
- Fix the remaining structural issues on:
  - `Novel Crops Insurance`
  - `Organic Insurance`
  - `Pedigreed Seed Crops`
  - `Polycrop Establishment Insurance`
  - `Potato Insurance`
  - `Reseed and Stage 1 Claim Information`
  - `Winter Wheat`
- Main work types: remove incorrect bullets, clean up tables, align bold treatment, fix section order, and apply current-year values where approved.

### MASC-D09 Hail and Forage program pass `[4.5h]`
- `Hail Insurance`: remove redundant hyperlink treatment, style the `Calculate Premium` button in MASC green, and apply weekend-flex date logic to `March 31` titlebars.
- `Continuous Hail Insurance Option` and related hail factsheets: tighten print bullet spacing and remove extra punctuation.
- `Forage Insurance`: direct-link the calculator, add visual grouping boundaries, fix photo crop/orientation, and align related-program buttons.
- `Forage Advantage` / `Forage Restoration` and related forage pages: apply the requested bolding, title order, and print fixes.

### MASC-D10 Claims, reporting, rates, and MMPP pass `[5h]`
- `How to File a Claim`: add visual boundaries, fix box titles, remove numbering where requested, implement the accordion / expand-collapse pattern if approved, swap the hero image, and fix wording changes.
- `How to File a Report`: add visual breaks between reporting sections and fix the broken PDF links / Quick Links items.
- `Risk Areas`: fix `15` -> `16`, correct the `Rates & Coverages` quick link, add collapse behavior for previous-year data if kept, clean up thematic crop map description rendering, and remove repeated content-box text.
- `MMPP` / related pages: fix links, PDF hookups, table presentation, and related reporting-page issues that were explicitly flagged.
- Dependency: `MASC-C04` for imagery and any product-direction call on accordion behavior.

### MASC-D11 Lending detail pages, tools, calculators, FSTR, and myMASC `[4.5h]`
- `Loan Maximum`, `Lending Rates`, `Young Farmer Rebate`, and related lending pages: apply link targets, commas, phrasing, and rate CTA fixes.
- `How to Apply for a Loan`: fix documentation links, remove obsolete content blocks, move the video-aligned copy up, and remove the wrong button.
- `FSTR`: fix the broken calculator, fix the Manitoba tax link, and apply the page-header line-break change.
- `Your myMASC`: update tab title rendering, preamble copy, online-services wording, direct deposit text, and image crop.
- `Your myMASC`: remove the literal asterisks from the browser tab title so it renders as `Your myMASC`, not `Your **my**MASC`.
- `Calculators` / `Tools`: fix broken links, add the lending forms/resources links, and apply the calculator-priority / prominence adjustments that are implementable without new product decisions.
- Sync note: if the `Loan Maximum` / `Young Farmer Rebate` values are confirmed to be backend-dataset-driven, move that subset into its own logic task instead of forcing it into this sprint as simple page cleanup.

### MASC-D12 News, corporate, Knowledge Centre, factsheets index, and global backlog `[4.5h]`
- `News`: remove items without photos if they are bad imports, fix duplicated breadcrumbs, keep individual news items in the same tab, and swap the content-owner name where required.
- `News`: only remove the `Category` control if the meeting decision confirms that the search bar alone is sufficient for filtering.
- `About MASC`, `Corporate Governance`, `Reports and Publications`, and `Policies`: fix the broken quick links, content-order rendering, report naming, filter labels, and broken document targets.
- `Knowledge Centre`: fix pagination count mismatch, rename `Media` -> `Content Type`, apply italic `myMASC` handling in filters, clean up the red play-button boundary, and wire the updated video metadata.
- `Knowledge Centre`: do not assume applied-filter colour coding is in scope; discuss first because it is implementable dev work but not represented in the current design direction.
- `Factsheets` index: fix XML description scraping, alphabetical ordering, missing factsheets, and the `Program` + `Category` filters.
- `Factsheets` index: treat the `Program` + `Category` filter change as a taxonomy/data task that may require content tagging, source-data normalization, and primary-vs-secondary categorization logic before the UI can be considered complete.
- Global backlog: new `Insurance Contracts` page, LPI icon swap, `Support for Next Generation` icon/text update, and any remaining contact-link fixes on knowledge pages.

## Suggested Order
1. `MASC-D01`
2. `MASC-D02`
3. `MASC-D03`
4. `MASC-D04`
5. `MASC-D05`
6. `MASC-D06`
7. `MASC-D07`
8. `MASC-D08`
9. `MASC-D09`
10. `MASC-D10`
11. `MASC-D11`
12. `MASC-D12`

## Planning Notes
- This file is a sort-and-batch document, not a replacement for the active board.
- `MASC-02`, `MASC-03`, and `MASC-04` already overlap some of this work, especially search, homepage cleanup, and the news block.
- `MASC-D01` is now complete, but the main board estimate is being left conservative until the overlap with the still-open `MASC-02` cleanup bundle is reconciled.
- If repeated factsheet issues can be solved through shared template and print-style fixes, the later page-specific sprints should compress materially.
- If content assets, copy decks, or approvals lag, `MASC-C01` to `MASC-C06` become the main blockers to sprint flow.
- The `Program` + `Category` factsheet filter request is likely understated if the current content is not already tagged cleanly; treat it as data-structure and categorization work first, UI work second.
