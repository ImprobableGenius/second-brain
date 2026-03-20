# Daily Report - 2026-03-17

## 📊 Capacity
- Weekly burn: 136h / 40h
- Portfolio load: 340% of weekly capacity
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
- Orbeon historical survey data was exported to CSV on 2026-03-19 and is now ready for handoff once sharing details are confirmed.
- `540` thematic crop map records were imported on 2026-03-18 using the scripts built the previous day.
- Banff response handling for the current Michel Technical Lead feedback is complete as of 2026-03-18, with all `37` comments acknowledged in Asana.

## 🟡 What's In Progress
- MASC sprint work for 2026-03-20: complete the promised 2h calculator missing-values fix first, then route or schedule the new cleanup bundle surfaced during feedback review and sequence the remaining plugin-owned and content-owned items.
- Local Contexts today: move the security-header hardening task into today's lane and treat it as a same-day 5h maintenance pass.
- New queue item: audit the current agency site portfolio and identify which site most needs updating, estimated at 2h and tracked to Wednesday, 2026-03-25.
- New maintenance queue item: `UA Local 179` mobile app compatibility check for Samsung Galaxy S7 devices, estimated at 3h and currently waiting on deadline, priority, and test-environment details.
- Agency portfolio audit working source is now the user-provided Google Sheet, with the user's note that it should represent the full portfolio unless gaps are discovered.
- Next week closeout: complete `IFWH` accessibility audit and remediation updates by Friday, 2026-03-27.
- Next week closeout: complete `NWAC` final documentation and compliance research by Friday, 2026-03-27.
- MASC EN feedback triage surfaced a new 6h cleanup bundle covering page-header whitespace reduction, table-border cleanup, a targeted program-link fix, borrowing-amount formatting, and a direct `my.masc.mb.ca` sign-in URL update once ownership and scope are confirmed.
- MASC queue addition: handoff-ready search regression fix to restore search results and the search bar to acceptable quality, estimated at 5h and currently waiting on scope clarification.
- MASC queue addition: handoff-ready News and Updates block regression fix, estimated at 4h, with category coin design needing review by the design department.
- Banff PM-only internal review items `MI_308`, `MI_310`, `MI_313`, and `MI_320` are now triaged to end of next week and should be worked only if time remains.
- Banff next week queue: `MI_307` is now tracked separately as deep linking and URL state persistence for the interactive map, with a formal feedback-update due date of 2026-04-03 and an earlier internal target still preferred.
- IPAM: member-object modeling and membership application frontend refinement.
- Banff next week queue: remediate the remaining current-scope Michel feedback bundle during the week of 2026-03-23, target early completion, and hold the formal feedback-update due date of 2026-04-03 while continuing GitHub and deployment release prep.

## 🔴 Blockers / Risks
- Total tracked work is 133h against a 40h week, so queued work cannot all move this week.
- Encore Cabinets marketing is blocked on U.S. shipment clarification.
- Orbeon Forms is waiting on client field definitions.
- The Orbeon historical survey export is complete, but the CSV is still waiting on sharing information before handoff.
- The Orbeon GitLab repo is stale and would need to move to GitHub, but that remains a separate maintenance item from the completed survey-data export.
- MACY is waiting on client approval for the Custom Post Type refactor.
- NWAC documentation is now confirmed as a client handoff, but compliance framing decisions still need to be pinned down so the final package does not stall.
- Local Contexts is now scheduled for today, but CSP may still need a Report-Only rollout before enforcement and the scope still needs to be kept clear on whether it stops at hosting-level headers or expands into WordPress app review.
- The new agency portfolio audit is now estimated at 2h, and the user-provided Google Sheet is the working source of truth; its relative priority next week and whether the audit covers technical updates only or broader refresh needs still need to be confirmed.
- `UA Local 179` has been added as a new maintenance item, but it still needs a target date, relative priority, and confirmation of whether the Samsung Galaxy S7 check will use a physical device or an emulator.
- Banff remediation includes asset and environment dependencies around SVG logo files and password protection access; `MI_311` and `MI_312` specifically need to be flagged to the PO and content collection team because the DMC logo should be SVG-only and sponsor logos should be acquired or created as SVGs to avoid blurry rendering at some sizes, zoom levels, and high-DPI screens.
- `MI_324` remains a next-submission item and needs PO/content confirmation on which content will be used for the language-toggle example and what approved translated copy will support it.
- `MI_330` should be flagged to content collection as a reminder to add alt text to all non-decorative images before the next submission.
- Banff `MI_307` is higher risk than the other Michel fixes because it requires browser history, refresh hydration, and permalink state to stay aligned.
- Banff `MI_308` may expand from a small wording change into a broader terminology review if there are more sensory-specific labels in the map experience.
- Banff `MI_310` may expand from a small clarification fix into a larger interaction change if the current multi-result page is not the intended product behavior.
- Banff `MI_313` may expand from a small return-link issue into a larger navigation or wayfinding change if the map journey lacks enough contextual cues.
- Banff `MI_320` may expand from a local whitespace adjustment into a broader page-template consistency pass if comparable Banff pages are not following one layout standard.
- NWAC secure-upload documentation is risky because the active file-encryption hook still contains debug output and hardcoded key material.
- The new MASC calculator missing-values pass is intentionally contained at 2h for Friday, March 20, 2026; if it uncovers broader payload, schema, or data-source issues, that follow-on work should be rescheduled instead of being absorbed into the promised fix.
- The new MASC search regression task still needs scope clarity and may widen if the issue touches both the global search UI and the custom search-results logic in the theme.
- The new MASC News and Updates regression task depends on design review of the category coin treatment and may widen if that design decision needs to be propagated beyond the `masc-home-news` block.
- The MASC EN feedback pass has already surfaced a new cleanup bundle plus ownership questions around Jordan, Holly, client-approved global changes, and whether the myMASC sign-in update is page-local or sitewide.
- The new thematic crop maps archive-page info-card task assumes existing coin styling can be reused for year, crop, and map type; it may widen if design wants a new taxonomy-coin variant.
- The featured thematic crop maps block is now live on the French-side page, but the content team still needs to supply French translations for the block content.

