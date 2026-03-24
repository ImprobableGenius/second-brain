# Daily Report - 2026-03-17

## 📊 Capacity
- Weekly burn: 192h / 40h
- Portfolio load: 480% of weekly capacity
- Near-term delivery window: MASC due 2026-03-20, Banff release due 2026-03-31, Banff feedback update due 2026-04-03

## 🟢 What's Done
- Normalized the project tracker into a single estimated queue and rewrote `brain.md` into the PM-agent reporting format.
- Built or refreshed PM context for Encore Cabinets, NWAC, MACY, and Local Contexts.
- Converted generic queue placeholders into concrete tasks with estimates, blockers, and next decisions.
- A MASC sync meeting was completed on 2026-03-19.
- MASC thematic crop maps archive build is complete as of 2026-03-17, including taxonomy registration for year/crop/map type, FacetWP archive filters, expanded import and broken-link documentation, and a new WP-CLI import bootstrap.
- A `45` minute MASC meeting on dynamic script calculations was completed on 2026-03-18.
- Thematic crop maps were merged into `main` on 2026-03-18.
- MASC homepage responsiveness was completed on 2026-03-18 across the homepage hero, post-hero layout, footer, attribution area, and resource carousel, with no further action needed on the News and Updates or calculators sections.
- The `MMPP` featured maps block was completed on 2026-03-18 and is currently under merge review.
- The featured thematic crop maps block merge and rollout were completed on 2026-03-19, and the block is now added to both the English `MMPP` page and the French-side page.
- MASC EN feedback review and follow-on scope capture were completed on 2026-03-19.
- MASC dynamic script evaluation and next-step capture were completed on 2026-03-19.
- MASC archive-page category coin updates for year, crop, and map type were completed and deployed to production on 2026-03-19.
- MASC calculator script missing-values work was completed on 2026-03-20.
- `MASC-06` FR logo asset review and update were completed on 2026-03-23.
- The Monday internal MASC sync was completed on 2026-03-23.
- `LFMP-01` for the local `leaflet-maps-plugin` was completed on 2026-03-23; the bailout bug is resolved and the functionality is reported as working as expected.
- `BANF-09` audio-cleanup recommendation reply was completed on 2026-03-20.
- Banff `MI_336` password protection was implemented and completed on 2026-03-23.
- Local Contexts security-header updates were completed on 2026-03-20, and a follow-up was sent after completion.
- Orbeon historical survey data was exported to CSV on 2026-03-19 and is now ready for handoff once sharing details are confirmed.
- `540` thematic crop map records were imported on 2026-03-18 using the scripts built the previous day.
- Banff response handling for the current Michel Technical Lead feedback is complete as of 2026-03-18, with all `37` comments acknowledged in Asana.

