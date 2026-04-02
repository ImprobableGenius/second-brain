---
title: "AMIK Project Context"
---

# AMIK Project Context

## Project Snapshot
- Source: `Workload Metrics - Main.csv`
- Project type: Laravel maintenance project
- Local repo path: `/Users/aarongilani/Dev_Arena/Laravel/amik-job-board`
- Product: AMIK Job Board
- Current branch: `fix/open-date-bug`
- Remote: `git@github.com:ImprobableGenius/amik-job-board.git`
- Priority: Low at portfolio level
- Load: Low
- Working estimate: 24h total remaining
- Task code prefix: `AMIK`
- Start date: TBD
- Deadline: Capacity Available
- Status: Maintenance Queue

## Stack
- Laravel 10
- PHP 8.1+
- Jetstream
- Livewire
- Nova
- Scout with Meilisearch
- Cashier and Spark Stripe
- PostgreSQL
- Vite + Tailwind
- Sentry
- DigitalOcean deployment pipeline

## Source Of Truth
- Project board: `/Users/aarongilani/Dev_Arena/Laravel/amik-job-board/docs/PROJECT_BOARD.md`
- Project board last updated: March 17, 2025
- Important mismatch: the board says no items are in progress, but the repo currently has an active maintenance branch and a dirty worktree, so the board is stale relative to the codebase

## Current Maintenance Item To Queue
- Board item: `ENH-001 Job Posting Scheduling`
- Board priority: High within the AMIK project
- Portfolio priority: Low until capacity is available
- Board effort: Medium (`3-5 days`)
- Working PM estimate: `24h remaining`
- Active task ID: `AMIK-01`

## What ENH-001 Is Trying To Fix
- Employers should be able to create job postings now and schedule them to go live later
- Jobs with a future `open_date` should stay hidden from the public board until that date arrives
- Employer-facing views should distinguish live, scheduled, and past jobs
- Search and indexing should not expose scheduled jobs before they open

## Current Code Reality
- `JobController::store` currently publishes jobs immediately with `status = true`
- `open_date` exists, but the project board says it currently behaves as display data rather than visibility control
- The scheduler in `app/Console/Kernel.php` only unpublishes jobs when `close_date` passes
- Public job visibility currently depends on `status` and `close_date`
- Search/indexing logic touches:
  - `app/Models/Job.php`
  - `app/Services/JobSearchService.php`
  - Livewire job listing components
  - middleware and employer views

## Current Repo State
- Dirty worktree on `fix/open-date-bug`
- Modified files:
  - `Dockerfile`
  - `app/Models/Job.php`
  - `app/Models/Org.php`
  - `config/scout.php`
  - `resources/views/job/inactive.blade.php`
  - `resources/views/jobs.blade.php`
- New file:
  - `app/Services/JobSearchService.php`
- This strongly suggests ENH-001 has already been partially started in code, even though the project board still lists it in backlog

## PM Read On Scope
- This is not a simple 4h maintenance tweak
- The documented enhancement crosses:
  - job creation flow
  - scheduled publishing logic
  - scheduler behavior
  - employer dashboard states
  - search visibility
  - Scout/Meilisearch indexing
  - possible credit deduction rules
  - tests
- The most likely unresolved product decision is credit timing: whether credits are consumed when a job is scheduled or when it goes live

## Queue Positioning
- Keep this project in the queue until capacity is available
- Do not assign a hard delivery date yet
- Follow-up reminder: if no response is received by Monday, 2026-03-30, send an AMIK check-in and confirm whether `ENH-001` should remain parked until capacity opens
- When capacity opens, first step should be to review `fix/open-date-bug` against `docs/PROJECT_BOARD.md` and decide whether to continue that branch or reconcile it with `main`

## Useful Starting Points
- Board and backlog: `docs/PROJECT_BOARD.md`
- Job creation flow: `app/Http/Controllers/JobController.php`
- Scheduler: `app/Console/Kernel.php`
- Search/indexing: `app/Models/Job.php`, `app/Services/JobSearchService.php`
- Public listings: `app/Livewire/JobsIndex.php`
- Employer views: `resources/views/job/*.blade.php`

## PM Notes
- AMIK is in maintenance mode, not active sprint delivery
- The queue trigger is available capacity, not calendar urgency
- Current PM reminder is to follow up during the week of `2026-03-30` if the client or stakeholder still has not responded
- When this project is pulled into active work, treat the first hour as review/reconciliation time because the board and branch state are not aligned
