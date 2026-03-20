# MACY Project Context

## Snapshot
- Project type: WordPress maintenance
- Load: Low
- Working estimate: 3h total
- Task code prefix: `MACY`
- Priority: Low
- Start date: TBD
- Deadline: TBD
- Status: Waiting on Client Approval

## Current Task
- [ ] MACY-01 Recommended Tracking CPT refactor | Estimate: 3h | Trigger: on client approval and when capacity is available

## Issue Summary
- The `Recommended Tracking` page is failing to load and save reliably because the tracking block currently stores too much data directly in page content.
- That payload appears to exceed server limits during save/update operations, which is causing the page editing failures.

## Proposed Fix
- Move the tracking dataset into a Custom Post Type instead of storing the full payload in page content.
- Replace the current heavy block usage on the page with a lighter display block that reads from the Custom Post Type data.
- Keep the recommendation scoped as maintenance work unless the client expands the request beyond storage refactor and display wiring.

## Estimate Breakdown
- Create and wire the Custom Post Type storage model: 1h
- Update the tracking block/page integration to read the lighter data source: 1h
- Regression check loading and saving on the affected page: 1h

## Client Communication Context
- Recommendation already sent to client.
- Client-facing summary:
  - Current tracking block stores too much data in page content.
  - This exceeds server restrictions and breaks loading/saving.
  - Proposed solution is a Custom Post Type-backed data model with a lighter page block.
  - Estimated effort sent to client: `3 hours`.

## PM Risks / Open Questions
- Awaiting explicit client approval to proceed.
- Unknown whether existing page-stored tracking data needs a one-time migration/backfill into the new Custom Post Type.
- Unknown whether the fix should be treated as urgent maintenance once approved, or simply scheduled into the next available capacity window.

## Notes
- Original project shell came from `Workload Metrics - Main.csv`.