## 🟡 What's In Progress
- `MASC-02` is still open after the `MASC-06` logo lane and the Monday internal sync were completed on 2026-03-23.
- New maintenance queue item: `UA Local 179` mobile app compatibility check for Samsung Galaxy S7 devices, estimated at 3h and currently waiting on deadline, priority, and test-environment details.
- Next week closeout: complete `IFWH` accessibility audit and remediation updates by Friday, 2026-03-27.
- Next week closeout: complete `NWAC` final documentation and compliance research by Friday, 2026-03-27.
- Next week scheduled item: `MACY-01` is approved to proceed, stays owned by Aaron for now, carries an internal follow-up on Wednesday, 2026-03-25, has an internal target date of Friday, 2026-03-27, and now explicitly includes data backfill plus a short update note for the new post type workflow.
- MASC EN feedback triage surfaced a new 6h cleanup bundle covering page-header whitespace reduction, table-border cleanup, a targeted program-link fix, borrowing-amount formatting, and a direct `my.masc.mb.ca` sign-in URL update once ownership and scope are confirmed.
- MASC queue addition: handoff-ready search regression fix to restore search results and the search bar to acceptable quality, estimated at 5h and currently waiting on scope clarification.
- Monday sync reminder for `MASC-03`: some calculator-driven pages and similar thin-content pages are producing awkward WordPress auto-generated search descriptions, so the sync should decide whether the right fix is custom excerpts, search-summary overrides, or a theme-level search-result rule.
- MASC queue addition: handoff-ready News and Updates block regression fix, estimated at 4h, with category coin design needing review by the design department.
- MASC queue addition: `MASC-05` to build a broader-site responsiveness remediation action plan and sync with Alex, estimated at 2h and now scheduled into next week with a working due date of Friday, 2026-03-27.
- `MASC-05` internal sync is now complete; the remaining follow-through is to capture the written plan, owner assignment, and sequencing recommendations cleanly.
- MASC staging feedback intake from `2026-03-23` has now been processed: `106` rows were reviewed, `344` struck-through items were excluded as complete, and `579` unresolved lines remain, so `MASC-07` has been added as a `55h` net-new remediation backlog estimate beyond the work already tracked in `MASC-02`, `MASC-03`, and `MASC-04`.
- MASC queue addition: `MASC-08` is a new 4h build item to create or restore the circular bin volume calculator widget and place it on the `Insurance with MASC` page, with a working due date of Wednesday, 2026-03-25 and permission to pull it into today if the current spillover lane stays contained.
- MASC later-sync flag: several lending-page feedback items now look backend-dataset-driven rather than content-only, including `Loan Maximum`, `Young Farmer Rebate`, and `View Lending Rates`, so they should be reviewed as rendering / formatter logic instead of routine copy cleanup.
- MASC later-sync flag: the factsheets filter request to move from the current single filter to `Program` + `Category` also looks materially larger than a UI change because it likely requires tagging, categorization, and source-data cleanup first.
- High-priority MASC QA fix: factsheets with white text on the webpage are not readable in print, so that issue should be treated as urgent print breakage under the print-stylesheet remediation lane.
- High-priority MASC QA fix: table cell shading should be removed for printer-friendliness, keeping only light grey header cells and leaving the rest of the table white; treat this as urgent print breakage under the same print-stylesheet lane.
- MASC meeting flag: confirm whether the `News` page should drop the `Category` control entirely and rely on the search bar alone for filtering.
- MASC meeting flag: applied-filter colour coding in the `Knowledge Centre` is technically feasible, but it is not reflected in the current design and should be discussed before being treated as remediation scope.
- Banff PM-only internal review items `MI_308`, `MI_310`, `MI_313`, and `MI_320` are now triaged to end of next week and should be worked only if time remains.
- Banff next week queue: `MI_307` is now tracked separately as deep linking and URL state persistence for the interactive map, with a formal feedback-update due date of 2026-04-03 and an earlier internal target still preferred.
- Banff queue addition: `BANF-10` is now a bounded 2h research-and-response item to confirm WPML URL and slug behavior for Michele, with delivery due by Friday, 2026-03-27.
- IPAM: member-object modeling and membership application frontend refinement.
- Banff next week queue: remediate the remaining current-scope Michel feedback bundle during the week of 2026-03-23, target early completion, and hold the formal feedback-update due date of 2026-04-03 while continuing GitHub and deployment release prep.

