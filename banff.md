---
title: "Banff Project Context"
---

# Banff Project Context

- Last updated: `2026-04-07`

## Project Snapshot
- Project type: Local WordPress site with a custom classic PHP theme
- Local site root: `/Users/aarongilani/Local Sites/banff`
- Theme path: `/Users/aarongilani/Local Sites/banff/app/public/wp-content/themes/banff`
- Theme repo: Git repo inside the theme folder
- Current branch: `final-merge`
- Remote: `git@github.com:Vincent-Design-Inc/banff.git`

## Current Delivery Tasks
- Source row: `Workload Metrics - Main.csv`
- Technical feedback source: `/Users/aarongilani/Downloads/Banff’s_Indigenous_Experiences_Map_P3-1.csv`
- CSV load: Medium
- CSV start date: 2026-03-18
- CSV due date: 2026-04-11
- Release deadline: 2026-03-31
- Feedback update due: 2026-04-20
- Tracking override: using `2026-03-31` for release work based on direct instruction, with the Banff feedback update now formally due `2026-04-20`
- Priority: Medium
- Current tracked estimate: 30h total
- Task code prefix: `BANF`
- [x] Respond to Michel Technical Lead feedback in Asana | Completed: 2026-03-18
- [x] BANF-09 Audio cleanup recommendation reply | Completed: 2026-03-20
- [ ] BANF-01 MI_308 internal wording decision | Estimate: 1h | Due: 2026-04-08 | Scheduling: early next week
- [ ] BANF-02 MI_310 internal UX decision | Estimate: 1h | Due: 2026-04-08 | Scheduling: early next week
- [ ] BANF-03 MI_313 return-to-map decision | Estimate: 1h | Due: 2026-04-08 | Scheduling: early next week
- [ ] BANF-04 MI_320 spacing consistency decision | Estimate: 1h | Due: 2026-04-08 | Scheduling: early next week
- [ ] BANF-05 MI_307 state persistence | Estimate: 6h | Queue week of: 2026-04-06 | Formal due: 2026-04-20 | Internal target: 2026-04-10
- [ ] BANF-06 Michel feedback remediation bundle | Estimate: 20h | Queue week of: 2026-04-06 | Formal due: 2026-04-20 | Internal target: 2026-04-10
- [x] BANF-07 Push theme to GitHub | Completed: 2026-04-01
- [x] BANF-08 Production deployment pipeline | Completed: 2026-04-01
- [x] BANF-10 WPML URL structure review + Michele response | Completed: 2026-03-25
- Working date assumption: "this week" = Friday, March 20, 2026; "next week" = Friday, March 27, 2026
- Scheduling note: the Banff feedback update is formally due Monday, April 20, 2026, and the active Banff execution lane should now start early in the week of 2026-04-06 so the work still finishes well ahead of that date.
- Internal PM note: Banff PM-only review work should now sit at the end of next week and be treated as time-permitting internal triage rather than a same-day or early-week commitment.
- Protection note on `2026-04-02`: Banff has been re-triaged to early next week because the official due date is now `2026-04-20`; use the rest of this week to reduce `NWAC-01` and other carryover work first.
- Reminder: schedule an internal Banff meeting by end of next week, targeting Friday, `2026-03-27`.
- Deployment target: production
- Deployment trigger: GitHub Action on merge to `main`
- Audio note: a same-day recommendation request came in on `2026-03-20` for spoken-word audio recorded in a restaurant with heavy background noise; the immediate output is a tool recommendation and reply, not full production cleanup.
- Estimate assumption: existing GitHub access plus a standard production deployment flow
- Estimate risk: add 2h to 4h if hosting credentials, environment approvals, or custom deployment tooling are still undefined

