# Prompt: Phase 1 - Core Feature MVP

**Phase**: 1 / 8
**Goal**: Implement the primary feature to prove core value proposition works.
**Estimated Output**: 8-15 commits, end-to-end feature working.
**Gate**: Gate 1 Validation

---

## How to Use This Prompt

Copy the **Copilot Prompt** below into your Copilot chat.
Reference your PRD and Phase 0 baseline.
Copilot will implement the MVP feature.

---

## Copilot Prompt

```
You are an expert full-stack engineer.
I'm at Phase 1: Core Feature MVP (of 8 phases).

PRD: [INSERT PATH TO PRD]
Project Root: [INSERT PROJECT ROOT]
Phase 0 is complete.

Phase 1 goal: Implement the primary feature from the PRD to prove core value works end-to-end.

From my PRD, the primary use case is:
[Copy primary use case from PRD section 4]

The core functional requirements are:
[Copy F1-F5 from PRD functional requirements]

Tasks for Phase 1:

1. FEATURE ANALYSIS
   - Identify the minimum set of functionality to deliver the primary use case
   - Break into sub-features or workflows
   - Plan data models (even if temporary)

2. DATA MODELS
   - Create initial Django models (or equivalent) for core entities
   - Create database migrations
   - Keep schema simple (only what's needed for MVP)
   - Document model relationships

3. API/SERVICE LAYER
   - Create API endpoints or service functions for the primary feature
   - Implement the main workflow from the use case
   - Include error handling for common cases
   - Document API contracts

4. PERSISTENCE
   - Implement database persistence for core data
   - Ensure data persists across operations
   - Handle concurrent access safely

5. TESTING
   - Create unit tests for core business logic
   - Create integration tests for end-to-end workflows
   - Aim for >80% code coverage on new code
   - All tests passing

6. MANUAL VALIDATION
   - Test the feature manually end-to-end
   - Walk through the primary use case scenario
   - Note any issues or gaps
   - Document steps to reproduce

COMMIT DISCIPLINE:
- Commit after models, after API layer, after tests
- Format: `feat(core-feature): implement <specific capability>`
- Example: `feat(core-feature): implement document ingestion`
- Keep commits focused

DOCUMENTATION:
- Update docs/architecture.md with Phase 1 design
- Add API documentation
- Update README with feature explanation
- Add acceptance criteria from Phase 1 gate to docs

VALIDATION BEFORE GATE:
- Run scripts/test.sh and ensure all tests pass
- Run scripts/lint.sh and ensure no critical issues
- Manually test the primary use case end-to-end
- Verify data persists correctly
- Verify error handling works

OUTPUT GATE 1 ASSESSMENT:
- Update CHANGES.md Gate 1 section
- List all commits for Phase 1
- Add test results and coverage %
- Add manual validation results
- Add Gate 1 Validation section with:
  - Assessment Date: [today]
  - Status: Pending (awaiting user approval)
- Ask user: "Gate 1 is ready. Primary feature works end-to-end. Review CHANGES.md. Approve or reject?"
```

---

## What Gets Created

After Phase 1, you will have:
- ✅ Primary feature implemented end-to-end
- ✅ Database models and migrations
- ✅ API layer functional
- ✅ Tests passing (unit + integration)
- ✅ Feature works with manual testing
- ✅ MVP proves core value

---

## Next Step

Once Gate 1 is approved, move to Phase 2: `02-phase2.md`

