# Phase-Gated Delivery Methodology

## Overview

This methodology automates the implementation of software projects through 8 phased gates, with minimal user interaction and maximum quality control.

**Phase-Gated Delivery is an implementation methodology** that assumes a PRD (Product Requirements Document) already exists. It takes a PRD as input and produces production-ready software through sequential phases, each ending with a user validation gate.

---

## Prerequisites

Before starting Phase-Gated Delivery:
1. ✅ PRD exists and is finalized (from Requirement Gathering & Documentation methodology).
2. ✅ PRD includes functional requirements, success metrics, constraints, and architecture direction.
3. ✅ Team and stakeholders understand the PRD and are committed to the scope.
4. ✅ Infrastructure (repo, CI/CD, hosting environment) is ready.

---

## Core Principles

1. **Phase-Gated Progression**: Each phase ends with a user validation gate. No phase advances without approval.
2. **Automated Execution**: Copilot automates implementation within phases. You validate at gates only.
3. **Committed Documentation**: Every commit tracked in CHANGES.md. Full audit trail maintained.
4. **Deviation Capture**: Blockers and discoveries are captured as side plans, not hidden.
5. **Quality Gates**: Security, testing, and evaluation built into every phase.

---

## The 8 Phases

| Phase | Goal | Gate | User Decision |
|-------|------|------|---------------|
| **0** | Foundation & Tooling | Gate 0 | Approve dev baseline |
| **1** | Core Feature MVP | Gate 1 | Approve MVP works |
| **2** | Data Persistence | Gate 2 | Approve metadata stable |
| **3** | Async Operations | Gate 3 | Approve background jobs reliable |
| **4** | Management Interface | Gate 4 | Approve admin UI functional |
| **5** | User-Facing Interface | Gate 5 | **Approve Alpha Release** |
| **6** | Advanced Features | Gate 6 | Approve secondary features |
| **7** | Production Hardening | Gate 7 | Approve evaluation metrics met |
| **8** | Release & Deploy | Gate 8 | **Approve Production Release** |

---

## User Interaction Model

### Only at Gates
- You review a gate assessment document.
- You make a binary decision: **Approved** or **Rejected**.
- If approved → next phase starts automatically.
- If rejected → focused remediation branch opens.

### Gate Assessment Includes
- Acceptance criteria checklist
- Test results and metrics
- Security scan results
- Linked commits and deliverables
- Gate-specific questions for you

### Remediation Workflow
If you reject a gate:
1. Specify what failed.
2. Copilot creates `gate-phase-X-remediation` branch.
3. Focused fixes are applied.
4. Once ready, you re-validate (same gate, updated assessment).
5. Cycle repeats until gate passes.

---

## Execution Strategy

### For Each Phase:

1. **Copilot develops** all tasks in the phase.
2. **Commits tracked** automatically in CHANGES.md.
3. **Tests run** and results captured.
4. **Gate assessment** generated with checklists and metrics.
5. **You review** and validate (approve or reject).

### Commit Discipline

Every commit follows Conventional Commits format:
```
feat(scope): description
fix(scope): description
refactor(scope): description
chore(scope): description
docs: description
```

Example: `feat(retrieval): add keyword search alongside vector search`

Commits are automatically captured in CHANGES.md per phase.

### Phase Remediation

If a gate is rejected:
- Branch created: `gate-phase-X-remediation`
- Fixes committed with `fix(gate-X):` prefix
- Development continues ONLY in remediation branch
- Once approved, branch merges and phase advances

---

## Phase Details (High-Level)

### Phase 0: Foundation and Tooling
**Goal**: Create development baseline and automation hooks.
**Includes**: Django/framework setup, Docker, CI pipeline, scripts, environment templates.
**Gate 0**: Project structure, CI working, docs validating.

### Phase 1: Core Feature MVP
**Goal**: Prove the main value proposition works end-to-end.
**Includes**: Core feature implementation based on PRD's primary use case.
**Gate 1**: MVP works, core feature delivers value, tests pass.

### Phase 2: Data Persistence
**Goal**: Move from in-memory to persistent storage.
**Includes**: Database schema, migration framework, idempotent operations.
**Gate 2**: Data persists, migrations clean, no data loss on restart.

