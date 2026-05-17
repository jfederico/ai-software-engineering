# Prompt 4: Functional and Non-Functional Requirements

**Phase**: 4 / 7
**Goal**: Formalize what the software must do and how it must behave.
**Estimated Time**: 30-45 minutes
**Output**: Functional requirements list, non-functional requirements, acceptance criteria.

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
This phase transforms use cases into concrete, testable requirements.
Think about behavior, not just features.

---

## Copilot Prompt

```
We're in Phase 4: Functional and Non-Functional Requirements.
We've defined users and how they use your software.
Now we'll translate that into specific, testable requirements.

There are two types of requirements:
- FUNCTIONAL: What the software does (features, behavior)
- NON-FUNCTIONAL: How well it does it (performance, reliability, security, usability)

Ask these questions one at a time:

1. "For your PRIMARY use case from Phase 3, 
   what specific functions must the software provide?
   
   Think about each step in the workflow and make it testable.
   
   Format: 'The system shall [action] so that [user value]'
   
   Examples:
   - 'The system shall accept PDF files up to 100MB'
   - 'The system shall extract text from uploaded documents'
   - 'The system shall allow users to ask questions and return answers with sources'
   - 'The system shall display confidence levels for answers'
   
   List 8-15 functional requirements."

2. "For each major feature (like 'search', 'upload', 'export'), 
   what does 'success' or 'done' look like?
   
   Make acceptance criteria specific and measurable.
   
   Example:
   Feature: Document Upload
   Acceptance Criteria:
   - User can select multiple files at once
   - System accepts PDF, DOCX, MD, TXT files
   - System rejects files larger than 100MB with clear error message
   - Upload progress is visible
   - User can see list of uploaded documents
   
   Provide acceptance criteria for your top 3-5 features."

3. "Now think about NON-FUNCTIONAL requirements.
   These are about quality, not just features.
   
   Consider:
   - PERFORMANCE: How fast? 'Typical queries return in < 10 seconds'
   - RELIABILITY: How often should it work? '99.9% uptime'
   - SCALABILITY: How much data? 'Support 1000+ documents, 100 concurrent users'
   - SECURITY: Who can access what? 'All data stays local, no cloud transmission'
   - USABILITY: How easy to use? 'Non-technical users can ingest documents without docs'
   
   For each category, list 1-3 requirements that matter for YOUR software."

4. "Are there integrations or external systems your software must work with?
   (Examples: databases, APIs, authentication systems, payment processors)
   
   If yes:
   - What systems do you integrate with?
   - What data flows in/out?
   - What protocols or formats?
   - What's the criticality (nice-to-have vs essential)?"

5. "What's your primary DEPLOYMENT MODEL?
   - Desktop application (Windows/Mac/Linux)?
   - Web application (browser)?
   - Mobile (iOS/Android)?
   - Self-hosted server?
   - SaaS cloud?
   - Something else?
   
   For each, list technical requirements that flows from that choice."

After I answer all questions, synthesize into:

## Functional Requirements
[Structured list of F1, F2, F3... with 'The system shall...' format]

## Acceptance Criteria
[For top features: specific, measurable acceptance criteria]

## Non-Functional Requirements
[Performance, reliability, security, usability, scalability]

## Integrations
[Systems and data flows if applicable]

## Deployment Model
[Primary delivery method and resulting technical requirements]

Then ask: "Does this feel complete? 
Are there requirements we missed or misunderstood?"

Refine based on feedback.

Confirm: "Phase 4 complete. 
Your functional and non-functional requirements are documented. 
Ready for Phase 5: Constraints when you are."
```

---

## Notes for Better Results

- **Make it testable**: "The system shall be fast" is vague. "The system shall return results in < 5 seconds 99% of the time" is testable.
- **Use stories, not tasks**: Focus on user value, not implementation details.
- **Prioritize**: Not all requirements are equal. Mark critical vs nice-to-have.
- **Non-functional matters**: Security, performance, and reliability often matter as much as features.

---

## What Comes Next

Move to Phase 5: `05-constraints.md`

