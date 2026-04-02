---
title: "Orbeon Forms Project Context"
---

# Orbeon Forms Project Context

## Project Snapshot
- Source: `Workload Metrics - Main.csv`
- Project type: Orbeon Form Runner support work in Java
- Working estimate: 4h remaining open work
- Task code prefix: `ORBF`
- Priority: Low
- Load: Low
- Start date: TBD
- Deadline: TBD
- Status: Mixed - legacy extraction complete, form build waiting on client

## Current State
- The new form build is still blocked until the client provides the fields required for the form
- The same-day legacy request to locate and extract the former survey and historical responses is now complete
- No implementation start date should be committed for the new form until the field list is received
- Login access to the current Orbeon system is confirmed as of `2026-03-19`
- Current constraint confirmed on `2026-03-19`: the site is running Orbeon Community Edition, so direct export from the admin UI is not available
- The former survey structure and historical responses were successfully exported to CSV on `2026-03-19`
- The exported CSV is now awaiting sharing information before handoff
- Repo note: the GitLab repository is stale and would need to be moved to GitHub, but that is a separate maintenance task from the immediate survey-data extraction request

## Completed Today
- [x] Investigate and extract the former survey structure and historical responses | Completed: `2026-03-19`
- Output delivered: CSV export of the historical survey data
- Current handoff note: awaiting sharing information before the dataset is delivered onward
- Original estimate: `3h`
- Delivery assumption used: this was a discovery-and-extraction pass, not a full analysis or reporting engagement

## Export Script Documentation
- Export method: PostgreSQL `\copy`
- Source table: `orbeon_form_data`
- Filter used:
  - `app = 'knk'`
  - `form = 'Inclusion-Criteria'`
- Output file: `~/orbeon_export.csv`
- Purpose: extract selected survey fields from the XML payload into a flat CSV for sharing and downstream analysis

```sql
\copy (SELECT
    document_id AS "System ID",
    created AS "Submission Date",
    (xpath('//coupon-number/text()', xml::xml))[1]::text AS "1. Coupon #",
    (xpath('//first-name/text()', xml::xml))[1]::text AS "2. First Name",
    (xpath('//last-name/text()', xml::xml))[1]::text AS "Last Name",
    (xpath('//people-you-know/text()', xml::xml))[1]::text AS "11. Indigenous People Known",
    (xpath('//relationship-to-coupon/text()', xml::xml))[1]::text AS "12. Relationship",
    (xpath('//gender/text()', xml::xml))[1]::text AS "14. Gender",
    (xpath('//control-33/text()', xml::xml))[1]::text AS "15. Transgender?",
    (xpath('//were-you-apart-of/text()', xml::xml))[1]::text AS "16. Residential School etc",
    (xpath('//tested-for-sti/text()', xml::xml))[1]::text AS "25. Tested STBBI?",
    (xpath('//control-35/text()', xml::xml))[1]::text AS "26. Tested Syphilis?",
    (xpath('//tested-for-hiv-aids/text()', xml::xml))[1]::text AS "27. Tested HIV?",
    (xpath('//tested-for-hepatitis-c/text()', xml::xml))[1]::text AS "28. Tested Hep C?",
    (xpath('//experience-with-these-services/text()', xml::xml))[1]::text AS "32. Experience Rating",
    (xpath('//sexual-wellness-lodge/text()', xml::xml))[1]::text AS "38. Accessed Lodge Before?",
    (xpath('//control-24/text()', xml::xml))[1]::text AS "Notes",
    (xpath('//control-22/text()', xml::xml))[1]::text AS "Interviewer"
FROM orbeon_form_data
WHERE app = 'knk'
  AND form = 'Inclusion-Criteria'
ORDER BY created DESC) TO '~/orbeon_export.csv' WITH CSV HEADER;
```

## Expected Work
- Open task: `ORBF-01` Await client fields + finalize scope
- Build or configure a form using the Orbeon Form Runner library
- Translate the client-provided field list into the final form structure
- Validate the final field set before implementation starts

## PM Notes
- Primary blockers are now split:
  - form build blocker: missing client field input
  - handoff blocker: the legacy survey CSV is ready, but sharing details still need to be confirmed
- Priority remains low until the client delivers the field requirements
- Once fields arrive, confirm whether the 4h estimate is still valid or whether validation, conditional logic, integrations, or approvals increase scope
- The extraction request was completed on `2026-03-19`, and the resulting dataset is now waiting on delivery details
- The GitLab-to-GitHub move should be treated as a separate repo-maintenance item unless repository access is directly required to find database configuration or storage details for the extraction
