# MASC Project Context

## Project Snapshot
- Source: `Workload Metrics - Main.csv`
- Project type: Local WordPress site with a custom theme
- Local site root: `/Users/aarongilani/Local Sites/masc`
- Theme path: `/Users/aarongilani/Local Sites/masc/app/public/wp-content/themes/masc-wordpress`
- Theme repo: Git repo inside the theme folder
- Current branch: `dev`
- Remote: `git@github.com:Vincent-Design-Inc/masc-wordpress.git`
- Load: Medium
- Working estimate: 75h total for current open tasks
- Task code prefix: `MASC`
- Priority: High
- Start date: 2026-03-16
- Deadline: 2026-03-20
- Status: In Progress

## Current Delivery Tasks
- CSV due date: 2026-03-27
- Current sprint deadline: 2026-03-20
- Tracking override: using Friday, 2026-03-20 for this week's deliverables
- [x] Complete thematic crop map archive page | Completed: 2026-03-17
- [x] Merge thematic crop maps pull request into `main` | Completed: 2026-03-18
- [x] Fix homepage responsiveness | Completed: 2026-03-18
- [x] Create featured maps block for MMPP page | Completed: 2026-03-18
- [x] Merge current MASC work to production site | Completed: 2026-03-19
- Current rollout note on 2026-03-19: the featured thematic crop maps block has been added to the English `MMPP` page and the French-side page; French translations for the block content still need to be supplied by the content team.
- [x] Review EN feedback and capture follow-on scope | Completed: 2026-03-19
- [x] Evaluate dynamic script requirements and next steps | Completed: 2026-03-19
- [x] Update archive page info cards to showcase coin categories for year, crop, and map type | Completed: 2026-03-19
- [x] MASC-01 Missing calculator values | Completed: 2026-03-20
- Delivery note on 2026-03-19: the archive-page category coin pattern update was completed and deployed to production.
- [x] MASC-02 EN feedback cleanup bundle | Completed: 2026-03-24
- Completion note on 2026-03-24: the cleanup bundle is now closed.
- [ ] MASC-03 Search regression handoff | Estimate: 5h | Due: TBD
- Search note on 2026-03-20: raise in the Monday, `2026-03-23` sync that some calculator-driven pages and similar thin-content pages are producing awkward WordPress auto-generated search descriptions because the page body is mostly just the calculator embed or output.
- [ ] MASC-04 News and Updates regression + coin review | Estimate: 4h | Due: TBD
- [x] MASC-05 Responsiveness remediation action plan + Alex sync | Completed: 2026-03-25
- 2026-03-25 completion note: the sync is done, the responsive tasks were broken out, and the remediation lane was handed off to Alex.
- [x] MASC-06 FR logo asset review + update | Completed: 2026-03-23
- [ ] MASC-07 Staging feedback remediation backlog beyond current tracked MASC scope | Estimate: 55h | Due: TBD
- [ ] MASC-08 Circular bin volume calculator widget + Insurance with MASC page update | Estimate: 4h | Due: 2026-03-25
- Execution note on 2026-03-24: pull `MASC-08` into today only if `MASC-02` and `BANF-10` stay contained; otherwise treat it as the next MASC implementation item for Wednesday, `2026-03-25`.
- Blocked note on 2026-03-25: `MASC-08` is now blocked pending design input and client input before implementation can continue.
- [x] MASC-10 Tristin dataset-path response | Completed: 2026-03-25
- Completion note on 2026-03-25: the sort message was sent to Tristin and the dataset-path response is now resolved.
- [ ] MASC-11 Borrowing with MASC calculator block follow-up | Estimate: 2h | Due: 2026-03-25
- Execution note on 2026-03-24: treat `MASC-11` as a separate follow-up from `MASC-08`; this is a second missing calculator-block issue on the `Borrowing with MASC` page and should be handled only if capacity opens after the primary staging lane.
- Blocked note on 2026-03-25: `MASC-11` is now blocked pending design input and client input before implementation can continue.
- [ ] MASC-12 Overview hero program image size increase | Estimate: 2h | Due: TBD
- Estimate assumption: `MASC-12` is a contained hero-image sizing and layout pass on the existing overview-page hero pattern, not a broader hero redesign.
- [ ] MASC-13 Overview nav gradient accessibility fix | Estimate: 3h | Due: TBD
- Estimate assumption: `MASC-13` is a contained fix to restore the dark gradient treatment under the nav on overview landing pages and improve contrast, not a full WCAG audit of the entire page family.
- [x] MASC-14 Plugin missing fields expansion | Completed: 2026-03-25
- Completion note on 2026-03-25: the missing plugin fields were added and the same-day expansion task is now closed.
- [x] MASC-09 Feeder Plus loan maximum rendering review | Completed: 2026-03-24
- Completion note on 2026-03-24: the response relating to `programDetails.xml` and the `FeederPlus` dataset has been completed, so this contained review item is now off the active MASC lane.
- Sprint-batch update on `2026-03-24`: `MASC-D01` is complete and `MASC-D02` is now the next active staging-feedback lane.
- `2026-03-25` progress note: `MASC-D02` is now complete.
- Burn-down note on `2026-03-24`: `MASC-02` is now closed. Keep `MASC-07` conservative until the next planning pass instead of reducing the backlog ad hoc midstream.
- Execution note on 2026-03-20: if time remains after `MASC-02`, use the end of day for light prep on `MASC-05` ahead of the Monday, `2026-03-23` sync.
- Monday note: schedule `MASC-06` first thing on Monday, `2026-03-23`, using the broader French logo asset set Mike shared.
- Triage decision: with the EN feedback review, dynamic script evaluation, archive-page coin update, and calculator missing-values fix all closed, use the remaining time to route or schedule the cleanup bundle and unresolved handoff items.
- Triage sequence:
  - 2026-03-19: complete EN feedback review and capture follow-on scope
  - 2026-03-19: complete dynamic script evaluation and capture next steps
  - 2026-03-19: complete the archive-page info-card update for year, crop, and map type coins and deploy it to production
  - 2026-03-20: complete the promised calculator missing-values fix in a contained 2h block
  - 2026-03-20: route or schedule the remaining cleanup bundle, plugin-owned items, content-owned items, and any follow-on replanning or spillover
