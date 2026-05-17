# Prompt: Phase 6 - Advanced Features

**Phase**: 6 / 8
**Goal**: Implement secondary features from PRD.
**Estimated Output**: 8-15 commits, feature-rich product.
**Gate**: Gate 6 Validation

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
Reference PRD secondary requirements.
Copilot will expand feature set.

---

## Copilot Prompt

```
You are an expert full-stack engineer.
I'm at Phase 6: Advanced Features (of 8 phases).

PRD: [INSERT PATH TO PRD]
Project Root: [INSERT PROJECT ROOT]
Phases 0-5 complete (Alpha version ready).

Phase 6 goal: Implement secondary and advanced features from PRD.

From my PRD:
- Secondary functional requirements: [Copy F6-F[N] from PRD]
- Advanced use cases: [Copy secondary use cases from PRD]
- Configurable behavior: [Any settings/profiles from PRD]

Tasks for Phase 6:

1. SECONDARY FEATURES
   - Implement features from PRD that weren't in MVP
   - For each feature:
     - Add backend logic
     - Add UI/UX
     - Add database support if needed
     - Add tests

2. ADVANCED CONFIGURATION
   - Implement user-customizable settings if applicable
   - Domain profiles or similar configurable behavior
   - Allow users to tailor the product to their needs

3. POWER-USER WORKFLOWS
   - Implement workflows for advanced users
   - Examples: bulk operations, exports, advanced search
   - Keep accessible but powerful

4. INTEGRATION FEATURES
   - Implement any integrations mentioned in PRD
   - APIs or connections to external systems
   - Handle errors gracefully

5. NO REGRESSIONS
   - Ensure Phase 5 (user interface) still works perfectly
   - Run full test suite including Phase 5 tests
   - Verify no performance degradation
   - Verify core feature still works as expected

6. TESTING
   - Create tests for each new feature
   - Create tests for advanced workflows
   - Create integration tests if new systems added
   - All tests passing

COMMIT DISCIPLINE:
- Commit after each major feature
- Format: `feat(<feature>): <description>`
- Example: `feat(advanced-search): implement full-text search`

DOCUMENTATION:
- Update user guide with new features
- Update API documentation
- Document advanced configurations

VALIDATION BEFORE GATE:
- Test each new feature
- Verify no regressions in Phase 5
- Run complete test suite
- Performance acceptable for new features
- Verify linting passes

OUTPUT GATE 6 ASSESSMENT:
- Update CHANGES.md Gate 6 section
- List all commits for Phase 6
- Add test results and coverage
- Add Gate 6 Validation section with:
  - Assessment Date: [today]
  - Status: Pending
- Ask user: "Gate 6 is ready. Advanced features implemented. Review CHANGES.md. Approve or reject?"
```

---

## What Gets Created

After Phase 6, you will have:
- ✅ Secondary features implemented
- ✅ Configurable behavior
- ✅ Advanced user workflows
- ✅ Integrations working
- ✅ No regressions
- ✅ Full-featured product

---

## Next Step

Once Gate 6 is approved, move to Phase 7: `07-phase7.md`