### Phase 3: Async Operations
**Goal**: Move heavy operations to background.
**Includes**: Job queue setup (Celery/Redis), async task handling, job monitoring.
**Gate 3**: Jobs process reliably, failures retry safely, queue health visible.

### Phase 4: Management Interface
**Goal**: Enable operational management without CLI.
**Includes**: Admin/management views for core resources, basic auth.
**Gate 4**: Collection/document/job management via UI, status visible.

### Phase 5: User-Facing Interface
**Goal**: Deliver user-facing product (**Alpha Release Point**).
**Includes**: Chat/interaction interface, visualization of results.
**Gate 5**: User can interact, get results, understand source evidence.

### Phase 6: Advanced Features
**Goal**: Enhance based on PRD's secondary requirements.
**Includes**: Domain profiles, advanced retrieval, configurable behavior.
**Gate 6**: Advanced features working, no regression in core.

### Phase 7: Evaluation and Quality
**Goal**: Measure and harden quality.
**Includes**: Evaluation framework, quality metrics, refinement.
**Gate 7**: Quality metrics pass threshold, evaluation reproducible.

### Phase 8: Production Hardening
**Goal**: Ready for production (**Production Release Point**).
**Includes**: Security hardening, deployment automation, runbooks, backup/restore.
**Gate 8**: Security scans clean, deployment tested, runbooks verified.

---

## How Phases Map to PRD

### Phase 0
- Uses: Tech stack preferences from PRD
- Produces: Development baseline

### Phase 1
- Uses: Primary use case, core functional requirements from PRD
- Produces: MVP implementation

### Phases 2-4
- Uses: Non-functional requirements (persistence, reliability, scalability) from PRD
- Produces: Operational foundation

### Phase 5
- Uses: User personas, use cases, UI/UX preferences from PRD
- Produces: **Alpha Release** for user testing

### Phases 6-7
- Uses: Secondary functional requirements, success metrics from PRD
- Produces: Full-featured, measured product

### Phase 8
- Uses: Constraints, compliance, deployment model from PRD
- Produces: **Production Release**

---

## Gate Validation Framework

Each gate assessment includes:

### 1. Acceptance Criteria Checklist
From the PRD and phase definition.
Each criterion has a status: ✅ Pass / ❌ Fail / ⚠️ Partial / ⏸️ Deferred

### 2. Test Results
- Unit tests: coverage %
- Integration tests: pass/fail
- Manual test results: details

### 3. Security Scan Results
- SAST (code scanning)
- Dependency vulnerabilities
- Secret scanning
- Container image scanning

### 4. Metrics and Quality
- Performance benchmarks (if applicable)
- Code quality scores
- Documentation completeness

### 5. Linked Artifacts
- Commits since last gate
- Code reviews and approvals
- Related side plans

### 6. Gate-Specific Questions
Unique questions for each phase (example: "Are all API endpoints documented?")

---

## Remediation Process

### Rejection Triggers

You reject a gate when acceptance criteria are NOT met:
- Tests failing
- Security issues
- Missing functionality
- Performance below threshold
- Documentation incomplete

### Remediation Branch

```
git checkout -b gate-phase-X-remediation origin/main
```

Copilot creates this automatically. All fixes go here.

### Remediation Commits

```
fix(gate-1): ensure all answers include citations
fix(gate-1): fix API response format validation
refactor(gate-1): improve error messages
```

### Re-Validation

Once fixes are ready:
1. You re-validate the same gate
2. Assessment regenerated with new results
3. Same decision: Approved or Rejected

### Merge

When gate passes:
```
git checkout main
git merge gate-phase-X-remediation
git tag gate-X-approved
```

Next phase auto-starts.

---

## Success Definitions

### MVP Success (End of Phase 2, Gate 2)
- Core feature works end-to-end
- Data persists correctly
- Grounded answers delivered with sources (if applicable)
- No critical bugs

### Alpha Success (End of Phase 5, Gate 5)
- User interface functional
- User can accomplish primary use case
- Results are understandable
- Minimal user friction