- Estimate assumption: thematic crop map archive work is completion/polish on the existing archive template, not a net-new archive system
- Estimate assumption: homepage responsiveness is a breakpoint and CSS/layout pass, not a homepage redesign
- Estimate assumption: featured maps block is a standard reusable content block that surfaces selected thematic crop maps on the MMPP page without introducing a new filtering system
- Delivery assumption: to hold the Friday, 2026-03-20 date, the featured maps block should be treated as a standard hand-picked editorial block rather than a custom query system
- Estimate assumption: the calculator missing-values task is a contained correction pass on known missing values rather than a broader backend remodel or data-model rewrite
- Estimate assumption: MASC-05 is a bounded planning and stakeholder-alignment step, not implementation of additional responsiveness fixes
- Estimate assumption: the `MASC-05` output should include the written remediation plan, Alex sync outcome, owner assignment, and sequencing recommendations
- Estimate assumption: archive-page info-card work reuses existing site coin styling and existing taxonomy fields for year, crop, and map type rather than creating a new metadata system
- Estimate assumption: EN feedback follow-up cleanup covers developer-owned fixes already identified in review, specifically page-header whitespace reduction, table-border cleanup, a targeted program-link update, borrowing-amount formatting cleanup, and a direct `my.masc.mb.ca` sign-in link change rather than plugin-owned or content-owned changes
- Estimate assumption: search regression work covers restoring the global search bar behavior, search results presentation, and search-quality regressions in the current theme stack rather than redesigning search from scratch
- Estimate assumption: News and Updates regression work covers the existing `masc-home-news` block and its category coin treatment rather than a full news-block redesign
- Estimate assumption: `MASC-08` reuses the existing MASC calculator widget pattern and existing circular bin volume calculator functionality, and the work is mainly block placement, page wiring, and visual fit on the Insurance with MASC page rather than a net-new calculator engine
- Estimate risk: add 2h to 4h if responsiveness issues span multiple custom blocks, if production rollout reveals regression fixes, or if the featured maps block needs bespoke query logic or editorial controls beyond standard block fields
- Estimate risk: add 2h to 4h if any of the EN feedback cleanup items turn out to be sitewide template changes, plugin-layer edits, or content-owned updates rather than isolated theme fixes
- Estimate risk: add 2h to 4h if the missing calculator values trace back to a broader payload, schema, or cross-program data issue instead of a contained correction
- Estimate risk: add 2h to 3h if the regression includes deeper query relevance issues in `lib/search-features.php` in addition to the visible search bar and search results UI regressions
- Estimate risk: add 1h to 2h if the design department asks for broader category coin changes that need to be propagated beyond the News and Updates block
- Estimate risk: add 1h to 2h if MASC-05 expands beyond the agreed plan, Alex sync, owner assignment, and sequencing recommendation set into a broader remediation audit
- Estimate risk: add 1h to 2h if `MASC-08` requires net-new widget rendering, custom data hookup, or new calculator-specific styling beyond the existing MASC calculator frame pattern

