# Phase-Gated Delivery: Commit Policy Template

Copy this file to your project root as `COMMIT-POLICY.md` when starting Phase-Gated Delivery.

---

# Project Commit Message Policy

This document defines the standard commit message format and CI/CD enforcement rules for this project.

---

## Commit Message Format

All commits must follow the Conventional Commits standard:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Type
Required. One of:
- **feat**: A new feature or capability
- **fix**: A bug fix or correction
- **refactor**: Code restructuring without behavior change
- **chore**: Build, dependency, configuration, or tooling changes
- **docs**: Documentation, runbooks, or comment-only changes
- **test**: Test code or test infrastructure changes
- **perf**: Performance improvement

### Scope (Optional)
Specifies what part of the system is affected. Examples:
- `core-feature`: Primary feature
- `api`: API endpoints
- `ui`: User interface
- `db`: Database or models
- `tests`: Test infrastructure
- `gate-X`: Fix for gate X failure (for remediation work)

Gate-specific commits use `gate-X` scope (e.g., `fix(gate-1): ensure citations present`).

### Subject
- Imperative mood ("add" not "added" or "adds")
- Do not capitalize first letter
- Do not end with a period
- Limit to 50 characters
- Clear and specific

Good examples:
- `fix: handle missing document metadata gracefully`
- `refactor: extract embedding service to provider adapter`
- `docs: add backup and restore procedures`

### Body (Optional)
- Explain **what** and **why**, not **how**.
- Wrap at 72 characters.
- Separate from subject with blank line.
- Use bullet points for multiple changes.

### Footer (Optional)
- Link related issues: `Closes #123`, `Fixes #456`
- Link related PRs: `Related-to: PR-789`
- Breaking changes: `BREAKING CHANGE: description`

---

## Special Commit Types

### Phase Start Commits
```
chore: start phase N <PHASE_NAME>

Initiating Phase N: <PHASE_NAME>
- Scope: <brief description>
- Gate: <gate number and criteria>
```

### Gate Assessment Commits
```
chore(gate-X): gate X assessment complete

All acceptance criteria evaluated.
Assessment stored in CHANGES.md for user review.
Awaiting user validation: Approved / Rejected.
```

### Remediation Commits
```
fix(gate-X): <specific fix>
refactor(gate-X): <refactoring for gate fix>
```

### Documentation Commits
```
docs: <document what changed>
```

### Changelog Commits
```
chore: update CHANGES.md with phase X commits
```

---

## Commit Frequency Guidelines

### Minimum Commits Per Phase
- 1 commit: Phase scaffold
- 2-5 commits: Core implementation
- 1 commit: Tests and validation
- 1 commit: Documentation updates
- **Minimum per phase: 5 commits**

### When to Create New Commits
- Each meaningful unit of work (not too granular, not too coarse).
- After tests pass for a feature.
- After documentation is updated.
- After a significant refactor or fix.

---

## CI/CD Enforcement

### Commit Message Linting
CI will enforce:
- Valid type (`feat|fix|refactor|chore|docs|test|perf`).
- Lowercase subject.
- Subject length <= 50 characters.
- No period at end of subject.
- If scope is used, it must be in the allowed list.

### Invalid Commits Will Be Rejected
```
✗ `FIX: handle edge case`  (capitalized type)
✗ `feat: add feature.`  (period at end)
✗ `feat(foo): this is a very long subject that exceeds 50 chars`
✓ `fix(core-feature): handle missing input gracefully`
```

### Gate Commits Must Include Scope
Gate fix/refactor commits must use `gate-X` scope:
```
✗ `fix: update validation logic`  (could be gate-related)
✓ `fix(gate-1): update validation logic to include citations`
```

---

## Integration with CHANGES.md

After each phase-level merge, automation runs:
```
scripts/changelog-update.sh
```

This script:
1. Extracts commits since last phase marker.
2. Parses commit type, scope, and subject.
3. Appends formatted list to CHANGES.md under the phase.
4. Commits the CHANGES.md update.

---

## Examples

### Example 1: New Feature
```
feat(core-feature): implement document upload with OCR support

Users can now upload documents and OCR is automatically applied to scanned PDFs.

- Detect image-heavy PDFs before text extraction
- Run OCRmyPDF + Tesseract on scanned pages
- Preserve page mapping in chunk metadata

Closes #78
```

### Example 2: Bug Fix
```
fix(api): prevent infinite loop in circular metadata references

When chunk metadata contains self-referential IDs, retriever would hang.
Now validates metadata structure before indexing.

Fixes #42
```

### Example 3: Gate Remediation
```
fix(gate-1): ensure all answers include source citations

Gate 1 was rejected due to missing citations.
Now enforces citation presence in answer composition.

- Add citation validation in answer composer
- Update prompt to require explicit citation blocks
- Add citation presence check in tests

Closes gate remediation for Gate 1
```

---

## Violations and Corrections

If a commit violates this policy:
1. CI will reject the PR.
2. Author must amend commit: `git commit --amend`
3. Force push with caution: `git push --force-with-lease origin branch`

---