## Audio Cleanup Note - 2026-03-20
- Incoming ask: provide guidance on better background-noise cleanup for restaurant-recorded audio where CapCut Premium did not remove enough ambient noise.
- Response status: outreach reply completed on `2026-03-20`; no further immediate Banff prioritization is needed unless the team asks for actual audio rescue work.
- Recommended response path:
  - first try [Adobe Podcast Enhance Speech](https://podcast.adobe.com/en/enhance-speech-v2) for fast spoken-word cleanup
  - if that is still not strong enough, try [Auphonic](https://auphonic.com/help/algorithms/multitrack.html) for adaptive denoise and leveling
  - if the recording is important enough to justify a paid desktop repair pass, use [iZotope RX 11](https://www.izotope.com/en/products/rx/features/dialogue-isolate.html) or [VEA](https://www.izotope.com/en/products/vea) for stronger dialogue isolation
- PM guidance:
  - restaurant ambience with overlapping voices is high-uncertainty cleanup work, so a recommendation reply should avoid promising a perfect result
  - if the Banff team needs actual rescue work beyond the tool recommendation, schedule that as a separate implementation item rather than absorbing it into `BANF-09`

## Michel Technical Lead Feedback Intake
- Extracted `37` Technical Lead comments from the Phase 3 CSV.
- Response scope this week: completed on `2026-03-18`; all `37` Michel items were acknowledged in Asana.
- Remediation scope next week: `32` actionable items grouped into accessibility, interaction, responsive polish, forms, sitemap, asset, and security-hardening work.
- `MI_307` is now tracked separately because it is a state-persistence / deep-linking feature rather than a light UX polish item.
- `MI_308` now carries an explicit internal-discussion step before remediation because the feedback is really about choosing the right universal action language, not only changing a button label.
- `MI_310` now carries an explicit internal-discussion step before implementation because Michel's note reads like a product or content-state question, not just a code defect.
- `MI_313` now carries an explicit internal-discussion step before remediation because the note is really questioning the expected navigation path back to the interactive map, not only a missing link.
- `MI_320` now carries an explicit internal-discussion step before remediation because the note is really about layout consistency and design intent, not only adding margin blindly to one page.
- These internal-discussion items are now intentionally triaged to end-of-next-week, time-permitting review because the external Banff feedback deadline has more room than the earlier internal schedule assumed.
- Deferred to a later phase or next submission instead of next week's remediation:
  - `MI_306` About page real-content re-evaluation
  - `MI_323` Resources page re-evaluation at next submission
  - `MI_324` Language toggle implementation example for next submission, with at least one fully translated example required
  - `MI_329` Image feature evaluation not yet performed
  - `MI_332` Video feature evaluation not yet performed

## MI_307 Roadmap Note
- `MI_307` requires URL state persistence for the homepage map experience so the selected location and the browser URL stay in sync.
- Minimum implementation scope assumed for the estimate:
  - push or replace URL state when a location is opened from the interactive map
  - hydrate the open state from the URL on page load or refresh
  - support back and forward navigation for the selected location state
  - reuse existing location permalinks where possible instead of inventing a parallel routing scheme
- This estimate does **not** assume a full single-page-router rebuild or a broader rewrite of all filter state handling.

## MI_308 Internal Discussion Note
- Michel's note is "Don't say view, find a more universal term."
- Internal decision needed before remediation:
  - confirm the preferred replacement language for the current map CTA
  - decide whether the fix stays local to one CTA or triggers a broader audit of sensory-specific wording in the map flow
  - align the wording choice with accessible, action-oriented language rather than sight-specific phrasing
- Planning assumption for the estimate:
  - hold a short internal review this week
  - lock the preferred wording so the implementation next week is a direct copy update instead of an open-ended content debate
- This estimate does **not** assume a full sitewide copy audit outside the Banff map experience.

## MI_310 Internal Discussion Note
- Michel's note flags the "View Different Artwork Locations" state as confusing and explicitly asks whether it is just a work-in-progress artifact.
- Internal decision needed before remediation:
  - is this screen the intended multi-result fallback behavior
  - does it only need clearer context and copy
  - or does it point to a larger issue with the map-to-list handoff
- Planning assumption for the estimate:
  - hold a short internal review this week
  - decide whether next week's work is a light UX clarification or a broader interaction change
- This estimate does **not** assume a redesign of the archive or a new multi-result navigation pattern.

## MI_313 Internal Discussion Note
- Michel's note flags a discoverability gap for getting back to the interactive map and points out that "go home" will not be obvious to every user.
- Internal decision needed before remediation:
  - should there be an explicit return-to-map CTA from downstream map-related pages
  - should the map experience keep stronger contextual breadcrumbs or navigation cues
  - is this a localized navigation fix or a broader information-architecture issue in the map journey
- Planning assumption for the estimate:
  - hold a short internal review this week
  - decide whether next week's work is a simple return-link addition or a broader navigation clarification
- This estimate does **not** assume a larger sitewide navigation redesign.

## MI_320 Internal Discussion Note
- Michel's note flags that the page would benefit from the same extra whitespace or margin treatment used on pages like About Us.
- Internal decision needed before remediation:
  - confirm which page or template this spacing comment applies to in the current build
  - decide whether the fix should follow an existing page-layout standard such as About Us
  - determine whether this is a local spacing adjustment or a broader template-consistency issue
- Planning assumption for the estimate:
  - hold a short internal review this week
  - lock the intended spacing pattern so next week's work is a direct layout adjustment rather than a broader redesign discussion
- This estimate does **not** assume a full template-system refactor or global spacing overhaul.

## Stakeholder Flags
- `MI_311`: flag to the PO and content collection team that the DMC logo should be provided and used as SVG only. The non-scalable version becomes fuzzy or blurry at some screen sizes and zoom levels, so this is an asset-quality dependency rather than just a front-end polish issue.
- `MI_312`: flag to the PO and content collection team that sponsor logos should be acquired or created as SVG versions where possible. The current versions render blurry at times on high-DPI screens, so this is also an asset-quality dependency rather than only a styling issue.
- `MI_324`: flag to the PO and content collection team that the next submission needs at least one full language-toggle implementation example backed by actual translated content. This depends on confirming the content pair and supplying approved source and translated copy, not only wiring the toggle UI.
- `MI_330`: flag to the content collection team that all non-decorative Banff images need alt text. Michel's note is a reminder-level observation, but it should be treated as a concrete content QA requirement before submission.
- `MI_336`: password protection is implemented and complete as of `2026-03-23`; this is no longer an open Banff environment dependency.

## Decision Log
- `2026-03-18` - `MI_315`: use ASCII or Unicode character encoding to obfuscate publicly rendered email addresses instead of exposing them as straight HTML. Planning assumption: treat this as the working spam-mitigation approach for next week's remediation, while keeping the visible address readable for users.
- `2026-03-18` - `MI_324`: confirm that the next submission should include at least one full language-toggle implementation example with actual translated content, and treat PO/content approval as a prerequisite instead of assuming placeholder text is sufficient.

## WPML URL Structure Note - 2026-03-24
- Michele's question is architectural: do translated Banff pages keep English slugs, or do slugs and path segments translate as part of the language-toggle experience.
- Working research note from WPML official docs:
  - WPML supports multiple language URL formats, including directories, separate domains, and query-parameter mode.
  - WPML supports translated slugs for pages, posts, custom post types, and taxonomies when slug translation is enabled and the content type is configured as translatable.
  - This should be treated as an early architecture decision because it affects permalink strategy, translated content setup, and how closely the language switcher should mirror localized URL structures.
- Response goal for `BANF-10`:
  - confirm the supported URL patterns
  - confirm whether translated slugs are viable for Banff's intended content model
  - reply to Michele with a recommendation before the next-submission language-toggle implementation example is scoped
- Completion note on `2026-03-25`:
  - `BANF-10` is complete
  - working recommendation delivered: let WPML own localized page, post, and taxonomy URLs and feed JS the localized permalinks or archive/filter URLs rather than inventing English-only route names in the client layer
- Source notes:
  - [Language Setup](https://wpml.org/documentation/getting-started-guide/language-setup/)
  - [How to Translate URL Slugs with WPML](https://wpml.org/documentation/getting-started-guide/translating-page-slugs/)

## Remediation Buckets
- Map, filter, and navigation behavior:
  - `MI_302`, `MI_303`, `MI_309`, `MI_310`, `MI_313`, `MI_335`
- State persistence and deep linking:
  - `MI_307`
- Accessibility semantics, labels, and screen-reader improvements:
  - `MI_300`, `MI_301`, `MI_304`, `MI_305`, `MI_322`, `MI_327`, `MI_328`, `MI_333`, `MI_334`
- Internal discussion items before remediation:
  - `MI_308`, `MI_310`, `MI_313`, `MI_320`
- Responsive, layout, and sitemap cleanup:
  - `MI_314`, `MI_316`, `MI_317`, `MI_318`, `MI_319`, `MI_320`, `MI_321`, `MI_325`, `MI_326`, `MI_331`
- Asset, content, and environment hardening:
  - `MI_311`, `MI_312`, `MI_315`, `MI_330`, `MI_336`

## Estimate Breakdown
- Review Michel's `37` comments and post complete Asana responses this week: 4h
- Review `MI_308` internally and lock sensory-neutral map wording this week: 1h
- Review `MI_310` internally and lock the intended remediation path this week: 1h
- Review `MI_313` internally and lock the return-to-map navigation approach this week: 1h
- Review `MI_320` internally and lock the page-spacing consistency approach this week: 1h
- Implement `MI_307` deep linking and URL state persistence next week: 6h
- Implement remaining map, filter, navigation, and accessibility interaction fixes next week: 8h
- Implement responsive, sitemap, footer, and form cleanup next week: 7h
- Handle asset/security/environment items and verification next week: 5h

## Feedback Risks / Dependencies
- `MI_307` touches open-state behavior, browser history, refresh hydration, and permalink expectations, so it has a higher regression risk than the smaller Banff UX fixes.
- `MI_308` may widen from a one-label change into a broader terminology sweep if the current map flow contains more sensory-specific wording than the first comment suggests.
- `MI_310` may widen from a simple copy or context fix into a broader interaction change if the current multi-result transition is not the intended product behavior.
- `MI_313` may widen from a simple return-link fix into a larger navigation or wayfinding change if the current map journey lacks enough contextual cues beyond the homepage entry point.
- `MI_320` may widen from a local whitespace adjustment into a broader page-template consistency pass if the spacing system is not applied consistently across comparable Banff pages.
- `MI_311` should be flagged to the PO and content collection team: use only the DMC SVG logo because the current non-scalable version becomes blurry at some sizes and zoom levels.
- `MI_312` should be flagged to the PO and content collection team: acquire or create SVG versions of sponsor logos because the current assets can appear blurry on high-DPI screens.
- `MI_324` remains deferred to the next submission and depends on PO/content confirming the translated example content needed to validate the language toggle properly.
- `MI_315` now has a working implementation decision: use ASCII or Unicode email obfuscation rather than leaving exposed addresses as plain HTML, and verify the rendered output remains usable.
- `MI_330` should be flagged to content collection as a reminder to add alt text to all non-decorative images, while `MI_334` may still need content review to distinguish decorative imagery from content images needing alt text.
- `MI_336` password protection was implemented and completed on `2026-03-23`, so it should no longer be treated as an open access blocker.
- `MI_314` and `MI_335` may expand once breakpoint and keyboard-regression testing begins.

## What This Project Appears To Be
- A Banff-focused content site with custom editorial pages plus a location directory and individual location detail pages
- Main content entities are `location` and `resource`
- The site includes an interactive Indigenous map, location archive filters, resource content, sponsors, sitemap pages, and standard marketing/informational pages
- Local QA routes explicitly cover `/`, `/about/`, `/resources/`, `/sitemap/`, `/sponsors/`, `/contact-us/`, `/location/`, and `/location/cascade-mountain-meadow/`

## Architecture
- Theme style: classic theme, not Full Site Editing
- Main PHP entry point: `functions.php`
- Core setup files live in `inc/`
- Templates are classic PHP templates such as `front-page.php`, `archive-location.php`, `single-location.php`, `page.php`, `single.php`, and `archive.php`
- Shared layout partials live in `template-parts/`
- Selectable page templates live in `templates/`
- Gutenberg is used as a curated content composer rather than as an FSE site-builder
- The theme uses `theme.json` for tokens and editor constraints, while actual UI is rendered through PHP templates and ACF blocks

## Content Model
- Custom post types from ACF JSON:
  - `location`
  - `resource`
- Custom taxonomy from ACF JSON:
  - `classification`
- `location` content includes custom fields for indigenous title, map marker, latitude, longitude, icon, list-view icon, and short description
- Classification terms have their own icon field
- The location archive supports classification filters for:
  - Artworks
  - Cultural Institution
  - Land and Site

## Block Inventory
- Custom ACF server-rendered blocks under `blocks/`:
  - `breadcrumbs`
  - `content-section`
  - `hero`
  - `indigenous-map`
  - `location-backdrop`
  - `location-card`
  - `location-feature`
  - `location-header`
  - `related-locations`
  - `section`
  - `sitemap-post-list`
  - `sponsor-list`
  - `teaching-resources`
  - `test`
- These blocks are registered from `blocks/*/block.json` via `inc/acf.php`
- ACF JSON is code-owned and saved/loaded from the theme `acf/` directory

## Frontend Stack
- CSS: Tailwind CSS v4 build into `static/dist/theme.css`
- Fonts: Google Fonts for `Roboto` and `Roboto Slab`
- Theme tokens: defined in `theme.json`
- Storybook: used for component preview and UI iteration
- Playwright: used for runtime screenshots, Storybook screenshots, and accessibility checks
- Axe: used in Playwright accessibility tests

## Working Conventions
- The README and `AGENTS.md` describe this as an ACF-first classic starter adapted for Banff
- Preferred UI pattern is inline Tailwind utilities inside block/template markup
- Shared `c-*` and `l-*` classes are only meant for repeated patterns
- Patterns are code-owned and live in `patterns/`
- Storybook routes and definitions are co-located with components
- Storybook preview routes are served by WordPress using `/?banff_story=<slug>&banff_story_fragment=1`
- Post editor constraints are enforced for normal posts via `inc/editor-constraints.php`

## Important Files
- Theme metadata: `style.css`
- Build and test scripts: `package.json`
- PHP lint scripts: `composer.json`
- Theme setup: `inc/theme-setup.php`
- Asset loading: `inc/assets.php`
- ACF block registration and JSON sync: `inc/acf.php`
- Storybook preview bridge: `inc/storybook-preview.php`
- Location archive implementation: `archive-location.php`

## Useful Commands
- Install PHP deps: `composer install`
- Install JS deps: `npm install`
- Build CSS: `npm run build`
- Watch CSS: `npm run watch`
- PHP lint: `npm run lint` or `composer run lint`
- Run Storybook: `npm run storybook`
- Runtime screenshots: `npm run screenshots`
- Runtime accessibility: `npm run test:a11y`
- Storybook screenshots: `npm run screenshots:stories`
- Storybook accessibility: `npm run test:a11y:stories`
- Figma verification pass: `npm run ui:verify:figma`

## Known In-Progress State
- The theme repo is not clean; `git status --short` shows many modified, deleted, and untracked files
- The current work appears to be a major transition from FSE template files to classic PHP templates plus Storybook/Playwright support
- The branch name `final-merge` suggests this is an integration branch rather than a fresh baseline

## Open Work Captured In Repo Docs
- `docs/client-status-todo.md` lists unfinished work including:
  - image lightbox behavior
  - accessibility remediation
  - media asset cleanup, alt text, captions, and metadata
  - resource sections on location pages
  - replacing placeholder resource content
  - deciding whether teaching resources exist or should be redesigned/removed
  - consistent ripple-effect background usage

## Practical Starting Points
- For theme behavior: start in `functions.php` and `inc/`
- For page/layout output: inspect `front-page.php`, `archive-location.php`, `single-location.php`, and `template-parts/`
- For component work: inspect `blocks/<block>/render.php`, `block.json`, stories, and ACF JSON
- For styling changes: inspect `styles/theme.css`, `theme.json`, and block/template utility classes
- For QA: inspect `tests/routes.js`, `tests/storybook-routes.js`, and `playwright.config.js`
