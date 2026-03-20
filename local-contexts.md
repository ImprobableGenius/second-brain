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
- Status: Complete

## Current Task
- [x] LCTX-01 Security-header hardening | Completed: 2026-03-20

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

## CSP Implementation Guidance
- Flywheel confirmed that CSP source discovery and policy setup is effectively a developer-owned task because the allowlist must match the site's real third-party dependencies.
- Their suggested workflow for `LCTX-01`:
  - use the [HTTP Headers plugin](https://wordpress.org/plugins/http-headers/) if needed to manage CSP from WordPress/PHP side
  - confirm the plugin can locate the `.user.ini` file on the hosting platform
  - start with CSP enabled in `Report-Only` mode
  - begin with `default-src 'self'`
  - visit the site, inspect the browser console, and collect every blocked source that needs to be explicitly allowed
  - repeat until the console no longer reports missing sources
  - only then switch from `Report-Only` to enforcement mode
- Practical example they called out: if the site loads Google Fonts, the policy would need to explicitly allow sources like `fonts.gstatic.com`.
- Reference: [Scott Helme CSP introduction](https://scotthelme.co.uk/content-security-policy-an-introduction/)

## Hosting Guidance Note
- Flywheel flagged that HSTS is typically set to a one-year expiration by default.
- Practical impact: once a visitor sees the HSTS header, their browser will force HTTPS for that domain for the duration of the policy. If SSL is removed during that period, repeat visitors may need to manually clear browser cache or HSTS state before the site will load over HTTP again.
- Additional caution: if the domain has been manually submitted to Chrome's HSTS preload list, rolling back to HTTP becomes much harder. This is only a risk if the domain was intentionally submitted.
- Reference: [Chrome HSTS preload information](https://opensource.google/projects/hstspreload)
- Flywheel alternative: the `Force HTTPS` option in the Flywheel dashboard advanced tab provides a similar redirect outcome on the server side, but is less strict than browser-enforced HSTS.
- Planning takeaway for `LCTX-01`: treat HSTS as a decision with rollback implications, not just a default toggle.

## Estimate Breakdown
- Review current hosting/header controls and confirm implementation path in Flywheel admin: 1h
- Configure HSTS, X-Frame-Options or frame controls, and Permissions-Policy: 1h
- Draft and test a baseline CSP rollout plan, likely starting in Report-Only: 2h
- Validate header behavior and document residual risks / next steps: 1h

## PM Risks / Open Questions
- Unknown whether the site uses third-party scripts or embeds that will require CSP allowlisting.
- Unknown whether Vincent Designs already has the required hosting-admin access for the environment in question.
- Local project path has not yet been confirmed in the workspace, so this note is currently based on the email thread rather than repo inspection.
- Need a deliberate decision on whether to enable strict HSTS or use Flywheel `Force HTTPS` instead, given the browser-side persistence risk.
- CSP setup may take longer than a simple header toggle because the site-specific source inventory has to be discovered and validated iteratively.

## Scheduling Note
- This project has now been pulled into today's lane for Friday, `2026-03-20`.
- Planning assumption: keep the scope focused on the hosting-layer security-header hardening path unless a broader WordPress app review is explicitly required.
- Completion note: Local Contexts updates were completed on `2026-03-20`, and a follow-up was sent after the work was finished.

## Email Context
- Client reported that a security firm identified missing hardening headers on the Local Contexts WordPress site.
- Client understanding is that the fixes need to be applied through Vincent Designs in the hosting admin site.
- Requested controls include HSTS, CSP, clickjacking protection, and optional Permissions-Policy hardening.
- Hosting follow-up context:
  - HSTS on Flywheel defaults to a one-year browser-enforced duration
  - removing SSL during that period can create access issues for repeat visitors unless browser state is cleared
  - HSTS preload is only relevant if the domain was manually submitted
  - Flywheel suggested `Force HTTPS` as a less strict server-side alternative
  - Flywheel also advised that CSP setup is developer-managed, should start in `Report-Only`, and may be easiest to manage through the HTTP Headers plugin if needed

## Notes
- This project was previously tracked under the generic name `Security`.
