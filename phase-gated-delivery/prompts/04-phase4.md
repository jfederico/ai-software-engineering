# Prompt: Phase 4 - Management Interface

**Phase**: 4 / 8
**Goal**: Build operational management UI without full user features.
**Estimated Output**: 5-10 commits, admin/ops interface working.
**Gate**: Gate 4 Validation

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
Copilot will build the management interface for operational tasks.

---

## Copilot Prompt

```
You are an expert full-stack engineer experienced with Django/web frameworks.
I'm at Phase 4: Management Interface (of 8 phases).

PRD: [INSERT PATH TO PRD]
Project Root: [INSERT PROJECT ROOT]
Phases 0-3 complete.

Phase 4 goal: Build admin/operational interface for managing core resources without full user features yet.

From my Phase 1-3 implementation, core resources are:
[List entities: collections, documents, jobs, etc.]

Tasks for Phase 4:

1. ADMIN/MANAGEMENT VIEWS
   - Create Django admin interface (or equivalent) for core resources
   - CRUD for main entities (create, read, update, delete)
   - Bulk operations if applicable
   - Keep interface simple and functional

2. OPERATIONAL DASHBOARDS
   - Dashboard showing system status
   - Job queue status and job list
   - System health indicators
   - Error/warning indicators

3. BASIC AUTHENTICATION
   - Implement basic auth (username/password)
   - Create admin user and password reset flow
   - Protect admin endpoints
   - Document user management

4. RESOURCE MANAGEMENT VIEWS
   - View/list core resources (collections, documents, jobs, etc.)
   - Create new resources via form
   - Edit existing resources
   - Delete resources with confirmation
   - Search and filter resources

5. JOB MONITORING
   - Display job list with status
   - Show job progress (if long-running)
   - Display job logs and errors
   - Allow job retry/cancel

6. TESTING
   - Create tests for admin auth
   - Create tests for CRUD operations
   - Create tests for job monitoring views
   - All tests passing

COMMIT DISCIPLINE:
- Commit after admin setup, after management views, after auth, after tests
- Format: `feat(admin): <capability>`
- Example: `feat(admin): implement resource management dashboard`

DOCUMENTATION:
- Update README with admin interface instructions
- Document how to create admin user
- Document admin interface usage

VALIDATION BEFORE GATE:
- Start app and navigate to admin interface
- Create a resource via admin UI
- Update a resource
- Delete a resource
- Monitor jobs from admin UI
- Run all tests
- Verify linting passes

OUTPUT GATE 4 ASSESSMENT:
- Update CHANGES.md Gate 4 section
- List all commits for Phase 4
- Add test results
- Add Gate 4 Validation section with:
  - Assessment Date: [today]
  - Status: Pending
- Ask user: "Gate 4 is ready. Management UI is operational. Review CHANGES.md. Approve or reject?"
```

---

## What Gets Created

After Phase 4, you will have:
- ✅ Django admin or equivalent management interface
- ✅ CRUD operations for core resources
- ✅ Job monitoring and management
- ✅ Basic authentication
- ✅ System status dashboard
- ✅ No CLI required for operational tasks

---

## Next Step

Once Gate 4 is approved, move to Phase 5: `05-phase5.md` (ALPHA RELEASE POINT)

