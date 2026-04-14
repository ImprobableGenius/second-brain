---
title: "IPAM Board"
---

- Last updated: `2026-04-14`

## Project Snapshot
- Load: High
- Working estimate: 42h total remaining
- Task code prefix: `IPAM`
- Priority: High
- Start date: 2026-03-16
- Deadline: Client demo ready by `2026-04-15`; production-ready work deferred to week of `2026-04-20`
- Status: In Progress
- Current branch: `feat/file-upload`
- Priority note on `2026-04-02`: IPAM has been bumped up in the active priority chain because the working target is now mid-April rather than late April.
- Scheduling note on `2026-04-14`: the current build is considered ready for client demo. Remaining open IPAM work should now be treated as production-readiness scope and pushed to the week of `2026-04-20` instead of consuming the current day.

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
- Execution note on `2026-04-14`: all remaining open tasks are now treated as next-week production-ready scope rather than blockers to the current client demo state.

## PM Read On Remaining Work
- The current application state is acceptable for a client demo, but it is not yet ready to be treated as production-ready.
- The backend/domain work is still the bigger unknown, but the application workflow itself is now materially built rather than just scaffolded.
- DEV-02 and DEV-03 are no longer greenfield; they are cleanup, integration, and stabilization work.
- DEV-04 is in active implementation now and is the clearest signal of current branch momentum.
- DEV-06 through DEV-08 remain the biggest schedule risk because the repo shows only early admin structures and no visible export/staging-completion layer yet.
- Test coverage is no longer empty, but it is still narrow relative to the expanded upload and admin scope.

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
- Later same-day branch progress now also includes:
  - moving the wizard from three steps to four
  - wiring document upload into the real application flow
  - route and middleware updates for the extra upload step
  - consistent upload-document descriptions
  - controller/request/test updates still sitting in the local worktree
- Additional same-day commits after the initial upload foundation:
  - `4af606b` update step 3 to include the document upload view
  - `e2e944f` move step 3 to step 4
  - `cf7cdb5` add extra step validation to member application middleware
  - `12874bf` update web routes to include the extra document upload step
  - `6119890` support file to keep consistent descriptions for upladed files
  - `aea3435` add another step to layout and update the stepper loop
  - `46c3285` remove step 3 request handler and add store membership application upload handler
  - `b12f1b2` update membership application rules to include the document upload step

## PM Risks
- Domain model may still be incomplete or too close to the paper form rather than the final admin workflow.
- Frontend refinement can sprawl if requirements shift from “polish” to “redesign”.
- Nova/admin review workflow may need additional fields or statuses once the data model settles.
- Meaningful tests are not in place yet, which increases regression risk as the model evolves.
