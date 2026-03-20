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
- Working estimate: 17h total for current open tasks
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
- [ ] MASC-02 EN feedback cleanup bundle | Estimate: 6h | Due: 2026-03-20
- Execution note on 2026-03-20: after `LCTX-01`, the next active work item is to finish `MASC-02`.
- [ ] MASC-03 Search regression handoff | Estimate: 5h | Due: TBD
- [ ] MASC-04 News and Updates regression + coin review | Estimate: 4h | Due: TBD
- [ ] MASC-05 Responsiveness remediation action plan + Alex sync | Estimate: 2h | Due: 2026-03-27
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
- Estimate risk: add 2h to 4h if responsiveness issues span multiple custom blocks, if production rollout reveals regression fixes, or if the featured maps block needs bespoke query logic or editorial controls beyond standard block fields
- Estimate risk: add 2h to 4h if any of the EN feedback cleanup items turn out to be sitewide template changes, plugin-layer edits, or content-owned updates rather than isolated theme fixes
- Estimate risk: add 2h to 4h if the missing calculator values trace back to a broader payload, schema, or cross-program data issue instead of a contained correction
- Estimate risk: add 2h to 3h if the regression includes deeper query relevance issues in `lib/search-features.php` in addition to the visible search bar and search results UI regressions
- Estimate risk: add 1h to 2h if the design department asks for broader category coin changes that need to be propagated beyond the News and Updates block
- Estimate risk: add 1h to 2h if MASC-05 expands beyond the agreed plan, Alex sync, owner assignment, and sequencing recommendation set into a broader remediation audit

## Responsiveness Planning Note
- Add a follow-up to build an action plan for responsiveness remediation and discuss it with Alex.
- Current planning assumption: this is a short PM or tech-lead alignment task to define the next remediation lane after the completed homepage responsiveness pass.
- Scheduling note: the Alex sync should happen during the week of `2026-03-23`, and `MASC-05` now sits in next week's execution lane with a working due date of `2026-03-27`.
- Delivery note: the remediation plan should be built collaboratively with Aaron and should include owner assignment and sequencing recommendations, not just notes from the Alex conversation.

## Recent Completed Work
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