### Production Success (End of Phase 8, Gate 8)
- All quality metrics passed
- Security scans clean
- Deployment and rollback procedures verified
- Runbooks complete and tested
- Team trained and ready

---

## Documentation Integration

### CHANGES.md (Auto-Generated)
Tracks every phase and gate decision.
Updated automatically after phase completion.
Serves as audit trail and progress log.

### Side Plans
When deviations are discovered, documented as side plans:
- `docs/side-plans/SP-001-vector-db-swap.md`
- Linked in CHANGES.md
- Tracked through completion

### Commit Messages
Every commit is structured for traceability:
```
feat(phase-1): implement core feature X
fix(gate-1): add missing citation
chore: update CHANGES.md with phase 1 commits
```

---

## Timeline Expectations

- **Phase 0**: 1-2 commits (scaffold)
- **Phases 1-8**: 3-10 commits per phase
- **Total**: 30-90 commits depending on scope

**Estimated durations** (assuming full-time Copilot):
- Phase 0: 1-2 days
- Phases 1-8: 3-7 days each
- **Total**: 4-8 weeks (assuming minimal gate rejections)

**With gate rejections** (expect 0-2):
- Add 2-5 days per rejection for remediation
- **Total**: 4-10 weeks

---

## Key Files and Artifacts

| File | Purpose | Auto-Generated |
|------|---------|---|
| CHANGES.md | Gate tracking, commit log | ✅ Yes |
| COMMIT-POLICY.md | Commit format rules | ⚪ Template |
| AUTOMATION.md | User interaction guide | ⚪ Template |
| docs/implementation-plan.md | Full phase details | ⚪ Template |
| docs/side-plans/*.md | Deviation tracking | ❌ Manual |
| docs/architecture.md | System design (from Phase 0) | ❌ Generated in Phase 0 |

---

## Deviations and Side Plans

During implementation, discoveries happen:
- Technical constraints prevent planned approach
- Dependencies fail or change
- Assumptions prove wrong
- Scope pressure emerges

### Handling Deviations

1. **Detect**: During phase work
2. **Document**: Create side plan in `docs/side-plans/SP-NNN-title.md`
3. **Decide**: Options, chosen path, implications
4. **Track**: Link in CHANGES.md, commit with side plan reference
5. **Resolve**: Update main plan if divergence becomes permanent

### Side Plan Template

Located in `templates/SIDE-PLAN-TEMPLATE.md`
Includes: issue, options, chosen path, timeline impact, closure notes.

---

## Next Steps

1. **Finalize PRD** (from Requirement Gathering)
2. **Review Phase-Gated Delivery METHODOLOGY.md** (this document)
3. **Start Phase 0** using `prompts/00-phase0.md`
4. **Copilot implements** Phase 0 fully
5. **You review** Gate 0 assessment in CHANGES.md
6. **Approve or Reject** to advance or remediate

---

## Getting Help

- **How do gates work?** → See AUTOMATION.md
- **What's the full plan?** → See docs/implementation-plan.md
- **How to document deviations?** → See templates/SIDE-PLAN-TEMPLATE.md
- **Commit format?** → See COMMIT-POLICY.md
- **Phase details?** → See prompts/0N-phaseN.md

---

## FAQ

**Q: Can I skip phases?**
A: No. Phases have dependencies. Each builds on prior work.

**Q: What if a gate fails?**
A: Remediation branch opens. Fix, re-validate, repeat until gate passes.

**Q: What if scope changes?**
A: Document in side plan. Scope changes may impact timeline/gates.

**Q: How long does each phase take?**
A: Depends on scope. Expect 3-7 days per phase with full-time Copilot.

**Q: Can I use this for agile/iterative development?**
A: Yes. Phases can be shorter/narrower. Each phase gates functionality.

**Q: What if I reject every gate?**
A: That's a signal to revisit PRD scope/timeline. Gates expose misalignment early.

---

## See Also

- `prompts/` — Phase-by-phase implementation prompts
- `templates/` — Reusable templates for CHANGES, side plans, policies
- Requirement Gathering methodology — For PRD creation

