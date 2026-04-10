---
title: "IPAM Architecture"
---

## Technical Snapshot
- Source: `Workload Metrics - Main.csv`
- Project type: Fresh Laravel-based member management system
- Local repo path: `/Users/aarongilani/Dev_Arena/Laravel/ipam`
- Product: Indigenous People's Alliance of Manitoba (IPAM) Membership Application System
- Current branch: `feat/file-upload`
- Remote: `git@github.com:Vincent-Design-Inc/ipam.git`

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
- The public membership experience is now a landing page plus a multi-step application wizard that is being expanded to include a dedicated document-upload step.
- The app already has:
  - landing route and membership application routes
  - membership application controller and step-specific request validation
  - draft/session persistence service and middleware for multi-step progress
  - `MembershipApplication` and `MembershipApplicationChild` models
  - preliminary `Member`, `Upload`, and `UploadAttachment` models
  - migrations for applications and dependent children
  - Nova resources and filters for admin review
  - dedicated views for landing, step 1, step 2, step 3, step 4, and thank-you states
  - an upload component, upload JS module, storage-driver setup, and preliminary upload tests
  - Pest feature coverage for the membership application wizard and landing route
- The project is actively being developed on `feat/file-upload`.

## Current Code Reality
- Public routes now include both the landing page and a multi-step membership application flow in `routes/web.php`.
- `MembershipApplicationController` now handles the wizard flow, request processing, and final submission.
- Validation is no longer just a single request object; the flow now includes:
  - `StoreMembershipApplicationRequest`
  - `StoreMembershipApplicationStep1Request`
  - `StoreMembershipApplicationStep2Request`
  - upload-step validation moving into `StoreMembershipApplicationUploadRequest`
- Draft progress is handled through:
  - `MembershipApplicationDraftService`
  - `MergeMembershipApplicationDraftIntoRequest` middleware
- Validation rules are also centralized in `app/Support/MembershipApplicationRules.php`.
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
  - separate step templates for the application wizard
  - a dedicated step 4 for document upload in the branch diff against `main`
  - a thank-you screen after submission
- Test coverage now goes beyond starter examples:
  - `tests/Feature/MembershipApplicationWizardTest.php`
  - landing-route coverage added in the latest work
  - `tests/Feature/UploadAttachmentTest.php`
  - `tests/Feature/DevFileUploadPreviewTest.php`

## Current Repo State
- Current branch is `feat/file-upload`, tracking `origin/feat/file-upload`
- Current tracked local modifications:
  - `app/Http/Controllers/MembershipApplicationController.php`
  - `app/Http/Requests/StoreMembershipApplicationRequest.php`
  - `resources/views/membership-application/landing.blade.php`
  - `tests/Feature/MembershipApplicationWizardTest.php`
- Current untracked implementation files/directories:
  - `app/Http/Controllers/MembershipApplicationUploadController.php`
  - `app/Nova/Filters/`
  - `app/Nova/MembershipApplication.php`
  - `app/Nova/MembershipApplicationChild.php`
  - `database/factories/MembershipApplicationFactory.php`
  - `database/factories/MembershipApplicationChildFactory.php`
  - `database/seeders/MembershipApplicationSeeder.php`
  - `project_details/`
  - `resources/views/partials/`
- This means the branch is beyond pure committed progress and is now in active local integration work for the upload step and admin/data-model follow-through.
- Current active branch work is concentrated around the document-upload milestone rather than the earlier landing-only branch.

## Source Of Truth
- Project overview: `/Users/aarongilani/Dev_Arena/Laravel/ipam/project_management/PROJECT_OVERVIEW.md`
- PM docs folder: `/Users/aarongilani/Dev_Arena/Laravel/ipam/project_management`
- Requirement reference: `/Users/aarongilani/Dev_Arena/Laravel/ipam/project_details/IPAM Application one page Jan 2 2026.pdf`
- Note: the PM docs are present but still mostly scaffolded, so the codebase is currently a better signal of actual progress than the backlog files.

## Useful Starting Points
- Public flow: `routes/web.php`, `app/Http/Controllers/MembershipApplicationController.php`
- Validation: `app/Http/Requests/StoreMembershipApplicationRequest.php`, `app/Http/Requests/StoreMembershipApplicationStep1Request.php`, `app/Http/Requests/StoreMembershipApplicationStep2Request.php`, `app/Http/Requests/StoreMembershipApplicationUploadRequest.php`
- Draft persistence: `app/Services/MembershipApplicationDraftService.php`, `app/Http/Middleware/MergeMembershipApplicationDraftIntoRequest.php`
- Domain models: `app/Models/MembershipApplication.php`, `app/Models/MembershipApplicationChild.php`, `app/Models/Member.php`, `app/Models/Upload.php`, `app/Models/UploadAttachment.php`
- Database shape: `database/migrations/*membership_application*`
- Upload path: `resources/views/components/file-upload.blade.php`, `resources/js/file-upload.js`, `app/Models/Concerns/HasUploadAttachments.php`
- Upload controller path: `app/Http/Controllers/MembershipApplicationUploadController.php`
- Admin workflow: `app/Nova/MembershipApplication.php`, `app/Nova/MembershipApplicationChild.php`
- Frontend behavior: `resources/views/membership-application/landing.blade.php`, `resources/views/membership-application/layout.blade.php`, `resources/views/membership-application/step-1.blade.php`, `resources/views/membership-application/step-2.blade.php`, `resources/views/membership-application/step-3.blade.php`, `resources/views/membership-application/step-4.blade.php`, `resources/views/membership-application/thank-you.blade.php`, `resources/js/app.js`

## PM Notes
- IPAM is an active build, not a maintenance project.
- The project is now past simple form scaffolding: there is a real landing experience, a multi-step application wizard, submission flow, and first-pass admin/data structures.
- The current PM focus is no longer “build the application form” but “finish the milestone chain from document upload through admin tools, export/payment handling, and staging readiness”.
- Near-term execution should stay split across three lanes:
  - schema / applicant-flow stabilization
  - document-upload completion and integration into the real application flow
  - admin/export/staging completion work
- The main scheduling risk is no longer basic form creation; it is the amount of still-pending finish work between upload, admin review, export/payment handling, and staging by `2026-04-15`.
