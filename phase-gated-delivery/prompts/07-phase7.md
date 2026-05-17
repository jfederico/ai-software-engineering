# Prompt: Phase 7 - Evaluation and Quality Gates

**Phase**: 7 / 8
**Goal**: Measure quality, validate success metrics, harden reliability.
**Estimated Output**: 5-10 commits, evaluation framework and quality metrics.
**Gate**: Gate 7 Validation

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
Reference PRD success metrics.
Copilot will build evaluation framework.

---

## Copilot Prompt

```
You are an expert quality engineer and data analyst.
I'm at Phase 7: Evaluation and Quality Gates (of 8 phases).

PRD: [INSERT PATH TO PRD]
Project Root: [INSERT PROJECT ROOT]
Phases 0-6 complete (Feature-rich product ready).

Phase 7 goal: Measure quality, validate success metrics from PRD, ensure product meets standards.

From my PRD:
- Success metrics: [Copy from PRD section 8]
- Non-functional requirements: [Copy quality requirements from PRD]
- Success definition: [What does success look like?]

Tasks for Phase 7:

1. EVALUATION FRAMEWORK
   - Create test suite that measures success metrics
   - Evaluate PRD success metrics quantitatively
   - Create test data (representative samples)
   - Create evaluation scripts that run tests and report results
   - Document evaluation process

2. QUALITY METRICS
   - Code quality: coverage, complexity, maintainability
   - Performance: latency, throughput, resource usage
   - Reliability: error rates, recovery time, uptime
   - Security: known vulnerabilities, security practices
   - User experience: usability, responsiveness

3. BASELINE BENCHMARKS
   - Run evaluation against PRD success metrics
   - Document results
   - Compare against targets from PRD
   - Identify any gaps

4. PERFORMANCE TESTING
   - Load testing (simulate expected user load)
   - Stress testing (find breaking points)
   - Endurance testing (stability over time)
   - Document performance characteristics

5. RELIABILITY TESTING
   - Test system under failure conditions
   - Verify graceful degradation
   - Verify recovery
   - Chaos engineering (if applicable)

6. SECURITY VALIDATION
   - Run security scans (SAST, dependency check, secret scan)
   - Review authentication and authorization
   - Verify data protection (encryption, privacy)
   - Document security posture

7. OPTIONAL IMPROVEMENTS
   - Based on evaluation, recommend optimizations
   - Implement quick wins if they improve metrics
   - Document deferred improvements (for post-launch)

COMMIT DISCIPLINE:
- Commit after evaluation framework, after benchmarks, after security scans
- Format: `feat(eval): <capability>` or `test(eval): <test>`
- Example: `feat(eval): add performance benchmark suite`

DOCUMENTATION:
- Create docs/EVALUATION.md documenting methodology and results
- Document success metrics and how they were measured
- Document quality thresholds and whether they were met
- Document performance characteristics

VALIDATION BEFORE GATE:
- Run complete evaluation suite
- Document all results
- Compare against PRD targets
- Verify security scans are clean
- Verify performance meets expectations
- All tests passing

OUTPUT GATE 7 ASSESSMENT:
- Update CHANGES.md Gate 7 section
- List all commits for Phase 7
- Add evaluation results and metrics
- Add security scan results
- Add performance benchmarks
- Add Gate 7 Validation section with:
  - Assessment Date: [today]
  - Status: Pending
  - Include: "All PRD success metrics measured and documented"
- Ask user: "Gate 7 is ready. Quality is measured and validated. Review CHANGES.md. Approve or reject?"
```

---

## What Gets Created

After Phase 7, you will have:
- ✅ Evaluation framework
- ✅ Quality metrics measured
- ✅ PRD success metrics validated
- ✅ Performance benchmarks
- ✅ Security validation complete
- ✅ Reliability verified

---

## Next Step

Once Gate 7 is approved, move to Phase 8: `08-phase8.md` (FINAL PRODUCTION RELEASE)

