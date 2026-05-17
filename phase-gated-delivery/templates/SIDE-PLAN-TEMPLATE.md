# Phase-Gated Delivery: Side Plan Template

Copy this template to `docs/side-plans/SP-<id>-<short-title>.md` when a deviation is discovered during implementation.

---

# SP-[ID] [Short Title]

## Overview
**Issue**: [What problem was discovered or what assumption failed?]
**Impact**: [Which phases and gates are affected?]
**Status**: Proposed | Approved | In Progress | Deferred | Superseded | Completed

**Created**: [DATE]
**Approved By**: [NAME]
**Approval Date**: [DATE, if approved]

---

## Deviation Details

### Root Cause
[Why did the planned approach not work?]
- Was it a technical constraint?
- Was it a dependency issue?
- Was it a design assumption that was wrong?
- Was it a security or privacy risk?
- Was it scope creep or effort underestimation?

### Scope Impact
- Phases affected: [Phase N, Phase N+1, ...]
- Gates affected: [Gate N, Gate N+1, ...]
- Acceptance criteria changed: [Yes/No, list if changed]

### Current Constraint or Limitation
[Describe the technical, operational, or policy constraint preventing the original plan]

---

## Options Considered

### Option A: [Name]
**Approach**: [Detailed description]
**Pros**:
- Pro 1
- Pro 2

**Cons**:
- Con 1
- Con 2

**Effort**: [Rough estimate]
**Risk**: [High/Medium/Low and rationale]

### Option B: [Name]
**Approach**: [Detailed description]
**Pros**:
- Pro 1
- Pro 2

**Cons**:
- Con 1
- Con 2

**Effort**: [Rough estimate]
**Risk**: [High/Medium/Low and rationale]

### Option C: [Name]
[Repeat structure]

---

## Chosen Path

**Selected Option**: [Option A/B/C]

**Rationale**: [Why this option was chosen]

**Implementation Path**:
- [Step 1]
- [Step 2]
- [Step 3]

**Timeline Impact**: [Does this delay any gates? By how much?]

---

## Decision: Covered Later vs. Immediate Divergence

**Decision**: This deviation will be [covered later in a future phase / diverge now from the planned path]

### If Covered Later
**Deferred Until**: [Phase N or gate X]
**Reason**: [Why deferral is acceptable]
**Risk of Deferral**: [Technical debt, rework required, complexity introduced, etc.]
**Mitigation**: [How will we track this deferred work?]

### If Immediate Divergence
**Branch**: [e.g., `SP-001-vector-db-swap`]
**Related Side Plans**: [Any other SPs that depend on or precede this one]
**Re-alignment Plan**: [How will we re-align with the original plan after this divergence resolves?]

---

## Security and Compliance Notes
[Any security, privacy, or compliance implications of this deviation?]

---

## Testing and Validation Strategy
[How will we validate that the chosen path works?]
- Test 1
- Test 2
- Acceptance criteria for this deviation

---

## Follow-Up Tasks
- [ ] Task 1
- [ ] Task 2
- [ ] Document any permanent changes to docs/architecture.md or docs/requirements.md
- [ ] Update docs/implementation-plan.md if deviation becomes permanent

---

## Reference Links
- Related issue tracker: [Link]
- Related commits: [Hash, Hash, ...]
- Related documentation: [Link]
- Slack thread: [Link, if applicable]

---

## History
| Date | Status | Notes |
|------|--------|-------|
| [DATE] | Proposed | Initial discovery and documentation |
| [DATE] | Approved | Approval from [NAME] |
| [DATE] | In Progress | Implementation started |
| [DATE] | Completed | Resolution and closure |

---

## Closure Notes
[Once this side plan is resolved, summarize the outcome here. Was the divergence temporary or permanent? What was learned?]