## Insurance With MASC Calculator Note - 2026-03-24
- New delivery item: the circular bin volume calculator widget is currently missing from the `Insurance with MASC` page and needs to be created or restored and wired into that page.
- Reference page: `https://mascag.wpenginepowered.com/insurance/insurance-coverage/insurance-with-masc/`
- Visual note from review: the missing section currently sits between the `Resources` area and `Quick Links`, where the page still shows a placeholder that the calculators and tools section should be added.
- Current PM assumption:
  - reuse the existing calculator-widget pattern already present elsewhere on the MASC site
  - add the circular bin volume calculator to the page without turning this into a broader calculators redesign
  - prioritize completion today only if the current spillover work closes quickly; otherwise make it the next implementation item tomorrow
- Blocker update on `2026-03-25`:
  - work is paused pending design input and client input
  - treat this as blocked rather than active same-day execution work

## Overview Hero Image Sizing Note - 2026-03-25
- New follow-up item: increase the size of the overview hero program images.
- Current PM assumption:
  - this is a visual adjustment on the existing overview hero pattern
  - scope is limited to image sizing and related layout fit
  - do not treat this as a broader redesign of the overview hero section unless new direction emerges

## Overview Nav Gradient Accessibility Note - 2026-03-25
- New follow-up item: several overview landing pages appear to be missing the dark gradient treatment under the navigation.
- Current risk:
  - this likely weakens contrast and may create a WCAG issue on those pages
  - because the treatment looks like a shared pattern, the fix may belong at the overview hero template level rather than as isolated page edits
- Current PM assumption:
  - start with restoring the missing dark gradient treatment on the affected overview landing pages
  - do not widen this by default into a full accessibility audit unless additional contrast issues are found

## Plugin Missing Fields Note - 2026-03-25
- New same-day delivery item: incoming MASC plugin work is expanding into adding multiple missing fields.
- Current PM assumption:
  - this is a contained plugin schema or field-definition pass on the current WordPress plugin work
  - estimate at `2h` based on the current read that the missing fields are already known and you are actively implementing them
  - if the work turns into field logic, migrations, or broader plugin behavior changes, re-estimate instead of absorbing it silently
- Today's intended sequence:
  - `MASC-14` is now complete
  - then close `MASC-08`
  - then close `MASC-11`
  - then close `IDE-01` if capacity still holds

## Borrowing With MASC Calculator Note - 2026-03-24
- Follow-up item: there is also a missing calculator block on the `Borrowing with MASC` page that did not get completed today.
- Working PM read:
  - treat this as separate from `MASC-08`, because it affects a different page and may not be the same widget
  - keep it as a contained follow-up rather than broadening it into a full calculator-pages sweep
- Planning assumption for `MASC-11`:
  - identify the missing block and restore or wire it correctly on the page
  - complete only if capacity opens after `MASC-D02`, `MASC-D03`, and `BANF-10`
- Estimate note:
  - `2h` assumes the missing block can reuse an existing MASC calculator or block pattern without new component work
- Blocker update on `2026-03-25`:
  - work is paused pending design input and client input
  - treat this as blocked rather than active same-day execution work

## Feeder Plus Loan Maximum Note - 2026-03-24
- Reminder item: review the `Feeder Plus` lending content where `Loans are available up to $5,750,000` is expected to be supplied from `programDetails.xml / lending / program / FeederPlus / FP_loan_maximum`.
- Working issue summary:
  - calculator/details were previously blocked because required details were missing
  - a `[year]` shortcode was proposed as a fallback or rendering aid
  - latest note says the current implementation is turning the value into a date, which needs verification
- Goal for `MASC-09`:
  - confirm whether the field source is correct
  - confirm whether the shortcode choice is wrong for this field
  - decide what the correct rendering path should be before this gets folded into broader lending cleanup

