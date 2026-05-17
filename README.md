# Complete Software Development Methodology
## From Requirements Gathering to Production Release

This is the master guide for the complete automated software development system comprised of two decoupled methodologies:

1. **Requirement Gathering & Documentation** (Interactive)
2. **Phase-Gated Delivery** (Automated Implementation)

---

## Open Source Release

This repository is ready for public use as a methodology toolkit.

Before contributing or opening issues, review:
- `LICENSE`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`
- `SECURITY.md`
- `SUPPORT.md`
- `CHANGELOG.md`
- `VERSIONING.md`
- `GOVERNANCE.md`

The current public baseline is **v0.1.0**.

---

## Overview: The Complete Workflow

```text
Your Idea
    ↓
Requirement Gathering & Documentation (Methodology 1)
    ↓ (You interact heavily: answer prompts, clarify scope)
PRD (Product Requirements Document)
    ↓ (Clear artifact - ready for implementation)
Phase-Gated Delivery (Methodology 2)
    ↓ (Copilot automates: 8 phases, 8 gates)
    Phase 0: Foundation
    ↓ (Gate 0: You approve)
    Phase 1: Core Feature MVP
    ↓ (Gate 1: You approve)
    Phase 2-4: Infrastructure & Management
    ↓ (Gates 2-4: You approve)
    Phase 5: User Interface (ALPHA RELEASE)
    ↓ (Gate 5: You approve - ALPHA ships)
    Phase 6-7: Features & Quality
    ↓ (Gates 6-7: You approve)
    Phase 8: Production Hardening
    ↓ (Gate 8: You approve - PRODUCTION RELEASE)