## 🔴 Blockers / Risks
- Total tracked work is 133h against a 40h week, so queued work cannot all move this week.
- Encore Cabinets marketing is blocked on U.S. shipment clarification.
- Orbeon Forms is waiting on client field definitions.
- The Orbeon historical survey export is complete, but the CSV is still waiting on sharing information before handoff.
- The Orbeon GitLab repo is stale and would need to move to GitHub, but that remains a separate maintenance item from the completed survey-data export.
- `MACY-01` is approved to proceed and scheduled for next week, but the confirmed backfill and short write-up raise the internal planning estimate beyond the original client-facing 3h and it may still be handed off midweek if a clean plan and available owner appear.
- NWAC documentation is now confirmed as a client handoff, but compliance framing decisions still need to be pinned down so the final package does not stall.
- `UA Local 179` has been added as a new maintenance item, but it still needs a target date, relative priority, and confirmation of whether the Samsung Galaxy S7 check will use a physical device or an emulator.
- Banff remediation still includes asset dependencies around SVG logo files; `MI_311` and `MI_312` specifically need to be flagged to the PO and content collection team because the DMC logo should be SVG-only and sponsor logos should be acquired or created as SVGs to avoid blurry rendering at some sizes, zoom levels, and high-DPI screens.
- `MI_324` remains a next-submission item and needs PO/content confirmation on which content will be used for the language-toggle example and what approved translated copy will support it.
- `BANF-10` is low execution risk but important architecture validation work because Michele is explicitly asking whether localized routes and translated slugs should be part of the WPML implementation strategy early, before Banff commits to a language-toggle pattern that would need rework later.
- `MI_330` should be flagged to content collection as a reminder to add alt text to all non-decorative images before the next submission.
- Banff `MI_307` is higher risk than the other Michel fixes because it requires browser history, refresh hydration, and permalink state to stay aligned.
- `BANF-09` is complete, but it may still turn into a follow-on production cleanup request if the simple tool recommendation does not rescue the audio enough for use.
- Banff `MI_308` may expand from a small wording change into a broader terminology review if there are more sensory-specific labels in the map experience.
- Banff `MI_310` may expand from a small clarification fix into a larger interaction change if the current multi-result page is not the intended product behavior.
- Banff `MI_313` may expand from a small return-link issue into a larger navigation or wayfinding change if the map journey lacks enough contextual cues.
- Banff `MI_320` may expand from a local whitespace adjustment into a broader page-template consistency pass if comparable Banff pages are not following one layout standard.
- NWAC secure-upload documentation is risky because the active file-encryption hook still contains debug output and hardcoded key material.
- The new MASC search regression task still needs scope clarity and may widen if the issue touches both the global search UI and the custom search-results logic in the theme.
- The new MASC News and Updates regression task depends on design review of the category coin treatment and may widen if that design decision needs to be propagated beyond the `masc-home-news` block.
- `MASC-05` now explicitly includes the written plan, Alex sync outcome, owner assignment, and sequencing recommendations, and it could still widen if the conversation turns into a broader sitewide responsiveness audit.
- `MASC-08` is expected to be contained if it can reuse the existing calculator-widget pattern, but it may widen if the bin volume tool needs net-new widget rendering or custom styling work to fit the current page layout.
- The MASC EN feedback pass has already surfaced a new cleanup bundle plus ownership questions around Jordan, Holly, client-approved global changes, and whether the myMASC sign-in update is page-local or sitewide.
- The newly processed MASC staging feedback export is the largest current portfolio scope increase: the estimate assumes repeated factsheet issues can be solved systemically, and it will grow materially if those fixes must be handled page by page.
- `MASC-02` is still open even though the Monday `MASC-06` and internal sync items are now complete, so the spillover cleanup bundle still needs a clean execution slot.
- The new thematic crop maps archive-page info-card task assumes existing coin styling can be reused for year, crop, and map type; it may widen if design wants a new taxonomy-coin variant.
- The featured thematic crop maps block is now live on the French-side page, but the content team still needs to supply French translations for the block content.
- Mike is collecting broader FR content feedback separately, and `MASC-06` has now closed cleanly without expanding into a wider French review task.

## Queue Snapshot
- This week: MASC
- Next active work: IFWH closeout, NWAC closeout, MACY-01, Banff technical remediation, Banff release prep, IPAM
- New maintenance intake: UA Local 179 Galaxy S7 compatibility check
- Current MASC next steps: route Jordan-owned plugin items and content-owned fixes to the right owners, finish `MASC-02`, capture the `MASC-05` written plan and sequencing follow-through, and get French translations for the featured block content on the French `MMPP` page.
- Current MASC next steps: finish `MASC-02`, complete `BANF-10`, pull `MASC-08` into today if runway opens, otherwise make it the next MASC implementation item tomorrow, and then return to the remaining owner-routing and `MASC-05` follow-through.
- New MASC queue item: `MASC-07` staging feedback remediation backlog beyond the currently tracked MASC scope
- New MASC handoff item: search results and search bar regression fix
- New MASC handoff item: News and Updates block regression with category coin design review
- New MASC queue item: EN feedback cleanup bundle for layout, borders, links, and formatting
- Next week reminder: schedule the internal Banff meeting by Friday, 2026-03-27
- Capacity queue: Encore Cabinets, AMIK
- Next week follow-up: if no AMIK response is received by Monday, 2026-03-30, send a check-in and confirm whether `ENH-001` stays parked until capacity opens
- Waiting on client: Orbeon Forms
- Next week follow-up: check `MACY-01` status and handoff options by Wednesday, 2026-03-25
- Documentation queue: NWAC