## Tristin Dataset Path Note - 2026-03-24
- New short response item: reply to Tristin on the MASC dataset-path question.
- Source notes to reference:
  - `Imported from allCrops.xml / Basic Hay / varieties / Low Dollar Value`
  - `Supplied by allCrops / crop Wheat / variety Winter Wheat / per_bushel`
- Current issue:
  - these are examples where the available path options are not visible or not obvious in the current tooling path picker
- Goal for `MASC-10`:
  - send a bounded response back to Tristin
  - confirm the intended source paths from the data model
  - note the gap that the path options are not appearing as expected
- Completion update on `2026-03-25`:
  - the response was sent to Tristin
  - the item is now closed as resolved

## Staging Feedback Intake - 2026-03-23
- Source reviewed: `/Users/aarongilani/Downloads/MASC Staging Link Feedback/Main.html`
- Detailed content-vs-dev sort and sprint batching file: `/Users/aarongilani/project-manager/masc/masc-new-feedback-sort-2026-03-23.md`
- Processing rule used: struck-through feedback items were treated as complete and excluded from the new estimate.
- Working parse totals:
  - `106` feedback rows reviewed
  - `344` struck-through items treated as already complete
  - `579` unresolved feedback lines remain
  - `48` rows include explicit `NEW` items
  - `24` rows include explicit `NOT FIXED` or carryover items
- Estimate approach:
  - treat repeated factsheet and template issues as systemic fixes where possible instead of estimating every page as a standalone implementation
  - keep the already-tracked `MASC-02`, `MASC-03`, and `MASC-04` estimates in place and add only the net-new remainder as `MASC-07`
- Working bundle estimate behind `MASC-07`:
  - shared factsheet and template remediation across repeated page patterns: `28h`
  - overview, lending, resource, and general page remediation beyond current tracked scope: `18h`
  - search, calculator, dynamic-data, and date-logic fixes beyond current tracked scope: `16h`
  - final regression, print stylesheet, and QA sweep: `8h`
  - less work already tracked in `MASC-02`, `MASC-03`, and `MASC-04`: `-15h`
  - net new estimate added as `MASC-07`: `55h`
- Main repeated patterns found in the export:
  - factsheet template issues such as missing illustrations, bold-date treatment, missing logos, broken contact links, print styling, breadcrumb spacing, and bullet-list alignment
  - overview and landing-page issues such as hero image or copy mismatches, footer or Quick Links inconsistencies, and incorrect link targets
  - search and calculator issues such as awkward search descriptions, search input problems, calculator double-entry flow, and data-driven value mismatches
  - resource and MMPP issues such as active-year labeling, table presentation, link hookups, and Program and Seeding Deadlines structure
  - factsheets index issues such as filter redesign, taxonomy tagging, missing entries, and categorization cleanup
- Execution update on `2026-03-24`:
  - `MASC-D01` completed
  - `MASC-D02` completed
  - `MASC-02` is now complete, so the active delivery lane is `MASC-D03` first, then `MASC-08`
- `2026-03-25` sync note:
  - `MASC-D03` now needs a quick sync on the `Lending Overview` point before implementation continues
  - queue that discussion for `2026-03-26`
- Immediate next-day plan:
  - move into `MASC-D03`
  - `MASC-10` is now complete
  - `BANF-10` is now complete
  - treat `IDE-01` and `MASC-08` as float items only if capacity opens after the primary lane
- Main estimate assumption:
  - if the repeated factsheet issues must be fixed page by page instead of through shared template or stylesheet changes, add `20h` to `30h`
- Scope note:
  - copy approvals, image swaps, and content-provided assets are still likely dependencies even where implementation is straightforward
- Meeting flag:
  - `News`: confirm whether the `Category` control should be deleted and the search bar alone is enough for filtering before treating that as a dev change
- Meeting flag:
  - `Knowledge Centre`: applied-filter colour coding to match content chips is technically feasible, but it is not in the current design and should be discussed before being treated as dev remediation
- High-priority QA note:
  - factsheets with white text on the webpage are not readable on the printable version; treat this as urgent print QA breakage inside the print-stylesheet lane, not as optional print cleanup
  - table cell shading should be removed for printer-friendliness, with only light grey header cells retained; treat this as the same urgent print QA lane and complete it as soon as possible

