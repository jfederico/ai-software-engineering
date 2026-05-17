# Phase-Gated Delivery: User Automation Guide Template

Copy this file to your project root as `AUTOMATION.md` when starting Phase-Gated Delivery.

---

# Project: Automated Phase-Gated Implementation
## User Interaction Guide

This guide explains how the automated Copilot-driven implementation works and what you need to do.

---

## Quick Summary

**You have exactly 8 validation gates. That is your only interaction.**

Copilot automates everything else. Each gate is a binary decision:
- ✅ **Approved** → Next phase starts automatically.
- ❌ **Rejected** → Focused remediation branch opens until fixed.

---

## Timeline

The automated system will proceed through 8 phases sequentially. Each phase ends with a gate validation request.

| Gate | Phase | Deliverable | Your Decision |
|------|-------|-------------|--------------|
| Gate 0 | Foundation & Tooling | Development baseline | Approve / Reject |
| Gate 1 | Core Feature MVP | Primary feature works | Approve / Reject |
| Gate 2 | Data Persistence | Data storage stable | Approve / Reject |
| Gate 3 | Async Operations | Background jobs working | Approve / Reject |
| Gate 4 | Management Interface | Admin/ops UI | Approve / Reject |
| **Gate 5** | **User-Facing Interface** | **ALPHA RELEASE** | **Approve / Reject** |
| Gate 6 | Advanced Features | Secondary features | Approve / Reject |
| Gate 7 | Evaluation & Quality | Quality metrics met | Approve / Reject |
| Gate 8 | Production Hardening | Ready to release | **APPROVE FOR PRODUCTION** |

**Alpha Release Point**: Gate 5 (User-Facing Interface)
**Production Release Point**: Gate 8 (Production Hardening)

---

## How It Works

### Before Each Gate Assessment
1. Copilot completes a full phase of work.
2. All commits are merged to a feature branch.
3. Tests, security scans, and evaluation run automatically.
4. A **gate assessment document** is generated.

### During Gate Validation
1. You receive a notification: "**Gate X Ready for Review**"
2. Assessment document is in [CHANGES.md](./CHANGES.md) under the phase section.
3. Assessment includes:
   - Checklist of acceptance criteria (all items checked or noted)
   - Test results and metrics
   - Security scan results
   - Linked commits and deliverables
4. You review and decide.

### After Gate Validation

**If You Approve** ✅
- Copilot tags the commit as `gate-X-approved`.
- Next phase begins automatically.
- Entry recorded in CHANGES.md with approval date.

**If You Reject** ❌
- Specify what failed (e.g., "answers missing citations", "UI unresponsive").
- Copilot creates a **focused remediation branch**: `gate-phase-X-remediation`.
- Development continues **only** in remediation branch.
- All fixes are grouped and tracked together.
- Once remediation is ready, you re-validate the same gate.
- Cycle repeats until gate passes.

---

## What You Review at Each Gate

### Gate 0: Foundation
- Project structure matches scope.
- Docker Compose dev environment works.
- CI pipeline is green.
- Scripts directory scaffolded and tested.

### Gate 1: Core Feature MVP
- Primary feature (from PRD) works end-to-end.
- Core value proposition delivered.
- Minimal feature set functioning.
- No critical bugs.

### Gate 2: Data Persistence
- Database tables exist and are indexed.
- Data persists across restarts.
- No duplicate data on re-operation.
- Migrations run clean.

### Gate 3: Async Operations
- Background jobs process reliably.
- Failed jobs retry safely.
- Queue health monitored.
- No data loss on restart.

### Gate 4: Management Interface
- Core resources can be managed via web.
- CRUD operations functional.
- Status visible without CLI.
- Basic auth working.

### Gate 5: User-Facing Interface (Alpha)
- User-facing interface functional.
- User can accomplish primary use case.
- Results are understandable.
- Minimal UI friction.
- **Alpha Release Ready**

### Gate 6: Advanced Features
- Secondary features from PRD implemented.
- No regression in core.
- Configurable behavior working.
- Power-user workflows supported.

### Gate 7: Evaluation & Quality
- Evaluation framework runs.
- Quality metrics from PRD measured.
- Success thresholds met.
- Performance acceptable.

