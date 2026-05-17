# Prompt 7: Finalize PRD - Lock and Handoff

**Phase**: 7 / 7
**Goal**: Lock the PRD and prepare it for implementation.
**Estimated Time**: 15-20 minutes
**Output**: Final, signed PRD ready for handoff.

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
This is the final phase. We'll do a final review and prepare your PRD for handoff 
to Phase-Gated Delivery or other implementation methodologies.

---

## Copilot Prompt

```
We're in Phase 7: Finalize PRD.
This is the final phase of requirement gathering.

We'll:
1. Do a final quality check
2. Format the PRD properly
3. Lock it for implementation
4. Prepare for handoff

Let me ask final questions:

1. "Are there any open questions or items we deferred during gathering?
   If yes, let me list them and we'll mark them as:
   - Resolve before v1 implementation
   - Defer to Phase 1 of implementation (can be decided later)
   - Note as assumption to validate"

2. "For success metrics (from Phase 6):
   Can we make them even MORE specific and measurable?
   
   Example:
   Instead of: 'Users will be satisfied'
   Better: '80% of users who ingested documents will ask a question within 1 week'
   
   What are your 3-5 most important success metrics?"

3. "What's one thing you're MOST uncertain about?
   Something where you might be wrong and could learn more?
   
   Examples:
   - 'I'm not sure if users will want local-only vs cloud'
   - 'I'm not sure if vector databases will scale to 100k documents'
   - 'I'm not sure if the timeline is realistic with our team'
   
   Let me document this as an assumption to validate during implementation."

4. "Is there anything we DIDN'T ask about during gathering that you think matters?
   Anything missing from the PRD?"

After I answer, I'll:

1. Generate a final PRD document in proper format
2. Mark all assumptions and open questions
3. Create sign-off section
4. Prepare handoff instructions

Then say: "Here's your final PRD.

REVIEW CHECKLIST:
- [ ] Product overview and elevator pitch accurate?
- [ ] Problem and solution statements clear?
- [ ] Scope (features in/out) realistic?
- [ ] User personas and use cases complete?
- [ ] Functional and non-functional requirements specific?
- [ ] Success metrics measurable?
- [ ] Constraints documented?
- [ ] Risks and assumptions listed?
- [ ] Anything else needed?

Is this PRD ready to hand off to implementation?
Any final changes before we lock it?"

Wait for approval.

Once approved, I'll:
1. Add final metadata (version, approval date, owner)
2. Save it as PRD.md in your project
3. Provide instructions for handoff to Phase-Gated Delivery

Finally: "Phase 7 complete! 

Your PRD is finalized and ready.

NEXT STEPS:
1. Save this PRD in your project as docs/PRD.md
2. If using Phase-Gated Delivery:
   - Copy the phase-gated-delivery template
   - Run: 'Implement Phase 0 using PRD: <path-to-PRD.md>'
3. Copilot will use this PRD to generate architecture, 
   design documents, and acceptance criteria for each phase.

Good luck with implementation! You've done the hard thinking up front."
```

---

## PRD Sign-Off Section

When finalizing, the PRD should include:

```markdown
## Sign-Off and Approval

**PRD Author**: [Your name]
**Date Created**: [Date]
**Date Finalized**: [Date]
**Version**: 1.0

**Stakeholders**:
- [ ] Product Owner: [Name, date]
- [ ] Technical Lead: [Name, date] (optional at this stage)
- [ ] Other: [Name, date]

**Assumptions to Validate**:
[List of things we're assuming that might change]

**Open Questions for Implementation**:
[Things Copilot/implementation team will need to decide]
```

---

## Notes for Better Results

- **Don't over-think**: At this point, you've documented thoroughly. Lock it.
- **Assumptions are valuable**: Documenting what you're unsure about helps implementation make smart choices.
- **You can revise v1**: After Phase 1 of implementation, if major assumptions prove wrong, it's OK to update. But freeze for now.

---

## Handoff to Phase-Gated Delivery

Once PRD is finalized:

**Option 1: Automated Handoff**
```
Copy the PRD.md file to your project repo.
Tell Copilot:

"I'm ready for Phase-Gated Delivery.
PRD is at: docs/PRD.md
Please implement Phase 0 based on this PRD."
```

**Option 2: Manual Handoff**
Share PRD with the implementation team and discuss:
- Architecture direction (what did we recommend?)
- Success criteria (what gates will we measure against?)
- Known risks (what might we get wrong?)

---

## Completion

Congratulations! 

You've completed the Requirement Gathering & Documentation methodology.

Your PRD is now ready for:
- Phase-Gated Delivery (implementation methodology)
- Traditional waterfall or agile development
- Stakeholder review and approval
- Team planning and estimation

What's next is implementation using your chosen methodology.