## Later Sync Flag - factsheets taxonomy and categorization
- The requested factsheets filter change from the current single filter to `Program` + `Category` is flagged as significant tagging and categorization work.
- PM guidance:
  - do not treat this as a light UI-filter enhancement
  - review the source taxonomy document in sync first, then confirm whether the current factsheet content is already tagged cleanly enough to support a primary `Program` filter plus secondary `Category` filter
  - if tagging is incomplete or inconsistent, the work should be estimated as content-model and source-data normalization before front-end filter implementation

## Later Sync Flag - backend-driven lending values
- The following MASC feedback items are flagged for a later sync because they appear to be sourced from the backend dataset and may need conditional rendering or formatter logic rather than static page edits:
  - `Loan Maximum` comma formatting such as `$5,750,000`
  - `View Lending Rates` link behavior where the CTA may be rendered from dataset-driven content
  - `Young Farmer Rebate` numeric formatting such as `$400,000`
  - phrase normalization such as `two per cent` and `five years of the loan` if those strings are injected from structured source data
- PM guidance:
  - do not treat these as normal content polish inside a small page-cleanup sprint
  - review in sync first, then decide whether they belong in a separate backend-logic task or a rendering-layer formatting pass
- Separate dev remediation note:
  - `Your myMASC` browser tab title should render as `Your myMASC`, not `Your **my**MASC`; this is tracked as front-end rendering cleanup rather than content review.

## Responsiveness Planning Note
- Add a follow-up to build an action plan for responsiveness remediation and discuss it with Alex.
- Working checklist file: `/Users/aarongilani/project-manager/masc/masc-responsiveness-qa-checklist-2026-03-25.md`
- Current planning assumption: this is a short PM or tech-lead alignment task to define the next remediation lane after the completed homepage responsiveness pass.
- Scheduling note: the Alex sync was planned for the week of `2026-03-23`, and `MASC-05` has now closed with the responsive tasks broken out and handed off to Alex.
- Delivery note: the remediation plan should be built collaboratively with Aaron and should include owner assignment and sequencing recommendations, not just notes from the Alex conversation.
- Prep note: if execution time remains at the end of Friday, `2026-03-20`, use it to sketch inputs for the Monday, `2026-03-23` sync rather than starting another unrelated MASC workstream.
- Update on `2026-03-25`: the responsiveness sync is complete, the responsive tasks were broken out, and the remediation lane was handed off to Alex.

## FR Review Note
- Mike has now provided the French version of the MASC logo.
- Immediate follow-up: update the FR side with the new logo asset first thing Monday, `2026-03-23`.
- Asset note: the supplied vector is a colour version; current working assumption is that it can be converted to solid white if needed without requiring a separate redesign request.
- Mike is collecting French content feedback separately, so `MASC-06` should stay scoped to the logo update rather than absorb the broader FR review.
- Update on `2026-03-20`: there are apparently multiple logo assets in the shared Drive folder, so `MASC-06` should now start with a short asset review before the final FR-side swap is made.
- Validation note: the Drive folder contents have not been independently inspected from this environment, so this scope update is based on the user's note rather than direct file review.
- Completion note on `2026-03-23`: the FR logo asset review and update are now complete.

## Recent Completed Work
- The FR logo asset review and update, `MASC-06`, were completed on `2026-03-23`.
- `MASC-05` was completed on `2026-03-25`; the responsiveness tasks were broken out and handed off to Alex.
- The Monday internal sync for the broader responsiveness lane was completed on `2026-03-23`.
- The calculator missing-values fix was completed on `2026-03-20`.
- The archive-page category coin update for year, crop, and map type was completed and deployed to production on `2026-03-19`.
- The dynamic script evaluation and next-step capture were completed on `2026-03-19`.
- The EN feedback review and follow-on scope capture were completed on `2026-03-19`.
- A MASC sync meeting was completed on `2026-03-19`.
- A `45` minute MASC meeting on dynamic script calculations was completed on `2026-03-18`.
- The thematic crop maps archive build completed on `2026-03-17`.
- The thematic crop maps pull request was merged into `main` on `2026-03-18`.
- Homepage responsiveness was completed on `2026-03-18`, including responsive improvements to the homepage hero, post-hero layout, footer, footer attribution area, and resource carousel.
- Homepage responsiveness completion details:
  - heading and sub-heading styles in the homepage hero were adjusted to scale more cleanly on smaller screens
  - hero section layout and spacing classes were updated for better mobile and tablet structure
  - footer banner padding, footer content spacing, and attribution logo layout were refined for smaller breakpoints
  - carousel navigation, dots, and slide spacing were improved for mobile and tablet behavior
  - service-card margin behavior was tuned for better alignment across desktop and mobile
  - responsive SVG masks were added for the hero and footer wave shapes
  - no additional action was needed on the News and Updates or calculators sections after the final pass
