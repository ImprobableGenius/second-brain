---
title: "MASC Architecture"
---

# MASC Architecture

## Technical Snapshot
- Source: `Workload Metrics - Main.csv`
- Project type: Local WordPress site with a custom theme
- Local site root: `/Users/aarongilani/Local Sites/masc`
- Theme path: `/Users/aarongilani/Local Sites/masc/app/public/wp-content/themes/masc-wordpress`
- Theme repo: Git repo inside the theme folder
- Current branch: `dev`
- Remote: `git@github.com:Vincent-Design-Inc/masc-wordpress.git`

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

## Useful Starting Points
- For theme behavior: `functions.php` and `lib/`
- For custom content types: `lib/custom-post-types/`
- For frontend components: `views/blocks/`
- For styling: `styles/`
- For active planning notes: `planning/`
- For QA: `tests/site-a11y.spec.js`, `bin/check-broken-links.js`, and `broken-links-report.json`

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

## PM Notes
- This is not a blank starter anymore; it is an actively customized client theme with multiple content systems already in place
- The strongest immediate execution risk is not missing architecture, it is coordination: current work-in-progress, outdated sprint notes, and partially stale QA tooling can create false signals if treated as fully current
- Before committing to a short deadline, confirm which of the current workstreams is the actual March 27 deliverable
- The `2026-03-23` staging feedback export materially expands open scope, so a fresh due date and execution order should be confirmed before treating `MASC-07` as committed delivery
