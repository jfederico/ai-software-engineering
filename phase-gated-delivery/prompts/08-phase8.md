# Prompt: Phase 8 - Production Hardening and Release

**Phase**: 8 / 8
**Goal**: Harden for production, automate deployment, document operations.
**Estimated Output**: 10-15 commits, production-ready system.
**Gate**: Gate 8 Validation (**PRODUCTION RELEASE**)

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
Copilot will finalize the system for production.

---

## Copilot Prompt

```
You are an expert DevOps engineer and production systems architect.
I'm at Phase 8: Production Hardening and Release (of 8 phases - FINAL PHASE).

PRD: [INSERT PATH TO PRD]
Project Root: [INSERT PROJECT ROOT]
Phases 0-7 complete (Feature-complete, quality-validated product).

Phase 8 goal: Harden system for production, automate deployment, document operations, release to production.

Tasks for Phase 8:

1. PRODUCTION DOCKER COMPOSE / KUBERNETES
   - Create production-ready docker-compose.yml (or k8s manifests)
   - Production configurations for all services
   - Resource limits and requests
   - Health checks for all services
   - Logging and monitoring setup
   - Test docker-compose up in production config

2. SECRETS MANAGEMENT
   - Remove all hardcoded secrets from codebase
   - Implement secrets management (environment variables, vault, etc.)
   - Document how to set secrets in production
   - Verify no secrets in git history

3. BACKUP AND RESTORE
   - Create backup scripts (data and configuration)
   - Create restore scripts (test restore works)
   - Document backup schedule and retention
   - Test full restore procedure

4. DEPLOYMENT AUTOMATION
   - Create deployment scripts (build, push, deploy)
   - Implement blue-green or rolling deployment strategy
   - Create rollback script and test it
   - Document deployment procedure

5. MONITORING AND LOGGING
   - Implement structured logging
   - Set up monitoring/alerting (Prometheus, Grafana, etc. or equivalent)
   - Health check endpoints operational
   - Dashboard for system status

6. RUNBOOKS AND DOCUMENTATION
   - Create docs/DEPLOYMENT.md (how to deploy to production)
   - Create docs/ROLLBACK.md (how to rollback if needed)
   - Create docs/INCIDENT-RESPONSE.md (common problems and solutions)
   - Create docs/BACKUP-RESTORE.md (backup/restore procedures)
   - Create docs/OPERATIONS.md (day-to-day operations)
   - Create RELEASE-NOTES.md for this version

7. SECURITY HARDENING
   - Run final security scans (SAST, dependency, secrets, container)
   - Fix all critical and high vulnerabilities
   - Review authentication and authorization
   - Verify HTTPS/TLS configured
   - Verify data encryption at rest and in transit

8. PRODUCTION TESTING
   - Smoke test: deploy to staging, verify functionality
   - Load test: verify system handles expected load
   - Failover test: verify graceful degradation
   - Restore test: verify backup/restore works
   - Rollback test: verify rollback procedure works

9. RELEASE CHECKLIST
   - Create PRODUCTION-RELEASE-CHECKLIST.md
   - Security checks passed
   - Performance benchmarks met
   - Documentation complete
   - Runbooks written and tested
   - Team trained
   - Stakeholder approval obtained

COMMIT DISCIPLINE:
- Commit after each major section (secrets, backup, deployment, monitoring, etc.)
- Format: `chore(infra): <improvement>`
- Example: `chore(infra): add production Docker Compose and monitoring`

DOCUMENTATION:
- All runbooks created and tested
- Release notes completed
- Production checklist created

VALIDATION BEFORE GATE:
- Run full security scan (must pass or document exceptions)
- Deploy to staging environment using deployment scripts
- Run smoke tests on staging
- Test backup and restore on staging
- Test rollback on staging
- Run load test if applicable
- Verify all runbooks work as documented
- All tests passing

OUTPUT GATE 8 ASSESSMENT:
- Update CHANGES.md Gate 8 section
- List all commits for Phase 8
- Add security scan results
- Add smoke test results
- Add backup/restore test results
- Add Gate 8 Validation section with:
  - Assessment Date: [today]
  - Status: Pending (PRODUCTION RELEASE CANDIDATE)
  - Note: This is the Production Release point
  - Checklist: security ✓, documentation ✓, testing ✓
- Ask user: "Gate 8 is ready. **This is your PRODUCTION RELEASE**. System is hardened and ready for production. Review CHANGES.md. Approve to release to production?"

PRODUCTION RELEASE:
If approved:
- Deploy to production using deployment scripts
- Monitor for 24 hours for stability
- Publish release notes
- Notify stakeholders and users
- Begin post-launch support
```

---

## What Gets Created

After Phase 8, you will have:
- ✅ Production Docker/Kubernetes configs
- ✅ Secrets management implemented
- ✅ Backup and restore procedures
- ✅ Deployment automation
- ✅ Monitoring and alerting
- ✅ Complete runbooks
- ✅ Security hardened
- ✅ **PRODUCTION READY**

---

## You're Done!

Congratulations! Your software is now production-ready.

**Summary**:
- ✅ Phase 0: Foundation
- ✅ Phase 1: MVP
- ✅ Phase 2: Persistence
- ✅ Phase 3: Async
- ✅ Phase 4: Management UI
- ✅ Phase 5: User UI (Alpha Release)
- ✅ Phase 6: Advanced Features
- ✅ Phase 7: Quality & Evaluation
- ✅ Phase 8: Production Hardening & Release

**Next**: Monitor production, gather user feedback, plan v2 features.

