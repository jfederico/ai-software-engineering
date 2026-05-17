# Prompt: Phase 3 - Asynchronous Operations

**Phase**: 3 / 8
**Goal**: Move long-running operations to background with reliability.
**Estimated Output**: 5-10 commits, async job system working.
**Gate**: Gate 3 Validation

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
Reference PRD non-functional requirements around reliability.
Copilot will implement async job handling.

---

## Copilot Prompt

```
You are an expert backend engineer with experience in job queues and async systems.
I'm at Phase 3: Asynchronous Operations (of 8 phases).

PRD: [INSERT PATH TO PRD]
Project Root: [INSERT PROJECT ROOT]
Phase 0-2 are complete (Foundation, MVP, Persistence).

Phase 3 goal: Move long-running operations (from Phase 1) to background job queue with reliability.

From my PRD:
- Timeline constraint: [Note if time-sensitive operations matter]
- Reliability requirement: [Note any uptime/resilience requirements]

Tasks for Phase 3:

1. JOB QUEUE SETUP
   - Set up Celery + Redis (or equivalent async framework)
   - Create docker-compose entries for Redis and Celery worker
   - Ensure services start reliably
   - Document job queue architecture

2. IDENTIFY LONG-RUNNING OPERATIONS
   - From Phase 1, identify operations that should be async (e.g., large document processing)
   - Keep fast operations synchronous (< 1 second)
   - Move slow operations to background jobs
   - Document which operations are async and why

3. JOB IMPLEMENTATION
   - Create Celery tasks (or equivalent) for long-running operations
   - Implement job status tracking (queued, running, completed, failed)
   - Implement retry logic for failed jobs
   - Ensure jobs are idempotent (safe to retry)

4. JOB PERSISTENCE
   - Store job records in database
   - Track job status, progress, errors
   - Allow user to monitor job progress
   - Implement job cleanup (completed jobs after retention period)

5. ERROR HANDLING AND RETRY
   - Implement exponential backoff on retry
   - Log errors with actionable information
   - Notify system (or log) on permanent failure
   - Document retry policy

6. WORKER RELIABILITY
   - Ensure worker restart doesn't lose in-progress jobs
   - Ensure worker crash doesn't corrupt data
   - Implement graceful shutdown
   - Test worker restart scenarios

7. TESTING
   - Create tests for job submission
   - Create tests for job completion
   - Create tests for job failure and retry
   - Create tests for worker restart (jobs continue after restart)
   - Create tests for concurrent jobs
   - All tests passing

COMMIT DISCIPLINE:
- Commit after queue setup, after job implementation, after tests
- Format: `feat(async): <capability>`
- Example: `feat(async): implement background job processing with Celery`
- Keep commits focused

DOCUMENTATION:
- Update docs/architecture.md to document async flow
- Document job types and their purposes
- Document retry policy
- Document worker monitoring/health

VALIDATION BEFORE GATE:
- Run docker-compose up and verify Celery worker starts
- Submit a long-running operation and verify it goes to queue
- Wait for job to complete and verify result
- Stop worker mid-job, restart, verify job continues
- Run all tests in scripts/test.sh (including async tests)
- Verify linting passes

OUTPUT GATE 3 ASSESSMENT:
- Update CHANGES.md Gate 3 section
- List all commits for Phase 3
- Add test results (especially worker restart test)
- Add Gate 3 Validation section with:
  - Assessment Date: [today]
  - Status: Pending
- Ask user: "Gate 3 is ready. Async jobs are reliable. Review CHANGES.md. Approve or reject?"
```

---

## What Gets Created

After Phase 3, you will have:
- ✅ Redis and Celery running in docker-compose
- ✅ Long-running operations moved to async
- ✅ Job status tracking and monitoring
- ✅ Retry logic for failures
- ✅ Worker restart doesn't lose jobs
- ✅ Tests validate reliability

---

## Next Step

Once Gate 3 is approved, move to Phase 4: `04-phase4.md`