### Gate 8: Production Ready
- Production stack passes all tests.
- Security scans clean.
- Backup/restore verified.
- Deployment scripts tested.
- Runbooks complete.
- **Production Release Ready**

---

## What Happens in CHANGES.md

[CHANGES.md](./CHANGES.md) is your **audit trail** and **gate tracking log**.

For each phase:
- Commits are listed automatically.
- Gate assessment checklist is shown.
- Your approval/rejection decision is recorded.
- If rejected, remediation branch and feedback are logged.

Example entry:

```
## Phase 1: Core Feature MVP

### Commits
- feat(core-feature): implement primary feature
- test(core-feature): add integration tests
- fix(core-feature): handle edge case

### Gate 1 Validation
**Assessment Date**: 2026-06-14
**Assessed By**: You
**Status**: Approved
**Feedback**: -
```

---

## If You Reject a Gate: Remediation Workflow

1. **Rejection**: You respond with specific feedback.
   - "Core feature is too slow."
   - "UI is not responsive on mobile."
   - "Database migrations failing."

2. **Remediation Branch Created**: `gate-phase-X-remediation`

3. **Fixes are Applied**: 
   - Work is committed to remediation branch only.
   - Commits use `fix(gate-X):` or `refactor(gate-X):` prefix.
   - Example: `fix(gate-1): optimize query performance to < 5 seconds`

4. **Re-Validation**: Once fixes are ready, you re-validate.
   - Same gate assessment checklist.
   - Updated metrics and test results.
   - Decision: Approved or Rejected again.

5. **Approval**: Once gate passes, remediation merges and phase advances.

---

## Side Plans (Discoveries During Implementation)

If Copilot discovers a blocker or constraint during implementation:
- A **side plan** is created (e.g., `docs/side-plans/SP-001-db-change.md`).
- Side plan documents the issue, options, chosen path, and timeline impact.
- CHANGES.md references any active side plans.

---

## Commits and Documentation

Every commit follows a standard pattern:
```
feat: add user-facing chat interface
fix: ensure all citations include source document
refactor: extract API logic to service layer
chore: update Docker Compose for production
docs: add deployment runbook
```

These commits are automatically captured in CHANGES.md after each phase.

---

## Key Files to Monitor

| File | Purpose |
|------|---------|
| [CHANGES.md](./CHANGES.md) | Gate decisions, phase progress, remediation tracking |
| [COMMIT-POLICY.md](./COMMIT-POLICY.md) | Commit message format rules |
| [docs/side-plans/](./docs/side-plans/) | Deviations from plan, discovered constraints |

---

## Your Responsibilities

1. **Review gate assessments** when notified.
2. **Approve or reject** with clear feedback.
3. **Approve side plans** if asked (rare).
4. **Monitor CHANGES.md** for progress.
5. **Do not commit directly** to main branch (automation handles this).
6. **Do not manually create branches** (automation handles this).

---

## If Something Goes Wrong

If Copilot gets stuck or produces unexpected behavior:

1. **Check the last commit message** in the active branch. Does it match the expected phase?
2. **Check CHANGES.md** for the last recorded gate assessment.
3. **Check docs/side-plans/** for any deviations logged.
4. **Create an issue** with:
   - Last commit hash
   - Active branch name
   - Gate or phase it's stuck on
   - Error message or unexpected behavior
5. **Manually fix** and document as a side plan if needed.

---

## Timeline Expectations

- Each phase typically produces 5-15 commits.
- Gate assessment takes ~1-2 hours of review.
- Rejected gates result in focused remediation (1-5 days typically).
- Total project time depends on remediation frequency.

**Target**: 4-8 weeks from Phase 0 to production (assuming minimal gate rejections).

---

## Getting Started

1. Start with **Phase 0**.
2. Copilot will bootstrap the project and request **Gate 0 validation**.
3. Review the gate assessment in CHANGES.md.
4. Respond: **Approved** or **Rejected with feedback**.
5. Phase 1 begins automatically after approval.

---

## Questions?

Refer to:
- [COMMIT-POLICY.md](./COMMIT-POLICY.md) for commit format rules.
- [CHANGES.md](./CHANGES.md) for gate assessment checklists.
- [docs/side-plans/](./docs/side-plans/) for deviation process.

