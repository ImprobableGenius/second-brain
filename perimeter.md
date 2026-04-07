---
title: "Perimeter Project Context"
---

# Perimeter Project Context

## Project Snapshot
- Project type: WordPress marketing/site build
- Local site path: `/Users/aarongilani/Local Sites/perimeter`
- Theme path: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter`
- Theme name: `Perimeter/Bearskin`
- Theme version: `3.0.2`
- Theme base: Sage / Acorn
- Task code prefix: `PERM`
- Current branch: `feat/zoom-fix`
- Status: Support / colleague-assist context
- Priority: Unscheduled

## Current Delivery Tasks
- [ ] `PERM-01` Flight widget debug + PR finalization | Estimate: `2h`
- Estimate basis:
  - the core issue has already been investigated and partially fixed on branch `feat/zoom-fix`
  - three related commits are already in place
  - remaining work appears to be finalizing the dirty widget/view/style changes, sanity-checking behavior, and cleaning the PR state

## Stack
- WordPress `5.9+`
- PHP `8.1+`
- Roots Sage
- Roots Acorn `^3.1`
- Blade templates
- Tailwind CSS `3.4`
- Bud `6.12`
- Sass
- ACF JSON field groups
- Gutenberg / custom block registrations

## Theme Architecture
- Theme bootstrap and WordPress setup live in:
  - `app/setup.php`
  - `app/admin.php`
  - `app/helpers.php`
  - `app/filters.php`
- Theme service-provider wiring lives in:
  - `app/Providers/ThemeServiceProvider.php`
- Custom block and editor registrations live in:
  - `app/Include/sage-acf-gutenberg-blocks.php`
  - `app/Include/block-patterns.php`
  - `app/Include/elements.php`
- Blade templates are under:
  - `resources/views/`
- Scripts are under:
  - `resources/scripts/`
- Styles are under:
  - `resources/styles/`
- Synced ACF field groups are stored in:
  - `acf/field_groups/`
- Built assets output to:
  - `public/`

## Current Code Reality
- The theme is a fairly full custom Sage build, not a lightweight brochure-theme override.
- There is a large custom block library under `resources/views/blocks/`, including:
  - homepage and content-hero variants
  - destination and featured-content blocks
  - map and parking blocks
  - accordion, CTA, card, and section patterns
  - form and search-related blocks
- Shared Blade components include:
  - `flight-search`
  - navigation variants
  - buttons, cards, alerts, featured-posts, and protected content
- Script modules include:
  - `StickyNav`
  - `Scroller`
  - `mmenu`
  - `leaflet`
  - `HomepageFeatures`
  - `DestinationsSlider`
  - `Tables`
  - `CategorySelect`
  - `Newsletter`
  - `SeatSalesDetails`
- The presence of `leaflet`, `flight-search`, parking/map blocks, and destination components suggests the site includes route, travel, and airport-style content interactions.
- ACF is heavily used; the theme currently has a large set of synced JSON field groups in `acf/field_groups/`.

## Current Repo State
- Current branch: `feat/zoom-fix`
- Recent committed branch work:
  - `e14d54d` apply overflow hidden to the homepage hero
  - `22dc75d` apply overflow hidden to the html document
  - `a2cbaa6` hide the autosuggest_overflow
- Current tracked modifications:
  - `resources/styles/components/flight-search.scss`
  - `resources/views/components/flight-search.blade.php`
  - `theme.json`
- Current untracked files/directories:
  - `resources/scripts/modules/Newsletter.js`
  - `resources/vendor/`
- Working read: the current branch activity is centered on the flight widget concern.
- The remaining dirty diff suggests the next completion steps are:
  - final widget overflow / z-index behavior when the calendar is open
  - patched widget-script loading from `resources/vendor/`
  - small widget config/data adjustments in the Blade component
  - cleanup of the unrelated `theme.json` change if it is not part of the fix
- Newsletter-related frontend work remains untracked on the same branch and should not be silently folded into the flight-widget estimate unless explicitly intended.

## Useful Starting Points
- Theme bootstrap: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter/app/setup.php`
- Theme provider: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter/app/Providers/ThemeServiceProvider.php`
- Block registration: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter/app/Include/sage-acf-gutenberg-blocks.php`
- Main layout: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter/resources/views/layouts/app.blade.php`
- Header partial: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter/resources/views/partials/header.blade.php`
- Flight search component: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter/resources/views/components/flight-search.blade.php`
- Flight search styles: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter/resources/styles/components/flight-search.scss`
- Theme config: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter/theme.json`
- Scripts entry: `/Users/aarongilani/Local Sites/perimeter/app/public/wp-content/themes/perimeter/resources/scripts/app.js`

## Reporting Notes
- `PERM-01` 2026-04-06: colleague support and debugging for the Perimeter flight widget concern on branch `feat/zoom-fix`.
- Working actual for reporting: `3h` of response/support time on 2026-04-06.
- Working remaining estimate to complete the widget/PR lane: `2h`.
- Scope note: that estimate is for finishing the current flight-widget concern only, not for absorbing the untracked newsletter/vendor work unless that is confirmed as part of the same PR.

## PM Notes
- Perimeter is currently a support context, not an actively scheduled delivery lane in the portfolio.
- The theme is substantial enough that future help requests should be treated as real project work, not tiny ad hoc fixes.
- If Perimeter starts recurring, it should be promoted into the tracked board with `PERM-*` tasks rather than kept only in daily reporting notes.