Production-Ready Software
```

---

## When to Use Each Methodology

### Use Requirement Gathering When:
- You have an idea but it's not fully formed.
- You need to align with stakeholders on scope and direction.
- You want a formal PRD before implementation.
- You're not sure if your idea is feasible or what it should include.

### Use Phase-Gated Delivery When:
- You have a PRD (from Requirement Gathering or elsewhere).
- You want automated, gated implementation with quality control.
- You want minimal interaction (only validate gates).
- You want reproducible, auditable progress tracking.

---

## Detailed Workflow

### PHASE 1: Requirement Gathering & Documentation

**Duration**: 2-4 hours of interactive work over 1-2 weeks.
**User Role**: Heavy interaction. You answer questions, refine scope, clarify requirements.

**Steps**:
1. Read `requirement-gathering/METHODOLOGY.md`
2. Start with `requirement-gathering/prompts/01-kickoff.md`
3. Work through phases 1-7 (one at a time)
4. End with finalized PRD in `docs/PRD.md`

**Key Prompts**:
- `01-kickoff.md` — Capture core idea
- `02-scope.md` — Define features in/out
- `03-users-usecases.md` — Understand users and workflows
- `04-requirements.md` — Formalize functional/non-functional requirements
- `05-constraints.md` — Identify timeline, budget, technical limits
- `06-review-refine.md` — Spot gaps and conflicts
- `07-finalize-prd.md` — Lock and prepare for handoff

**Output**:
- ✅ Finalized PRD (`docs/PRD.md`)
- ✅ Clear problem statement and solution
- ✅ User personas and workflows
- ✅ Functional and non-functional requirements
- ✅ Success metrics and constraints
- ✅ Ready for implementation

**Template**:
- `requirement-gathering/templates/PRD-TEMPLATE.md` — Use this as your PRD format

---

### PHASE 2: Phase-Gated Delivery Implementation

**Duration**: 4-10 weeks of mostly automated work (depends on scope and gate rejections).
**User Role**: Minimal interaction. You validate 8 gates (binary approve/reject decisions).

**Steps**:
1. Have PRD ready (from Requirement Gathering or elsewhere)
2. Read `phase-gated-delivery/METHODOLOGY.md`
3. Initialize project (copy templates to your project)
4. Start Phase 0 using `phase-gated-delivery/prompts/00-phase0.md`
5. After each phase, review gate assessment in `CHANGES.md`
6. Approve or reject to advance or remediate

**The 8 Phases**:
1. **Phase 0**: Foundation & Tooling (Django, Docker, CI)
2. **Phase 1**: Core Feature MVP (Primary feature works)
3. **Phase 2**: Data Persistence (Robust storage, migrations)
4. **Phase 3**: Async Operations (Background jobs, reliability)
5. **Phase 4**: Management Interface (Admin/ops UI)
6. **Phase 5**: User Interface ⭐ **ALPHA RELEASE**
7. **Phase 6**: Advanced Features (Secondary requirements)
8. **Phase 7**: Evaluation & Quality (Measure success metrics)
9. **Phase 8**: Production Hardening ✓ **PRODUCTION RELEASE**

**Key Files**:
- `phase-gated-delivery/prompts/0N-phaseN.md` — Phase implementation prompts
- `CHANGES.md` — Gate tracking (auto-updated)
- `COMMIT-POLICY.md` — Commit format rules
- `AUTOMATION.md` — User interaction guide
- `docs/side-plans/` — Deviations and discoveries

**Output**:
- ✅ Production-ready software
- ✅ 8 phases implemented, 8 gates passed
- ✅ Full audit trail (commits, gates, decisions)
- ✅ Documentation and runbooks
- ✅ Deployment automation
- ✅ Ready for production release

---

## Key Interaction Points

### In Requirement Gathering
You interact **heavily and frequently**:
- Answer targeted questions per phase
- Refine scope as you discover trade-offs
- Iterate on requirements with Copilot
- Make scope/timeline/architecture decisions

**Goal**: Produce a high-quality PRD that removes ambiguity.

### In Phase-Gated Delivery
You interact **sparingly and only at gates**:
- Review gate assessment (1-2 hours per gate)
- Make binary decision (approve or reject)
- Provide feedback if rejecting (30 min)
- Monitor progress in CHANGES.md

**Goal**: Validate that each phase meets expectations, gate by gate.

---

## What PRD Must Contain (For Phase-Gated Delivery)

Phase-Gated Delivery assumes a complete PRD with:

1. **Problem & Solution** — Clear statement of what problem you're solving
2. **Target Users** — Personas and who will use this
3. **Primary Use Case** — The main scenario/workflow
4. **Functional Requirements** — What the system must do (F1, F2, ...)
5. **Non-Functional Requirements** — Performance, reliability, security, scalability
6. **Success Metrics** — How you'll measure success
7. **Scope Boundaries** — What's in v1, what's deferred
8. **Constraints** — Timeline, budget, team, technical limits
9. **Architecture Direction** — Tech stack preferences (if known)

PRD doesn't need to be perfect—Phase-Gated Delivery can surface and handle deviations. But it should be complete enough to drive architecture and design decisions.

---

## Success Criteria by Milestone

### Requirement Gathering Success
- ✅ PRD is finalized and signed off
- ✅ Stakeholders align on scope and vision
- ✅ Requirements are specific and testable
- ✅ Success metrics are measurable
- ✅ Constraints are documented and realistic

### MVP Success (End of Phase 2, Gate 2)
- ✅ Core feature works end-to-end
- ✅ Data persists correctly
- ✅ Primary use case validated

### Alpha Success (End of Phase 5, Gate 5)
- ✅ User-facing interface is functional
- ✅ Users can accomplish primary use case
- ✅ Results are understandable
- ✅ Ready for user feedback and testing

### Production Success (End of Phase 8, Gate 8)
- ✅ All quality metrics passed
- ✅ Security scans clean
- ✅ Deployment automated and tested
- ✅ Runbooks complete
- ✅ Ready for production release

---

## Handling Deviations and Changes

### During Requirement Gathering
If you discover something in Phase 6 (Review & Refine) that contradicts Phase 2 (Scope):
- Go back to Phase 2 and update scope
- Iterate until coherent
- This is normal and expected

### During Phase-Gated Delivery
If Copilot discovers a blocker during implementation:
- A side plan is created (`docs/side-plans/SP-NNN-title.md`)
- Side plan documents: issue, options, chosen path, impact
- You may need to approve the side plan decision
- Side plans are linked in CHANGES.md

### Major Changes
If major assumptions prove wrong (e.g., "vector databases won't scale as expected"):
- Document as side plan
- Update PRD if necessary
- Update acceptance criteria for affected gates
- Gate validations may be adjusted accordingly

---

## Tools and Files

### Requirement Gathering

```text
requirement-gathering/
  METHODOLOGY.md              (How to use requirement gathering)
  prompts/
    01-kickoff.md
    02-scope.md
    ... (7 prompts total)
    07-finalize-prd.md
  templates/
    PRD-TEMPLATE.md           (Output format)
```

### Phase-Gated Delivery

```text
phase-gated-delivery/
  METHODOLOGY.md              (How to use phase-gated delivery)
  prompts/
    00-phase0.md
    01-phase1.md
    ... (8 phases total)
    08-phase8.md
  templates/
    CHANGES-TEMPLATE.md       (Gate tracking log)
    SIDE-PLAN-TEMPLATE.md     (Deviation template)
    COMMIT-POLICY-TEMPLATE.md (Commit format rules)
    AUTOMATION-TEMPLATE.md    (User interaction guide)