- The `MMPP` featured maps block was completed on `2026-03-18`; merge review is now in progress before the work is fully folded into the current MASC rollout.
- The featured thematic crop maps block merge and rollout were completed on `2026-03-19`, and the block is now added to both the English `MMPP` page and the French-side page.
- Content follow-up: the content team still needs to provide French translations for the featured block content on the French `MMPP` page.
- `540` thematic crop map records were imported on `2026-03-18` using the import scripts built the previous day.
- The `ThematicCropMaps` custom post type was extended with hierarchical taxonomies for:
  - `thematic_year`
  - `thematic_crop`
  - `thematic_map_type`
- The thematic crop maps archive template now renders FacetWP-powered filters for year, crop, and map type.
- Crop map cards now display taxonomy metadata and descriptions to improve filtering context and content clarity.
- Project documentation was expanded to cover broken-link checks and thematic crop map import workflows, including command usage and verification steps.
- A `lib/wp-cli.php` bootstrap file was added to register a WP-CLI import command for thematic crop maps, creating a cleaner automation path for bulk imports.

## EN Feedback Triage Notes - 2026-03-19
- Developer-owned follow-up fixes identified:
  - reduce whitespace between the page header and the start of the AgriInsurance Claims content, likely by reusing the tighter image-overlap pattern seen on the How to File a Report page
  - add borders on all four sides of affected table cells
  - update the Complementary Program link so Program and Seeding Deadlines points only to Seeding Deadlines
  - fix the borrowing amount formatting so it displays as `$5,750,000`
  - update the myMASC sign-in link to point to `https://my.masc.mb.ca/` instead of the long direct Azure B2C authorization URL, pending confirmation on whether this is a sitewide change
- Plugin or Jordan-owned items flagged during review:
  - LPI widget results styling updates are with Jordan
  - titlebar title alignment appears to come from the plugin layer and is with Jordan
  - Mike's Calculators doc follow-up appears to sit with Jordan because he built the plugin
- Client, content, or clarification flags identified during review:
  - removing the Back to Top button appears to be a global change and should be flagged to the client before implementation
  - the missing lending rates link may be a Holly or content update and needs ownership confirmation
  - the sub-bullet differentiation under the myMASC information bullets may already be partly addressed and needs confirmation on what remains
  - the whitespace feedback should be confirmed against the intended How to File a Report layout pattern before implementation begins

## Search Regression Note
- `MASC-03` should include search-result summary quality, not just the visible search bar and results layout.
- Specific symptom to review in the Monday, `2026-03-23` sync: calculator pages and similar pages where the page body is mostly just the calculator are producing awkward WordPress-generated descriptions in search results.
- Likely outcome needed from sync: decide whether those pages need custom excerpts, search-specific summary fields, or a theme-level override for search-result descriptions.

## What This Project Appears To Be
- A custom MASC site built on a reusable `Basic-WP` starter, then extended with MASC-specific blocks, content types, and templates
- The site appears content-heavy and bilingual, with both English and French routes present in the current crawl data
- Major site sections include insurance, lending, calculators, factsheets, knowledge centre, reports and publications, yield data, careers, policies, contact, and sitemap

## Architecture
- Theme style: classic PHP WordPress theme, not an FSE theme
- Base stack: PHP + ACF + Tailwind CSS v4 + Playwright
- Theme bootstrap: `functions.php`
- Core logic lives in `lib/`
- WP-CLI integrations now also live in `lib/`, including thematic crop map import bootstrap wiring
- Templates use classic PHP files such as `front-page.php`, `archive-*.php`, `single-*.php`, `page.php`, and `search.php`
- ACF blocks are registered from `views/blocks/*`
- Build output compiles to `static/dist/theme.css`

## Content Model
- Confirmed custom post type files exist for:
  - `factsheet`
  - `knowledgecentre`
  - `reportsandpublications`
  - `servicecentre`
  - `thematiccropmaps`
  - `yieldmanitoba`
