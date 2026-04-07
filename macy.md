---
title: "MACY Project Context"
---

- Last updated: `2026-04-07`

## Snapshot
- Project type: WordPress maintenance
- Load: Low
- Working estimate: 5h total
- Task code prefix: `MACY`
- Priority: Low
- Start date: 2026-03-23
- Deadline: 2026-03-27
- Status: Complete

## Current Task
- [x] MACY-01 Recommended Tracking CPT refactor | Completed: 2026-03-27

## Issue Summary
- The `Recommended Tracking` page is failing to load and save reliably because the tracking block currently stores too much data directly in page content.
- That payload appears to exceed server limits during save/update operations, which is causing the page editing failures.

## Proposed Fix
- Move the tracking dataset into a Custom Post Type instead of storing the full payload in page content.
- Replace the current heavy block usage on the page with a lighter display block that reads from the Custom Post Type data.
- Backfill the existing Recommended Tracking data into the new Custom Post Type structure.
- Keep the display block on the current page rather than changing the editorial entry point.
- Deliver a short write-up explaining how to update the new Custom Post Type after launch.
- Keep the recommendation scoped as maintenance work unless the client expands the request beyond storage refactor and display wiring.

## Estimate Breakdown
- Create and wire the Custom Post Type storage model: 1h
- Update the tracking block/page integration while keeping the block on the current page: 1h
- Backfill existing Recommended Tracking data into the new Custom Post Type: 1h
- Regression check loading and saving on the affected page: 1h
- Write a short editor/admin update note for the new Custom Post Type workflow: 1h

## Client Communication Context
- Recommendation already sent to client.
- Client approval to proceed confirmed on `2026-03-20`.
- Confirmed implementation scope on `2026-03-20`:
  - backfill the existing Recommended Tracking data into the new post type
  - keep the block on the current page
  - share a short write-up on how to update the new post type
- Client-facing summary:
  - Current tracking block stores too much data in page content.
  - This exceeds server restrictions and breaks loading/saving.
  - Proposed solution is a Custom Post Type-backed data model with a lighter page block.
  - Estimated effort sent to client: `3 hours`.

## PM Risks / Open Questions
- Handoff is preferred if a good execution plan and available owner appear next week, but the task stays on Aaron's list until that handoff is actually arranged.
- The confirmed backfill and short write-up push the working PM estimate above the original client-facing 3h figure, so implementation should track against the updated 5h internal planning number.

## Scheduling Note
- Internal target: complete `MACY-01` by Friday, `2026-03-27`.
- Internal follow-up: check status and handoff options by Wednesday, `2026-03-25`.
- Planning assumption: keep Aaron as owner for now and hand off only if a clean plan and capacity become available midweek.

## Completion Note
- Recommendation changes are complete as of `2026-03-27`.
- The `Recommended Tracking` CPT refactor, backfill, current-page block support, and short update note are now treated as closed work.

## Notes
- Original project shell came from `Workload Metrics - Main.csv`.
