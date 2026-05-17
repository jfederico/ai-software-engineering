# Prompt: Phase 5 - User-Facing Interface (ALPHA RELEASE)

**Phase**: 5 / 8
**Goal**: Build user-facing interface for primary use case.
**Estimated Output**: 8-15 commits, Alpha version ready.
**Gate**: Gate 5 Validation (**ALPHA RELEASE**)

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
Reference PRD user personas and use cases.
Copilot will build the user-facing interface.

---

## Copilot Prompt

```
You are an expert full-stack engineer and UX designer.
I'm at Phase 5: User-Facing Interface (of 8 phases).

PRD: [INSERT PATH TO PRD]
Project Root: [INSERT PROJECT ROOT]
Phases 0-4 complete (Foundation, MVP, Persistence, Async, Management).

Phase 5 goal: Build user-facing interface for primary use case. This is the ALPHA RELEASE point.

From my PRD:
- Primary user personas: [Copy from PRD]
- Primary use case: [Copy from PRD]
- User interaction: [How will users interact? Chat, forms, menus?]
- Success metrics: [Copy relevant metrics from PRD]

Tasks for Phase 5:

1. USER INTERFACE DESIGN
   - Design user workflow for primary use case
   - Keep interface simple and intuitive (minimal onboarding)
   - Non-technical users should understand it without docs
   - Design or find UI framework (React, Vue, simple HTML/CSS)

2. PRIMARY USER FEATURE
   - Build the main user interaction (question interface, form, etc.)
   - Implement the user workflow from PRD primary use case
   - Display results clearly
   - Handle errors gracefully

3. RESULT VISUALIZATION
   - Display results from Phase 1 feature in user-friendly format
   - Show relevant context or evidence
   - Make it clear to user what the result is
   - Add confidence levels or quality indicators if applicable

4. RESPONSIVE DESIGN
   - Ensure interface works on desktop
   - Basic mobile support (or document mobile limitations)
   - No major UI glitches or unresponsive elements

5. USER HELP & GUIDANCE
   - Clear instructions on how to use the feature
   - Error messages that guide users
   - Help text for inputs
   - Keep guidance minimal (design speaks for itself)

6. INTEGRATION WITH BACKEND
   - Connect UI to Phase 1-4 backend
   - Ensure data flows correctly
   - Handle async operations (show progress for long jobs)
   - Handle errors gracefully

7. TESTING
   - Create tests for user interface (manual testing documented)
   - Test primary use case end-to-end as a user would
   - Test error scenarios (invalid input, server errors)
   - Performance: typical interaction < 10 seconds response
   - All tests passing

COMMIT DISCIPLINE:
- Commit after UI framework setup, after main feature, after visualization, after integration
- Format: `feat(ui): <capability>`
- Example: `feat(ui): build user-facing chat interface`

DOCUMENTATION:
- Create user guide (how to use the interface)
- Update README with UI instructions
- Document user workflows

VALIDATION BEFORE GATE:
- Start app and open user interface
- Walk through primary use case as a user
- Verify results display correctly
- Test error handling
- Test on mobile (or document mobile limitations)
- Run all tests
- Verify linting passes
- Check performance (typical operation < 10 seconds)

OUTPUT GATE 5 ASSESSMENT:
- Update CHANGES.md Gate 5 section
- List all commits for Phase 5
- Add test results and performance metrics
- Add Gate 5 Validation section with:
  - Assessment Date: [today]
  - Status: Pending (ALPHA RELEASE CANDIDATE)
  - Note: This is the Alpha Release point
- Ask user: "Gate 5 is ready. **This is your ALPHA RELEASE**. Interface is user-facing and functional. Review CHANGES.md. Approve to release Alpha version?"

ALPHA RELEASE:
If approved, this is your Alpha version:
- Core feature works end-to-end
- Users can interact with the system
- Results are understandable
- Not feature-complete but valuable
- Ready for user testing and feedback
```

---

## What Gets Created

After Phase 5, you will have:
- ✅ User-facing interface (web/app)
- ✅ Primary feature accessible to users
- ✅ Results visualized clearly
- ✅ Error handling and guidance
- ✅ Performance acceptable
- ✅ **ALPHA RELEASE READY**

---

## Next Step

Once Gate 5 is approved (ALPHA RELEASE), move to Phase 6: `06-phase6.md`

