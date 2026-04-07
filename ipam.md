---
title: "IPAM Project Context"
---

- Last updated: `2026-04-07`

## Project Snapshot
- Source: `Workload Metrics - Main.csv`
- Project type: Fresh Laravel-based member management system
- Local repo path: `/Users/aarongilani/Dev_Arena/Laravel/ipam`
- Product: Indigenous People's Alliance of Manitoba (IPAM) Membership Application System
- Current branch: `feat/file-upload`
- Remote: `git@github.com:Vincent-Design-Inc/ipam.git`
- Priority: High
- Load: High
- Working estimate: 42h total remaining
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
  - preliminary `Member`, `Upload`, and `UploadAttachment` models
  - migrations for applications and dependent children
  - Nova resources and filters for admin review
  - dedicated views for landing, step 1, step 2, step 3, and thank-you states
  - an upload component, upload JS module, storage-driver setup, and preliminary upload tests
  - Pest feature coverage for the membership application wizard and landing route
- The project is actively being developed on `feat/file-upload`

## Current Delivery Tasks
- [ ] IPAM-01 DEV-02 Core database schema + member objects | Remaining estimate: 4h | Status: Behind | Original target: 2026-03-06
- [ ] IPAM-02 DEV-03 V1 applicant form + frontend refinement | Remaining estimate: 6h | Status: Behind | Original target: 2026-03-13
- [ ] IPAM-03 DEV-04 Document upload implementation | Remaining estimate: 8h | Status: Behind | Original target: 2026-03-20
- [ ] IPAM-04 DEV-06 Complete admin review tools | Remaining estimate: 8h | Status: Behind | Original target: 2026-04-03
- [ ] IPAM-05 DEV-07 Export and payment marker | Remaining estimate: 6h | Status: On Track | Target: 2026-04-10
- [ ] IPAM-06 DEV-08 Complete staging site | Remaining estimate: 10h | Status: On Track | Target: 2026-04-15
- Scope note: this now reflects the full milestone chain visible in the current completion plan rather than only the earlier modeling/frontend placeholder tasks.
- Estimate assumption: DEV-02 and DEV-03 are materially built already, DEV-04 is actively underway, and DEV-06 through DEV-08 still require significant completion work.
- Estimate risk: add 8h to 12h if admin review expands into approved-member lifecycle automation, if document upload requires production-grade storage/policy hardening, or if staging includes a full UAT/fix cycle rather than a simple deployment-ready handoff.

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
  - `Member`
  - `Upload`
  - `UploadAttachment`
- Upload support is now partially implemented through:
  - `HasUploadAttachments`
  - file-upload component/view work
  - upload JS
  - Spaces / S3 driver configuration
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
  - `tests/Feature/UploadAttachmentTest.php`
  - `tests/Feature/DevFileUploadPreviewTest.php`

## PM Read On Remaining Work
- The backend/domain work is still the bigger unknown, but the application workflow itself is now materially built rather than just scaffolded
- DEV-02 and DEV-03 are no longer greenfield; they are cleanup, integration, and stabilization work
- DEV-04 is in active implementation now and is the clearest signal of current branch momentum
- DEV-06 through DEV-08 remain the biggest schedule risk because the repo shows only early admin structures and no visible export/staging-completion layer yet
- Test coverage is no longer empty, but it is still narrow relative to the expanded upload and admin scope

## Current Repo State
- Current branch is `feat/file-upload`, tracking `origin/feat/file-upload`
- There are no tracked local modifications at the moment
- The current repo state is clean apart from untracked implementation files:
  - `app/Nova/Filters/`
  - `app/Nova/MembershipApplication.php`
  - `app/Nova/MembershipApplicationChild.php`
  - `database/factories/MembershipApplicationFactory.php`
  - `database/factories/MembershipApplicationChildFactory.php`
  - `database/seeders/MembershipApplicationSeeder.php`
  - `project_details/`
  - `resources/views/partials/`
- This means the current branch activity is largely committed, with a remaining untracked admin/data-model layer still to be formalized in git
- Current active branch work is concentrated around the document-upload milestone rather than the earlier landing-only branch

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

### 2026-04-07
- Active branch checked: `feat/file-upload`
- Today branch activity is concentrated around DEV-04 document upload implementation.
- Main work areas visible in today's commits:
  - Spaces / S3 storage setup
  - file-upload component and JS module
  - upload, upload attachment, and member models
  - upload-related migrations and factories
  - polymorphic upload relationship wiring
  - preliminary upload tests
- Today's commit log:
  - `44e42c2` update agents context, using newer version of PHP
  - `f6c59b7` perlimnary tests for upload pattern
  - `035a3e6` basic upload and upload attachment factories to run pest tests
  - `a23a6b5` register upload pattern on boot
  - `3b6940e` build a UploadAttachment concern to allows traits on existing models, which would enable modles to participating the upload pattern
  - `71fb37d` init upload attachment model to morph uploads and match them to their respective models
  - `ab4c7fb` build uploads model and establish one to one relationship with attachments
  - `48d4aa6` define isomorphic relationship for membership application model
  - `d7610c7` migrations for upload and upload_attachment tables
  - `75a2735` prelimnary member model to define isomophic upload relationships
  - `ad6a4ea` file upload js module
  - `1f21756` file upload component preview for development and testing environment only
  - `62cfb94` file upload component
  - `824f495` install aws s3 storage drivers
  - `99d35a1` init spaces storage connection

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
- Domain models: `app/Models/MembershipApplication.php`, `app/Models/MembershipApplicationChild.php`, `app/Models/Member.php`, `app/Models/Upload.php`, `app/Models/UploadAttachment.php`
- Database shape: `database/migrations/*membership_application*`
- Upload path: `resources/views/components/file-upload.blade.php`, `resources/js/file-upload.js`, `app/Models/Concerns/HasUploadAttachments.php`
- Admin workflow: `app/Nova/MembershipApplication.php`, `app/Nova/MembershipApplicationChild.php`
- Frontend behavior: `resources/views/membership-application/landing.blade.php`, `resources/views/membership-application/layout.blade.php`, `resources/views/membership-application/step-1.blade.php`, `resources/views/membership-application/step-2.blade.php`, `resources/views/membership-application/step-3.blade.php`, `resources/views/membership-application/thank-you.blade.php`, `resources/js/app.js`

## PM Notes
- IPAM is an active build, not a maintenance project
- The project is now past simple form scaffolding: there is a real landing experience, a three-step application wizard, submission flow, and first-pass admin/data structures
- The current PM focus is no longer “build the application form” but “finish the milestone chain from document upload through admin tools, export/payment handling, and staging readiness”
- Near-term execution should stay split across three lanes:
  - schema / applicant-flow stabilization
  - document-upload completion and integration into the real application flow
  - admin/export/staging completion work
- The main scheduling risk is no longer basic form creation; it is the amount of still-pending finish work between upload, admin review, export/payment handling, and staging by `2026-04-15`
