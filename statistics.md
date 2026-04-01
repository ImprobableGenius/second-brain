# Productivity Statistics

## Purpose
- Track day-on-day productivity using the same estimate-based task system already used in the portfolio.
- Keep the score adaptive by comparing each day against a rolling baseline instead of a fixed target.
- Separate delivery output from scope growth so busy days with heavy intake do not get mistaken for high delivery.

## Tracking Basis
- This model uses task estimates from the portfolio, not clocked timesheet hours.
- `Shipped h`: estimate hours on implementation or deployment tasks fully completed that day.
- `Response h`: estimate hours on review, comment, PM, QA-response, or admin tasks fully completed that day.
- `Progress h`: estimate hours of meaningful progress on unfinished tasks that moved materially forward that day.
- `New Scope h`: estimate hours added to the queue that day.
- `Blocked h`: estimate hours explicitly blocked by missing access, client input, assets, or approvals.

## Adaptive Metric
- `Weighted Output = Shipped h + (0.7 x Response h) + (0.5 x Progress h)`
- `Rolling Baseline = median of the prior 5 logged workdays' Weighted Output`
- If fewer than 5 prior workdays exist, use all prior logged workdays.
- If no prior workdays exist, set the baseline equal to the current day's Weighted Output and set the index to `100`.
- `Adaptive Productivity Index (API) = round(100 x Weighted Output / Rolling Baseline)`
- `Day Delta % = round(100 x (Weighted Output - Previous Day Weighted Output) / Previous Day Weighted Output)`
- `Scope Pressure % = round(100 x New Scope h / max(Weighted Output, 1))`

## Reading The Metric
- `API = 100`: on baseline for the current rolling period.
- `API > 100`: above recent baseline.
- `API < 100`: below recent baseline.
- `Scope Pressure > 100%`: more estimated work entered the system than was output that day.
- A low-output day is not necessarily a bad day if response or unblock work was the priority; that should be logged in `Response h`.

## Update Rules
- Log one row per workday at the end of the day.
- Count a task in `Shipped h` or `Response h` only when it is fully closed for the day.
- Use `Progress h` only for meaningful movement on open work; do not carry the same progress twice across multiple days without new movement.
- Keep notes short and factual: one delivery driver and one constraint or blocker.
- Do not backfill historical scope churn unless it is explicitly confirmed; use conservative seed data instead.

## Daily Log
| Date | Shipped h | Response h | Progress h | New Scope h | Blocked h | Weighted Output | Rolling Baseline | API | Day Delta % | Scope Pressure % | Notes |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | --- |
| 2026-03-17 | 4.0 | 0.0 | 0.0 | 0.0 | 0.0 | 4.0 | 4.0 | 100 | n/a | 0 | Seed row from confirmed MASC thematic crop maps archive completion; historical scope additions before statistics tracking are intentionally excluded. |
| 2026-03-18 | 11.0 | 4.0 | 0.0 | 26.0 | 0.0 | 13.8 | 4.0 | 345 | 245 | 188 | MASC delivery drove the day with homepage responsiveness and the featured maps block closed; scope pressure stayed high as Banff internal discussion items, a new EN feedback review, and new MASC regression/calculator tasks were added to the queue. |
| 2026-03-19 | 7.0 | 2.0 | 0.0 | 6.0 | 0.0 | 8.4 | 8.9 | 94 | -39 | 71 | MASC archive-page category coin deployment and the Orbeon CSV export drove delivery; the main constraint was new MASC cleanup scope opened by the EN feedback pass, though scope pressure fell well below the prior day. |
| 2026-03-20 | 7.0 | 1.0 | 1.0 | 10.0 | 1.0 | 8.2 | 8.4 | 98 | -2 | 122 | Local Contexts hardening and the MASC calculator fix drove delivery; `MASC-02` stayed open at end of day as scope and ownership questions kept the cleanup bundle from closing. |
| 2026-03-23 | 6.0 | 1.0 | 0.0 | 59.0 | 0.0 | 6.7 | 8.3 | 81 | -18 | 881 | `LFMP-01` and `MASC-06` drove delivery, with the Monday internal sync closing cleanly as coordination work; the main pressure was the large `MASC-07` staging-feedback backlog entering the system the same day. |
| 2026-03-24 | 10.5 | 1.0 | 4.0 | 8.0 | 1.0 | 13.2 | 8.2 | 161 | 97 | 61 | `MASC-02` and `MASC-D01` drove delivery, with `MASC-09` closed as a contained response item; the main constraint was that `MASC-D02` stopped just short of completion with two team-discussion blockers carried to the next day. |
| 2026-03-25 | 2.0 | 3.5 | 0.0 | 7.0 | 6.0 | 4.5 | 8.4 | 53 | -66 | 157 | `MASC-14`, `MASC-10`, `MASC-05`, and `IDE-01` closed, but the day skewed response-heavy; the main blocker was `MASC-08` and `MASC-11` moving into blocked status on design and client input. |
| 2026-03-26 | 2.0 | 7.0 | 0.0 | 1.0 | 5.0 | 6.9 | 8.2 | 84 | 53 | 14 | `MASC-03`, `MASC-11`, and `MASC-15` drove the day, with the MASC sync clarifying the next remediation lane; the main blocker was `MASC-08` still waiting on design and client input plus missing access to the newer dataset files. |
| 2026-03-27 | 5.0 | 0.0 | 0.0 | 0.0 | 5.0 | 5.0 | 6.9 | 72 | -28 | 0 | `MACY-01` drove the day as the main closed delivery item; the main constraint was that `IFWH-01`, `NWAC-01`, and the blocked MASC lane remained open going into Monday. |
| 2026-03-30 | 0.0 | 2.0 | 2.0 | 0.0 | 0.0 | 2.4 | 6.7 | 36 | -52 | 0 | Alex responsiveness check-in and other internal coordination made this a response-heavy day; the main delivery movement was progress on `IFWH-01`, but it did not fully close. |
| 2026-03-31 | 5.0 | 2.0 | 0.0 | 0.0 | 0.0 | 6.4 | 5.0 | 128 | 167 | 0 | `IFWH-01` technical remediation drove the day as the main closed delivery item, with a `2h` MASC dynamic scripting response block and a small Corn Insurance factsheet fix also handled; no new scope entered the system. |

## Rolling Notes
- Start conservative. The first 5 logged workdays will be noisy because the baseline window is still small.
- Once 10 or more workdays are logged, the API becomes a more reliable trend signal for comparing delivery rhythm and scope pressure over time.