- Thematic crop maps now also use hierarchical taxonomies for:
  - `thematic_year`
  - `thematic_crop`
  - `thematic_map_type`
- Custom archive templates exist for:
  - `factsheet`
  - `knowledgecentre`
  - `reports-publications`
  - `thematic-crop-maps`
  - `yield-manitoba`
- Custom single templates exist for:
  - `annual-report`
  - `factsheet`
  - `thematic-crop-maps`
  - `yield-manitoba`

## Block / Feature Inventory
- MASC-specific blocks include:
  - `masc-callout-section`
  - `masc-calculator-frame`
  - `masc-contact-banner`
  - `masc-contact-map`
  - `masc-home-news`
  - `masc-info-card`
  - `masc-info-cards`
  - `masc-knowledge-centre-carousel`
  - `masc-pdf-list`
  - `masc-quick-links`
  - `masc-resource-carousel`
  - `masc-service-centres`
  - `masc-social-media`
  - `masc-video-carousel`
  - `masc-yield-manitoba-cards`
- Shared starter blocks also remain in use, including accordion, button, buttons, grid, grid-cell, homepage hero, media-text, page-children, section, sitemap, and sitemap-post-list
- The thematic crop maps archive now includes FacetWP-powered filter controls for year, crop, and map type

## Tooling And Commands
- JS scripts from `package.json`:
  - `npm run watch`
  - `npm run build`
  - `npm run links:check`
- PHP quality scripts from `composer.json`:
  - `composer run lint`
  - `composer run fix`
- WP-CLI automation now includes a thematic crop maps import command registered via `lib/wp-cli.php`
- Theme includes Playwright accessibility coverage in `tests/site-a11y.spec.js`

## Current Repo State
- Repo is not clean
- Current modified/untracked items indicate active work in:
  - `README.md`
  - `package.json`
  - mobile navigation CSS
  - a new broken-link checker script
  - a generated broken-links report
  - planning notes under `planning/`

## Current Planning Signals
- `planning/sitemap-block.md` documents a sitemap block implementation plan
- `planning/table-with-legend.md` documents a reusable matrix table pattern system with ACF-driven variants
- `TODO.md` contains a sprint-style velocity log, but it appears stale because it is still labeled for `Dec 15 - Dec 19`

## QA / Delivery Risks
- A broken-link crawl report already exists and suggests active QA work:
  - 226 pages crawled
  - 371 links checked
  - 10 broken links
  - 2 warnings
  - 7 page fetch failures
- The broken-link checker uses local environment values from `.env`, which is good for repeatable QA
- The Playwright accessibility suite still targets `http://basic-wp.test/...` routes, which likely means the test configuration is inherited from the starter and may be stale for the current MASC environment
- Dirty worktree on `dev` means work is already in flight and should be reviewed before making scheduling assumptions

## PM Read On Likely Active Workstreams
- Merge and deploy the completed thematic crop map archive work
- Update archive page info cards to showcase coin categories for year, crop, and map type
- Update calculator backend data so program detail payloads are complete for dynamic script logic
- Restore the search bar and search results experience to acceptable quality after regression
- Restore the News and Updates block quality and validate the category coin design direction with design
- Navigation polish or mobile navigation refinement
- Broken-link remediation and link QA
- Sitemap or content-discovery improvements
- Table or data-display pattern work
- Ongoing enhancement of content-heavy archive and resource sections

## Useful Starting Points
- For theme behavior: `functions.php` and `lib/`
- For custom content types: `lib/custom-post-types/`
- For frontend components: `views/blocks/`
- For styling: `styles/`
- For active planning notes: `planning/`
- For QA: `tests/site-a11y.spec.js`, `bin/check-broken-links.js`, and `broken-links-report.json`

## PM Notes
- This is not a blank starter anymore; it is an actively customized client theme with multiple content systems already in place
- The strongest immediate execution risk is not missing architecture, it is coordination: current work-in-progress, outdated sprint notes, and partially stale QA tooling can create false signals if treated as fully current
- Before committing to a short deadline, confirm which of the current workstreams is the actual March 27 deliverable
- The `2026-03-23` staging feedback export materially expands open scope, so a fresh due date and execution order should be confirmed before treating `MASC-07` as committed delivery
