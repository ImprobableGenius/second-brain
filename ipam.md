---
title: "IPAM Project Context"
---

# IPAM Project Context

## Project Snapshot
- Source: `Workload Metrics - Main.csv`
- Project type: Fresh Laravel-based member management system
- Local repo path: `/Users/aarongilani/Dev_Arena/Laravel/ipam`
- Product: Indigenous People's Alliance of Manitoba (IPAM) Membership Application System
- Current branch: `feat/landing`
- Remote: `git@github.com:Vincent-Design-Inc/ipam.git`
- Priority: High
- Load: High
- Working estimate: 20h total remaining
- Task code prefix: `IPAM`
- Start date: 2026-03-16
- Deadline: 2026-04-15
- Status: In Progress
- Priority note on `2026-04-02`: IPAM has been bumped up in the active priority chain because the working target is now mid-April rather than late April.

## Stack
- PHP 8.2+
- Laravel 12
- Laravel Nova 5
- PostgreSQL
- Tailwind CSS v4
- Vite
- Pest
- Docker / Laravel Sail

## Project Goal
- Replace the paper-based IPAM membership application with a digital workflow
- Public application form for applicants
- Child/dependent capture
- Nova admin for internal review and status management
- Membership application records that can be reviewed, filtered, and updated

## Current State
- The public membership experience is now a landing page plus a three-step application wizard with a thank-you screen
- The app already has:
  - landing route and membership application routes
  - membership application controller and step-specific request validation
  - draft/session persistence service and middleware for multi-step progress
  - `MembershipApplication` and `MembershipApplicationChild` models
  - migrations for applications and dependent children
  - Nova resources and filters for admin review
  - dedicated views for landing, step 1, step 2, step 3, and thank-you states
  - Pest feature coverage for the membership application wizard and landing route
- The project is actively being developed on a dirty `feat/landing` branch

## Current Delivery Tasks
- [ ] IPAM-01 Member object modeling | Estimate: 12h
- [ ] IPAM-02 Membership frontend refinement | Estimate: 8h
- Estimate assumption: current work is finishing and correcting the first pass, not building a full multi-role membership platform from scratch
- Estimate risk: add 6h to 10h if “member objects” expands beyond application records into approved-member lifecycle, renewals, payments, or document uploads

## Current Code Reality
- Public routes now include both the landing page and a multi-step membership application flow in `routes/web.php`
- `MembershipApplicationController` now handles the wizard flow, request processing, and final submission
- Validation is no longer just a single request object; it now includes:
  - `StoreMembershipApplicationRequest`
  - `StoreMembershipApplicationStep1Request`
  - `StoreMembershipApplicationStep2Request`
  - `StoreMembershipApplicationStep3Request`
- Draft progress is handled through:
  - `MembershipApplicationDraftService`
  - `MergeMembershipApplicationDraftIntoRequest` middleware
- Validation rules are also centralized in `app/Support/MembershipApplicationRules.php`
- The current domain model centers on:
  - `MembershipApplication`
  - `MembershipApplicationChild`
- Nova resources already exist for:
  - `MembershipApplication`
  - `MembershipApplicationChild`
  - status/member type/aboriginal status filters
- The frontend now includes:
  - a dedicated landing page
  - a shared application layout
  - separate step templates for the three-step wizard
  - a thank-you screen after submission
- Test coverage now goes beyond starter examples:
  - `tests/Feature/MembershipApplicationWizardTest.php`
  - landing-route coverage added in the latest work

## PM Read On Remaining Work
- The backend/domain work is still the bigger unknown, but the application workflow itself is now materially built rather than just scaffolded
- “Member objects need to be modeled and updated” now reads more like refinement of the application-to-member lifecycle, not greenfield application intake work
- The frontend exists in a meaningful first pass and now needs refinement, IA cleanup, and likely responsive polish rather than first-time assembly
- Test coverage is no longer empty, but it is still narrow and should be expanded as the domain model settles

## Current Repo State
- Current branch is `feat/landing`, tracking `origin/feat/landing`
- There are no tracked local modifications at the moment
- The current repo state is clean apart from untracked implementation files:
  - `app/Nova/Filters/`
  - `app/Nova/MembershipApplication.php`
  - `app/Nova/MembershipApplicationChild.php`
  - `database/factories/MembershipApplicationFactory.php`
  - `database/factories/MembershipApplicationChildFactory.php`
  - `database/seeders/MembershipApplicationSeeder.php`
  - `project_details/`
- This means the current branch activity is largely committed, with a remaining untracked admin/data-model layer still to be formalized in git
- Commit history for today shows the repo is already into a real first-pass implementation of the landing experience and membership wizard, not just scaffolding

