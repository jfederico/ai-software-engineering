# Prompt: Phase 2 - Data Persistence and Integrity

**Phase**: 2 / 8
**Goal**: Harden data persistence, migrations, and metadata management.
**Estimated Output**: 5-10 commits, production-ready persistence.
**Gate**: Gate 2 Validation

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
Reference PRD requirements around reliability and data integrity.
Copilot will harden persistence layer.

---

## Copilot Prompt

```
You are an expert database and backend engineer.
I'm at Phase 2: Data Persistence and Integrity (of 8 phases).

PRD: [INSERT PATH TO PRD]
Project Root: [INSERT PROJECT ROOT]
Phase 0 (Foundation) and Phase 1 (MVP feature) are complete.

Phase 2 goal: Ensure data persistence is reliable, migrations work cleanly, and no data loss.

From my PRD:
- Non-functional requirements: [Copy relevant N-F requirements around reliability, durability]
- Data model assumptions: [Note any data consistency requirements]

Tasks for Phase 2:

1. DATABASE SCHEMA REVIEW
   - Review current schema from Phase 1
   - Ensure all core entities are modeled
   - Add missing indices for performance
   - Add foreign key constraints for integrity
   - Create or update docs/data-model.md with schema details

2. IDEMPOTENT OPERATIONS
   - Ensure Phase 1 core operations (ingestion, persistence) are idempotent
   - If the same operation runs twice, no duplicates/corruption
   - Test: run Phase 1 feature twice and verify data integrity
   - Document idempotency guarantees

3. MIGRATION FRAMEWORK
   - Ensure migration framework is set up (Alembic, Django migrations, etc.)
   - Create test that runs migrations from empty schema
   - Ensure no manual steps required
   - Document migration process

4. DATA INTEGRITY CONSTRAINTS
   - Add unique constraints where needed
   - Add NOT NULL constraints where required
   - Add check constraints for business rules
   - Verify referential integrity (foreign keys)
   - Add audit fields if needed (created_at, updated_at)

5. TRANSACTION HANDLING
   - Ensure critical operations are transactional
   - Prevent partial failures
   - Handle rollback scenarios
   - Document transaction boundaries

6. TESTING
   - Create tests for migration path (empty -> full schema)
   - Create tests for data integrity constraints
   - Create tests for idempotent operations
   - Create tests for concurrent access (if applicable)
   - All tests passing

7. BACKUP AND RECOVERY THOUGHTS
   - Document how data can be backed up
   - Document how data can be recovered
   - (Full backup strategy is Phase 8, but plan here)

COMMIT DISCIPLINE:
- Commit after schema updates, after migration tests, after integrity tests
- Format: `refactor(db): <improvement>` or `feat(db): <new capability>`
- Example: `refactor(db): add indices for query performance`
- Keep commits focused

DOCUMENTATION:
- Update docs/data-model.md with full schema details
- Document migration process
- Document idempotency guarantees
- Document data integrity constraints

VALIDATION BEFORE GATE:
- Run migration test: start from empty schema, apply all migrations, verify result
- Run Phase 1 feature twice: verify no duplicates
- Run all tests in scripts/test.sh
- Verify linting passes
- Document any schema changes or new constraints

OUTPUT GATE 2 ASSESSMENT:
- Update CHANGES.md Gate 2 section
- List all commits for Phase 2
- Add migration test results
- Add idempotency test results
- Add Gate 2 Validation section with:
  - Assessment Date: [today]
  - Status: Pending
- Ask user: "Gate 2 is ready. Data persistence is hardened. Review CHANGES.md. Approve or reject?"
```

---

## What Gets Created

After Phase 2, you will have:
- ✅ Database schema with constraints and indices
- ✅ Migration framework working cleanly
- ✅ Operations are idempotent (no duplicates on re-run)
- ✅ Data integrity verified
- ✅ Tests ensure reliability
- ✅ Production-ready persistence layer

---

## Next Step

Once Gate 2 is approved, move to Phase 3: `03-phase3.md`

