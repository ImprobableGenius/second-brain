# IPAM Project Context

## Project Snapshot
- Source: `Workload Metrics - Main.csv`
- Project type: Fresh Laravel-based member management system
- Local repo path: `/Users/aarongilani/Dev_Arena/Laravel/ipam`
- Product: Indigenous People's Alliance of Manitoba (IPAM) Membership Application System
- Current branch: `main`
- Remote: `git@github.com:Vincent-Design-Inc/ipam.git`
- Priority: High
- Load: High
- Working estimate: 20h total remaining
- Task code prefix: `IPAM`
- Start date: 2026-03-16
- Deadline: 2026-04-25
- Status: In Progress

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
- The basic public membership application form is already built
- The app already has:
  - membership application controller and request validation
  - `MembershipApplication` and `MembershipApplicationChild` models
  - migrations for applications and dependent children
  - Nova resources and filters for admin review
  - frontend JS for dynamic child rows and fee updates
- The project is actively being developed on a dirty `main` branch

## Current Delivery Tasks
- [ ] IPAM-01 Member object modeling | Estimate: 12h
- [ ] IPAM-02 Membership frontend refinement | Estimate: 8h
- Estimate assumption: current work is finishing and correcting the first pass, not building a full multi-role membership platform from scratch
- Estimate risk: add 6h to 10h if “member objects” expands beyond application records into approved-member lifecycle, renewals, payments, or document uploads

## Current Code Reality
- Public form routes are already in place in `routes/web.php`
- `MembershipApplicationController` stores applications and nested children
- Validation is defined in `StoreMembershipApplicationRequest`
- The current domain model centers on:
  - `MembershipApplication`
  - `MembershipApplicationChild`
- Nova resources already exist for:
  - `MembershipApplication`
  - `MembershipApplicationChild`
  - status/member type/aboriginal status filters
- The form frontend already handles dynamic children and auto-calculates total fees

## PM Read On Remaining Work
- The backend/domain work is still the bigger unknown
- “Member objects need to be modeled and updated” likely means the first-pass application entities need refinement before the system is stable enough for real admin use
- The frontend exists, but it still needs refinement for layout, usability, and likely mobile/responsive polish
- There is little meaningful test coverage yet; the `tests/` folder still only contains starter example tests

## Current Repo State
- Dirty worktree with active membership-application changes
- Modified files include:
  - `database/seeders/DatabaseSeeder.php`
  - `package-lock.json`
  - `resources/js/app.js`
  - `routes/web.php`
- New untracked work includes:
  - membership application controller
  - form request
  - membership application models
  - Nova resources and filters
  - factories, migrations, seeder
  - membership application views
  - extra project notes folders
- This confirms the project is past scaffolding and in the first implementation pass

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
- Public form flow: `routes/web.php`, `app/Http/Controllers/MembershipApplicationController.php`
- Validation: `app/Http/Requests/StoreMembershipApplicationRequest.php`
- Domain models: `app/Models/MembershipApplication.php`, `app/Models/MembershipApplicationChild.php`
- Database shape: `database/migrations/*membership_application*`
- Admin workflow: `app/Nova/MembershipApplication.php`, `app/Nova/MembershipApplicationChild.php`
- Frontend behavior: `resources/views/membership-application/form.blade.php`, `resources/js/app.js`

## PM Notes
- IPAM is an active build, not a maintenance project
- The basic form is done; the current focus is turning that first pass into a stable domain model and a production-ready frontend
- Treat backend modeling and frontend refinement as the two primary workstreams until the member object structure is settled
