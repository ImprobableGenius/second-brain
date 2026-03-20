# Local Contexts Project Context

## Snapshot
- Project type: WordPress maintenance / security hardening
- Local repo: Not yet identified in `/Users/aarongilani/Local Sites`
- Hosting context: Flywheel-hosted WordPress site with caching/CDN headers present
- Load: Medium
- Working estimate: 5h total
- Task code prefix: `LCTX`
- Priority: Scheduled today
- Start date: 2026-03-20
- Deadline: 2026-03-20
- Status: Active today

## Current Task
- [ ] LCTX-01 Security-header hardening | Estimate: 5h | Due: 2026-03-20 | Flag: High Uncertainty

## Review Summary
- External review identified WordPress generator visibility and Flywheel hosting indicators.
- Missing headers called out in the review:
  - `Strict-Transport-Security`
  - `Content-Security-Policy`
  - `X-Frame-Options`
  - `Permissions-Policy`
- Headers already present:
  - `X-Content-Type-Options: nosniff`
  - `Referrer-Policy: no-referrer-when-downgrade`
  - `X-XSS-Protection: 1`

## Proposed Fix
- Configure the missing security headers through the hosting admin layer, as indicated in the client email.
- Enable HSTS only after confirming the domain is HTTPS-only and subdomain coverage is safe.
- Start CSP in `Report-Only` mode unless the site has already been audited for all required third-party scripts, fonts, and embeds.
- Use either `frame-ancestors` in CSP or `X-Frame-Options`, depending on whether any legitimate framing use case exists.

## Estimate Breakdown
- Review current hosting/header controls and confirm implementation path in Flywheel admin: 1h
- Configure HSTS, X-Frame-Options or frame controls, and Permissions-Policy: 1h
- Draft and test a baseline CSP rollout plan, likely starting in Report-Only: 2h
- Validate header behavior and document residual risks / next steps: 1h

## PM Risks / Open Questions
- Unknown whether the site uses third-party scripts or embeds that will require CSP allowlisting.
- Unknown whether Vincent Designs already has the required hosting-admin access for the environment in question.
- Local project path has not yet been confirmed in the workspace, so this note is currently based on the email thread rather than repo inspection.

## Scheduling Note
- This project has now been pulled into today's lane for Friday, `2026-03-20`.
- Planning assumption: keep the scope focused on the hosting-layer security-header hardening path unless a broader WordPress app review is explicitly required.

## Email Context
- Client reported that a security firm identified missing hardening headers on the Local Contexts WordPress site.
- Client understanding is that the fixes need to be applied through Vincent Designs in the hosting admin site.
- Requested controls include HSTS, CSP, clickjacking protection, and optional Permissions-Policy hardening.

## Notes
- This project was previously tracked under the generic name `Security`.
