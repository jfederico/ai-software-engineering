# Prompt: Phase 0 - Foundation and Tooling

**Phase**: 0 / 8
**Goal**: Create development baseline, CI/CD, and automation scaffolding.
**Estimated Output**: 5-10 commits, working dev environment, CI green.
**Gate**: Gate 0 Validation

---

## How to Use This Prompt

Copy the **Copilot Prompt** section below into your Copilot chat.
Provide the PRD path when asked.
Copilot will scaffold your project foundation.

---

## Copilot Prompt

```
You are an expert software architect and automation engineer.
I'm implementing a new software project using Phase-Gated Delivery methodology.

I'm at Phase 0: Foundation and Tooling.
My PRD is at: [INSERT PATH TO PRD]
My project directory is: [INSERT PROJECT ROOT]

Phase 0 goal: Create development baseline, CI/CD, Docker environment, and automation scripts.

Tasks for Phase 0:

1. PROJECT STRUCTURE
   - Initialize the project in [PROJECT ROOT]
   - Create app boundaries based on architecture (if PRD specifies architecture preferences)
   - Create directory structure: docs/, scripts/, infra/, .github/workflows/, tests/
   - Create a README with setup instructions

2. FRAMEWORK SETUP
   - Choose backend framework based on PRD tech stack preferences (Django, FastAPI, etc.)
   - Create minimal app skeleton with placeholder routes/views
   - Create requirements.txt or equivalent with core dependencies
   - Ensure project can start without errors

3. DOCKER SETUP
   - Create Dockerfile for main application
   - Create docker-compose.yml for local development
   - Include at least: app service, db service (PostgreSQL recommended)
   - Create .dockerignore and docker-compose.override.example.yml
   - Verify docker-compose up works without errors

4. ENVIRONMENT CONFIGURATION
   - Create .env.example with all required environment variables
   - Document what each variable does
   - Create env config strategy (environment files, secrets management approach)

5. CI/CD PIPELINE
   - Create .github/workflows/ci.yml (or equivalent for your platform)
   - CI should run:
     - Lint checks (flake8, black, or equivalent)
     - Unit tests (pytest or equivalent)
     - Documentation validation
   - Ensure CI passes on main

6. AUTOMATION SCRIPTS
   - Create scripts/bootstrap-dev.sh (setup local environment)
   - Create scripts/lint.sh (run code quality checks)
   - Create scripts/test.sh (run unit tests)
   - Create scripts/build-images.sh (build Docker images)
   - Create scripts/docs-validate.sh (validate markdown docs)
   - All scripts should be executable and tested

7. DOCUMENTATION
   - Create docs/architecture.md (high-level system design based on PRD)
   - Create docs/data-model.md (database schema overview if applicable)
   - Create docs/SETUP.md (local development setup instructions)
   - Copy COMMIT-POLICY.md, AUTOMATION.md, CHANGES.md templates to project root
   - Customize CHANGES.md for this project

8. BASIC REQUIREMENTS FROM PRD
   - Review PRD and extract any tech stack preferences
   - Ensure chosen technologies align with PRD constraints
   - Document any deviations

COMMIT DISCIPLINE:
- Commit after each major section (framework, docker, CI, scripts, etc.)
- Use format: `chore(<scope>): description` or `feat: description`
- Example: `chore: setup Django project skeleton`
- Keep commits focused and descriptive

VALIDATION:
- Run scripts/lint.sh and ensure it passes
- Run scripts/test.sh (should pass even if tests are minimal)
- Run scripts/docs-validate.sh and ensure it passes
- Run docker-compose up and verify app starts
- Verify .github/workflows/ci.yml passes on a test commit

OUTPUT GATE 0 ASSESSMENT:
After all tasks complete, generate a gate assessment:
- Copy CHANGES-TEMPLATE.md to CHANGES.md (if not already done)
- Fill in Gate 0 section with acceptance criteria
- List all commits since phase start
- Add Gate 0 Validation section with:
  - Assessment Date: [today]
  - Status: Pending
  - Awaiting user approval
- Save CHANGES.md

FINAL STEP:
Output a summary:
- List all commits made
- Confirm CI is green
- Confirm docker-compose starts without errors
- Confirm all scripts run successfully
- Note any PRD assumptions or tech choices made
- Ask user: "Gate 0 is ready for validation. Review CHANGES.md Gate 0 section. Approve or reject?"
```

---

## What Gets Created

After Phase 0, you will have:
- ✅ Project structure matching scope
- ✅ Django (or chosen framework) app scaffold
- ✅ Docker Compose dev environment
- ✅ CI/CD pipeline (GitHub Actions or equivalent)
- ✅ Automation scripts
- ✅ Documentation framework
- ✅ Working dev environment (docker-compose up)
- ✅ CI passing on main

---

## Next Step

Once Gate 0 is approved, move to Phase 1: `01-phase1.md`