## Progress Log

### 2026-04-06
- Active branch checked: `feat/landing`
- Today branch activity landed as a concentrated implementation burst across the public landing and membership application flow.
- Main work areas visible in today's commits:
  - landing route and preliminary landing-page design
  - multi-step form layout and thank-you flow
  - membership form validation and request handling
  - draft/session persistence middleware and service wiring
  - membership application model, child model, and migration setup
  - test coverage for the base landing route and multi-step form behavior
  - design-system setup to match the current IPAM brand guide
- Today's commit log:
  - `d05e53a` landing page prelimnary scrible design
  - `6975a26` update testing to include base landing route
  - `ac4825a` include landing page route
  - `d372fae` migration scripts for membership application table
  - `ced63ed` create seperate model for children attached to membership application
  - `988ad81` register membership application model
  - `3d16285` controller to handle membership form requests
  - `f680928` Merge pull request #1 from Vincent-Design-Inc/feat/multi-step-form
  - `af57f0d` use ipam image in the final card
  - `1f34d0d` update routes for the multistep form
  - `6caaecc` register mermbership draf middleware
  - `60cc9de` set-up design system to match current IPAM brand guide - taken from their existing website
  - `968c3c3` use in memory sqlite db for testing
  - `69ea782` unit tests for multi step form methods and resources
  - `cc36e49` build a middleware to inject draftService at construction
  - `cd0303d` build a service to store application progress as session data without relying on user authentication
  - `b5e4beb` updated step3 request validation with block comments
  - `3441f5a` Membersip form request handler, we validate each step of the form by type hinting data across requests posted to same controller
  - `85090d3` final thank you screen once the user has submitted their application
  - `cf334ff` break form into three steps
  - `0baede7` base layout for multistep form
  - `93260f3` membership form validation rules

## PM Risks
- Domain model may still be incomplete or too close to the paper form rather than the final admin workflow
- Frontend refinement can sprawl if requirements shift from “polish” to “redesign”
- Nova/admin review workflow may need additional fields or statuses once the data model settles
- Meaningful tests are not in place yet, which increases regression risk as the model evolves

## Source Of Truth
- Project overview: `/Users/aarongilani/Dev_Arena/Laravel/ipam/project_management/PROJECT_OVERVIEW.md`
- PM docs folder: `/Users/aarongilani/Dev_Arena/Laravel/ipam/project_management`
- Requirement reference: `/Users/aarongilani/Dev_Arena/Laravel/ipam/project_details/IPAM Application one page Jan 2 2026.pdf`
- Note: the PM docs are present but still mostly scaffolded, so the codebase is currently a better signal of actual progress than the backlog files

## Useful Starting Points
- Public flow: `routes/web.php`, `app/Http/Controllers/MembershipApplicationController.php`
- Validation: `app/Http/Requests/StoreMembershipApplicationRequest.php`, `app/Http/Requests/StoreMembershipApplicationStep1Request.php`, `app/Http/Requests/StoreMembershipApplicationStep2Request.php`, `app/Http/Requests/StoreMembershipApplicationStep3Request.php`
- Draft persistence: `app/Services/MembershipApplicationDraftService.php`, `app/Http/Middleware/MergeMembershipApplicationDraftIntoRequest.php`
- Domain models: `app/Models/MembershipApplication.php`, `app/Models/MembershipApplicationChild.php`
- Database shape: `database/migrations/*membership_application*`
- Admin workflow: `app/Nova/MembershipApplication.php`, `app/Nova/MembershipApplicationChild.php`
- Frontend behavior: `resources/views/membership-application/landing.blade.php`, `resources/views/membership-application/layout.blade.php`, `resources/views/membership-application/step-1.blade.php`, `resources/views/membership-application/step-2.blade.php`, `resources/views/membership-application/step-3.blade.php`, `resources/views/membership-application/thank-you.blade.php`, `resources/js/app.js`

## PM Notes
- IPAM is an active build, not a maintenance project
- The project is now past simple form scaffolding: there is a real landing experience, a three-step application wizard, submission flow, and first-pass admin/data structures
- The current PM focus is no longer “build the application form” but “stabilize the domain model, formalize the admin layer, and refine the public experience into a production-ready flow”
- Near-term execution should stay split across three lanes:
  - member-object and application-model refinement
  - frontend/UX refinement for the landing and wizard flow
  - admin/Nova formalization and cleanup of the remaining untracked data-model files
- The main scheduling risk is that IPAM can sprawl from a bounded application system into a broader membership-platform rewrite if the approved-member lifecycle is not clearly scoped