```

---

## Sample Timeline

### Requirement Gathering Timeline
- Day 1: Phase 1 (Kickoff) — 20 minutes
- Day 2-3: Phases 2-3 (Scope, Users) — 1 hour total
- Day 4-5: Phase 4 (Requirements) — 45 minutes
- Day 6: Phase 5 (Constraints) — 30 minutes
- Day 7-8: Phase 6 (Review & Refine) — 1-2 hours (may iterate)
- Day 9: Phase 7 (Finalize) — 20 minutes

**Total**: 1-2 weeks of calendar time, 2-4 hours of work time.

### Phase-Gated Delivery (Assuming Minimal Gate Rejections)
- Phase 0: 1-2 days → Gate 0 validation: 1-2 hours
- Phase 1: 2-3 days → Gate 1 validation: 1-2 hours
- Phase 2: 2-3 days → Gate 2 validation: 1-2 hours
- Phase 3: 2-3 days → Gate 3 validation: 1-2 hours
- Phase 4: 2-3 days → Gate 4 validation: 1-2 hours
- Phase 5: 3-5 days → Gate 5 validation: 1-2 hours **ALPHA RELEASE**
- Phase 6: 3-5 days → Gate 6 validation: 1-2 hours
- Phase 7: 2-3 days → Gate 7 validation: 1-2 hours
- Phase 8: 3-5 days → Gate 8 validation: 1-2 hours **PRODUCTION RELEASE**

**Total**: 4-8 weeks of elapsed time (with full-time Copilot), ~16 hours of user validation time.

---

## Getting Started

### Quick Start: New Project from Scratch
1. **Read this guide** (10 minutes)
2. **Go to Requirement Gathering**:
   - Read `requirement-gathering/METHODOLOGY.md` (10 minutes)
   - Run `requirement-gathering/prompts/01-kickoff.md` in Copilot
   - Work through 7 phases (2-4 hours total)
   - Get PRD
3. **Go to Phase-Gated Delivery**:
   - Read `phase-gated-delivery/METHODOLOGY.md` (15 minutes)
   - Copy templates to project
   - Run `phase-gated-delivery/prompts/00-phase0.md`
   - Validate 8 gates (16 hours validation time over 4-8 weeks)
4. **You have production-ready software**

### Quick Start: Existing PRD
1. Skip Requirement Gathering
2. Go directly to Phase-Gated Delivery
3. Copy PRD to project
4. Run Phase 0 prompt
5. Validate 8 gates

---

## FAQ

**Q: Can I skip Requirement Gathering and go straight to Phase-Gated Delivery?**
A: Yes, if you have a complete PRD from another source. Phase-Gated Delivery is agnostic about where the PRD comes from.

**Q: Can I use Phase-Gated Delivery with a different implementation methodology (not Copilot)?**
A: Yes. The PRD is the contract. You can use any implementation approach; Phase-Gated Delivery just structures the gates.

**Q: What if a gate fails multiple times?**
A: That's a signal. Multiple gate failures suggest the PRD may be unrealistic or the scope is wrong. Use remediation iterations to surface and address root causes.

**Q: Can I skip phases?**
A: No. Phases have dependencies. Phase 1 requires Phase 0 foundation. Phase 5 requires Phases 1-4.

**Q: Can I run multiple phases in parallel?**
A: Not recommended. Phases have dependencies, and gates are sequential.

**Q: What if the PRD changes mid-implementation?**
A: Document the change in a side plan. Update PRD and affected gate criteria. Continue.

---

## See Also

- `requirement-gathering/METHODOLOGY.md` — Full Requirement Gathering guide
- `phase-gated-delivery/METHODOLOGY.md` — Full Phase-Gated Delivery guide
- `COMMIT-POLICY.md` — Commit format rules (used in Phase-Gated Delivery)

---

## Questions or Feedback?

This methodology is designed to be:
- **Reusable** — Use for any software project
- **Composable** — Swap implementations; PRD is the contract
- **Auditable** — Full trail of commits, gates, decisions
- **Minimal interaction** — You only decide at gates
- **Quality-focused** — Gates prevent low-quality progression

If you have suggestions or encounter issues, document them and consider updating these guides for future projects.

---

**You're ready to build software systematically and reliably.**

Start with your idea. Go through Requirement Gathering. Get a PRD. Feed it to Phase-Gated Delivery. Get production software.

Good luck!

