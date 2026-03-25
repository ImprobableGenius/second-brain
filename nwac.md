# NWAC Project Context

## Snapshot
- Project type: WordPress custom Gravity Forms site
- Local repo: `/Users/aarongilani/Local Sites/nwac/app/public/wp-content/themes/NWAC`
- Repo remote: `git@github.com:Vincent-Design-Inc/NWAC.git`
- Active branch: `main`
- Load: Medium
- Working estimate: 10h total
- Task code prefix: `NWAC`
- Priority: Low
- Start date: TBD
- Deadline: 2026-03-27
- Audience: client handoff
- Status: Next Week Closeout

## Current Task
- [ ] NWAC-01 Final documentation + compliance research | Estimate: 10h | Status: On Track | Due: 2026-03-27 | Flag: High Uncertainty

## Platform Notes
- Custom WordPress theme based on Genesis Block Theme with project-specific edits in `functions.php`.
- Gravity Forms is the core application surface, with installed add-ons including `gravityforms`, `gravityformssignature`, `gravityformssurvey`, `gravity-pdf`, and `gravity-forms-encrypted-fields`.
- The current worktree is dirty in `functions.php`, which is also where the compliance-sensitive upload logic lives.

## Compliance-Relevant Implementation Notes
- The theme registers a `gform_submission_files_pre_save_field_value` hook intended to encrypt uploaded files before they are stored.
- The theme also registers a `gform_file_path_pre_download` hook intended to decrypt files when they are downloaded.
- The current upload-encryption path includes active `var_dump($files); die();` debug output and hardcoded AES key material, so the final documentation should not present secure upload handling as production-ready until that behavior is verified.
- There do not appear to be project-specific documentation or policy files in the theme, so the final handoff will likely need to be authored from the current implementation rather than updated from an existing doc set.

## Research Tracks
- Document how the site handles sensitive Gravity Forms data across collection, consent, upload, storage, download, export, and retention.
- Validate the documentation against current PIPEDA principles for accountability, consent, safeguards, openness, and retention/breach handling.
- Confirm which Indigenous data governance framework the client expects the final documentation to reference; CARE is a broad baseline, but client-specific governance requirements may be narrower or more specific.

## Estimate Breakdown
- Audit Gravity Forms workflow and compliance-relevant code paths: 3h
- Research and map documentation requirements against PIPEDA and Indigenous data governance guidance: 3h
- Draft and finalize the documentation package with open risks and admin notes: 4h

## PM Risks / Open Questions
- Unknown whether the final document should assert compliance, or document implemented controls plus unresolved gaps.
- Need confirmation on which Indigenous data governance framework the client wants cited in the documentation.

## Scheduling Note
- This project is now targeted for closure during the week of `2026-03-23`, with completion due by Friday, `2026-03-27`.
- Planning assumption: if audience or compliance-framing decisions remain unresolved, the documentation should still be pushed to a closeout-ready draft rather than left unscheduled.
- Protection note on `2026-03-25`: `NWAC-01` must be pushed through this week so the week of `2026-03-30` can be protected for Banff execution.

## Source Links
- [PIPEDA fair information principles](https://www.priv.gc.ca/en/privacy-topics/privacy-laws-in-canada/the-personal-information-protection-and-electronic-documents-act-pipeda/p_principle/)
- [PIPEDA consent guidance](https://www.priv.gc.ca/en/privacy-topics/privacy-laws-in-canada/the-personal-information-protection-and-electronic-documents-act-pipeda/p_principle/principles/p_consent/?wbdisable=true)
- [PIPEDA safeguards guidance](https://www.priv.gc.ca/en/privacy-topics/privacy-laws-in-canada/the-personal-information-protection-and-electronic-documents-act-pipeda/p_principle/principles/p_safeguards/?wbdisable=true)
- [CARE Principles for Indigenous Data Governance](https://www.gida-global.org/care)

## Notes
- Original project shell came from `Workload Metrics - Main.csv`.