## Queue Snapshot
- This week: MASC
- This week also: Banff internal UX decisions on `MI_308`, `MI_310`, `MI_313`, and `MI_320`
- Next active work: IFWH closeout, NWAC closeout, Banff technical remediation, Banff release prep, IPAM
- Today's additional lane: Local Contexts security-header hardening
- Next queued audit: agency portfolio review due 2026-03-25
- New maintenance intake: UA Local 179 Galaxy S7 compatibility check
- Current MASC next steps: complete the calculator missing-values fix, route Jordan-owned plugin items and content-owned fixes to the right owners, schedule the new EN feedback cleanup bundle, and get French translations for the featured block content on the French `MMPP` page
- New MASC handoff item: search results and search bar regression fix
- New MASC handoff item: News and Updates block regression with category coin design review
- New MASC queue item: EN feedback cleanup bundle for layout, borders, links, and formatting
- Next week reminder: schedule the internal Banff meeting by Friday, 2026-03-27
- Capacity queue: Encore Cabinets, AMIK, MACY, Local Contexts
- Next week follow-up: if no AMIK response is received by Monday, 2026-03-23, send a check-in and confirm whether `ENH-001` stays parked until capacity opens
- Waiting on client: Orbeon Forms, MACY
- Documentation queue: NWAC

## Rest Of Week - 2026-03-18 To 2026-03-20
- Completed on 2026-03-18: Banff response handling for the current Michel Technical Lead feedback was closed in Asana.
- Completed on 2026-03-19: Orbeon historical survey structure and responses were exported to CSV and are now waiting on sharing details before handoff.
- Completed on 2026-03-19: MASC EN feedback review was closed and the follow-on cleanup bundle was captured in the tracker.
- Completed on 2026-03-19: MASC dynamic script evaluation was closed and the next-step capture was logged.
- Completed on 2026-03-19: MASC archive-page category coin updates were completed and deployed to production.
- On 2026-03-20: use a contained 2h block to investigate and fix the known missing values in the MASC calculator.
- On 2026-03-20: pull Local Contexts into today's lane for security-header hardening.
- Next week, work `IFWH` ahead of `Banff` because the IFWH closeout date lands first on 2026-03-27.
- Merge current MASC work to the production site on 2026-03-18.
- Use the remaining execution time this week on routing the new MASC cleanup bundle, plugin-owned items, and content-owned follow-ups after the archive-page work.
- Keep the Banff feedback update on an early internal target even though the formal due date is now 2026-04-03.
- Move the Banff PM-only internal decisions to end-of-next-week, time-permitting review instead of forcing them into today's or early-next-week lane.
- During the week of 2026-03-23, close `IFWH` accessibility work and `NWAC` documentation so both projects can be taken off the active board by Friday, 2026-03-27.
- Flag to content team: provide French translations for the featured thematic crop maps block content on the French `MMPP` page.
- Capture any Banff blockers, especially the `MI_311` DMC SVG asset dependency, the `MI_312` sponsor SVG asset need, and password-protection access, so next week's remediation queue stays accurate.
- Keep the `MI_324` language-toggle dependency visible so the next submission does not reach implementation without approved translated content from PO/content.
- Keep the `MI_330` alt-text reminder visible so content collection closes image metadata gaps before submission.

## Slack Update
Today's PM pass closed the featured thematic crop maps block merge and rollout for MASC, and the block is now added to both the English and French `MMPP` pages. The archive-page category coin update is also complete and deployed to production, and the Orbeon historical survey data export is complete in CSV format with only sharing details left before handoff; today's active execution now includes the contained 2h MASC calculator missing-values fix and the `Local Contexts` security-header hardening pass, while the agency portfolio audit is queued as a 2h review for Wednesday, March 25, 2026, `UA Local 179` has been added as a new 3h maintenance compatibility check for Samsung Galaxy S7 devices, and both `IFWH` and `NWAC` are scheduled for next-week closeout by Friday, March 27, 2026, with `IFWH` explicitly prioritized ahead of `Banff`. Banff PM-only review items are now pushed to the end of next week as time-permitting work because the external Banff feedback date has more room. The main risk is capacity: tracked work sits at 136h against a 40h week, and the cleanup bundle, owner-dependent follow-ups, the cross-portfolio audit, Banff remediation, the new `UA Local 179` maintenance intake, and the `NWAC` documentation framing decisions still need to be sequenced cleanly.