## Rest Of Week - 2026-03-18 To 2026-03-20
- Completed on 2026-03-18: Banff response handling for the current Michel Technical Lead feedback was closed in Asana.
- Completed on 2026-03-19: Orbeon historical survey structure and responses were exported to CSV and are now waiting on sharing details before handoff.
- Completed on 2026-03-19: MASC EN feedback review was closed and the follow-on cleanup bundle was captured in the tracker.
- Completed on 2026-03-19: MASC dynamic script evaluation was closed and the next-step capture was logged.
- Completed on 2026-03-19: MASC archive-page category coin updates were completed and deployed to production.
- Completed on 2026-03-20: the contained 2h MASC calculator missing-values fix was closed.
- Completed on 2026-03-20: `BANF-09` audio-cleanup recommendation reply was sent.
- Completed on 2026-03-20: Local Contexts security-header updates were closed and the follow-up was sent.
- End of day 2026-03-20: `MASC-02` remained open and now carries into Monday, 2026-03-23.
- Completed on Monday, 2026-03-23: `MASC-06` was closed and the internal sync ran as planned before returning to the remaining MASC lane.
- Next week, work `IFWH` ahead of `Banff` because the IFWH closeout date lands first on 2026-03-27.
- During the week of 2026-03-23, keep `MACY-01` on Aaron's list as the owner, follow up internally by Wednesday, 2026-03-25, and aim to close the work by Friday, 2026-03-27 unless a clean handoff becomes available first.
- During the week of 2026-03-23, run `MASC-05` and use the Alex sync to lock the broader MASC responsiveness remediation plan.
- Merge current MASC work to the production site on 2026-03-18.
- Use the remaining execution time this week on routing the new MASC cleanup bundle, plugin-owned items, and content-owned follow-ups after the archive-page work.
- Keep the Banff feedback update on an early internal target even though the formal due date is now 2026-04-03.
- Move the Banff PM-only internal decisions to end-of-next-week, time-permitting review instead of forcing them into today's or early-next-week lane.
- During the week of 2026-03-23, close `IFWH` accessibility work and `NWAC` documentation so both projects can be taken off the active board by Friday, 2026-03-27.
- Flag to content team: provide French translations for the featured thematic crop maps block content on the French `MMPP` page.
- Capture any Banff blockers, especially the `MI_311` DMC SVG asset dependency and the `MI_312` sponsor SVG asset need, so next week's remediation queue stays accurate.
- Keep the `MI_324` language-toggle dependency visible so the next submission does not reach implementation without approved translated content from PO/content.
- Keep the `MI_330` alt-text reminder visible so content collection closes image metadata gaps before submission.

## Slack Update
Today's PM pass now reflects that `MASC-06` is complete and the Monday internal sync has also been completed, while `MASC-02` remains the main open MASC spillover item and `MASC-05` now only needs the written follow-through captured. `IFWH`, `NWAC`, and `MACY-01` remain the main closeout items for the week ahead of Banff PM-only work. The main risk is still capacity: tracked work sits at 186h against a 40h week, and the cleanup bundle, owner-dependent follow-ups, Banff remediation, `MASC-05` follow-through, `MACY-01` handoff planning, the new `UA Local 179` maintenance intake, and the `NWAC` documentation framing decisions still need clean sequencing.
