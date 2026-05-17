# Requirement Gathering & Documentation Methodology

## Overview

This methodology guides interactive, Copilot-assisted requirement gathering to produce a formal Product Requirements Document (PRD) suitable for downstream implementation methodologies like Phase-Gated Delivery.

The methodology is **interactive and exploratory**, helping users clarify, refine, and formally document their software ideas.

---

## When to Use This Methodology

Use this when:
- You have a software idea but need to crystallize it.
- Requirements are unclear or partially formed.
- You need a formal PRD before starting implementation.
- Stakeholders need to align on scope and success metrics.
- You want reproducible, documented requirements for any implementation methodology.

Do NOT use this when:
- Requirements are already fully documented and locked.
- You're only implementing a pre-approved PRD (use Phase-Gated Delivery directly).

---

## Methodology Phases

The requirement gathering process has 7 interactive phases, each with user dialogue and documentation:

| Phase | Prompt | Goal | User Role |
|-------|--------|------|-----------|
| Phase 1 | 01-kickoff.md | Initial idea capture | Describe what you want to build |
| Phase 2 | 02-scope.md | Scope definition | Define what's in/out and why |
| Phase 3 | 03-users-usecases.md | User and use case mapping | Identify stakeholders and how they use it |
| Phase 4 | 04-requirements.md | Formalize requirements | List functional and non-functional needs |
| Phase 5 | 05-constraints.md | Identify constraints | Budget, timeline, technical limits |
| Phase 6 | 06-review-refine.md | Review and iterate | Spot gaps, resolve contradictions |
| Phase 7 | 07-finalize-prd.md | Finalize and document | Lock PRD and prepare for handoff |

---

## How It Works

### For Each Phase:

1. **Read the phase prompt** (located in `prompts/NN-PHASE-NAME.md`).
2. **Follow the prompt guidance** — Copilot will ask targeted questions.
3. **Provide your responses** — Be as detailed as possible; ambiguity creates rework.
4. **Copilot documents** your input in a working PRD.
5. **Move to next phase** — Or iterate current phase if clarifications needed.

### Documentation as You Go

Each phase updates a working PRD (in the project directory, not this template):
```
<your-project>/
  prd/
    PRD.md (working document, updated each phase)
```

After Phase 7, the PRD is finalized and ready for handoff to implementation.

---

## User Interaction Model

**Format**: Conversational with structured capture.

**Example interaction**:

```
Copilot: "Let's start with your core idea. 
What problem does your software solve?
What's the elevator pitch (one sentence)?"

You: "We're building a local knowledge RAG platform 
that lets anyone ask questions about their document collections 
without sending data to the cloud."

Copilot: "Great. Let me refine that. You said 'local knowledge RAG'. 
Are we building:
a) A framework that others integrate into their apps?
b) A standalone application users run themselves?
c) A SaaS platform they access via web?
Which resonates most?"

You: "Option b — standalone application"

Copilot: "Perfect. I've documented that as the primary delivery model. 
Let's dig into the documents you expect to support..."
```

---

## Key Artifacts

### Input
- Your idea (verbal or rough notes).
- Time budget for gathering (1-3 hours typically).
- Willingness to iterate and clarify.

### Output
- **PRD.md**: Finalized Product Requirements Document (see `templates/PRD-TEMPLATE.md`).
- **PRD is now the contract** for any implementation methodology (Phase-Gated Delivery, etc.).

### PRD Contents
The PRD contains:
1. Product overview and elevator pitch
2. Problem statement
3. Solution overview
4. Target users and personas
5. Use cases and scenarios
6. Functional requirements
7. Non-functional requirements (performance, scalability, etc.)
8. Constraints (timeline, budget, technical, compliance)
9. Success metrics and acceptance criteria
10. Out-of-scope items
11. Risks and assumptions
12. Architecture direction (if known)
13. Future roadmap

---

## Phase Details

### Phase 1: Kickoff (01-kickoff.md)
**Goal**: Capture the core idea clearly.

**Questions**:
- What problem does this software solve?
- Who has the problem (target users)?
- Why is existing software not sufficient?
- What's the core value proposition?

**Output**: Documented problem statement and solution overview.

### Phase 2: Scope (02-scope.md)
**Goal**: Define what's in and out, and why.

**Questions**:
- What are the major features in v1?
- What's explicitly NOT included in v1 (out of scope)?
- Why are those choices?
- Are there secondary features that could wait?

**Output**: Feature list, scope boundaries, rationale.

### Phase 3: Users & Use Cases (03-users-usecases.md)
**Goal**: Understand who uses it and how.

**Questions**:
- Who are the primary users?
- What's their typical workflow?
- What problems do they encounter today?
- How will your software change their workflow?

**Output**: User personas, use case scenarios, workflow diagrams.

### Phase 4: Requirements (04-requirements.md)
**Goal**: Formalize functional and non-functional requirements.

**Questions**:
- What must the software do? (functional)
- What quality attributes matter? (non-functional: performance, reliability, security)
- What integrations or APIs are needed?
- What's the deployment model?

**Output**: Structured requirement lists, acceptance criteria.

### Phase 5: Constraints (05-constraints.md)
**Goal**: Identify real-world limitations.

**Questions**:
- What's the timeline for v1?
- What's the budget or team size?
- Are there technical constraints (languages, platforms)?
- Are there compliance or security mandates?
- What dependencies exist (on other systems, vendors, approvals)?

**Output**: Documented constraints and their implications.

### Phase 6: Review & Refine (06-review-refine.md)
**Goal**: Spot gaps and resolve contradictions.

**Questions**:
- Are there conflicting requirements?
- Are there missing use cases?
- Is the scope realistic given constraints?
- Are success metrics measurable?

**Output**: Clarifications, scope adjustments, refined requirements.

### Phase 7: Finalize PRD (07-finalize-prd.md)
**Goal**: Lock the PRD and prepare for handoff.

**Actions**:
- Final review of all sections.
- Confirm all open questions resolved.
- Set PRD version and sign-off date.
- Prepare for handoff to implementation.

**Output**: Final, signed PRD ready for Phase-Gated Delivery (or other methodologies).

---

## Best Practices

1. **Be honest about unknowns.** If you don't know something, say so. Copilot will help you explore or defer.

2. **Iterate freely.** Phases are not one-way. Go back and revise if later phases reveal issues.

3. **Involve stakeholders.** If multiple people care about the outcome, gather input from each perspective.

4. **Document trade-offs.** When choosing between options, record why you chose one over another.

5. **Use concrete examples.** "Users ask questions about PDFs" is better than "users interact with documents."

6. **Keep requirements testable.** "The system should be fast" is vague; "99% of queries return in < 10 seconds" is testable.

7. **Plan for iteration.** Requirements often evolve. Plan to revisit PRD after Phase 1 of implementation if needed.

---

## Timeline

- **Phase 1**: 15-20 minutes
- **Phase 2**: 20-30 minutes
- **Phase 3**: 30-45 minutes
- **Phase 4**: 30-45 minutes
- **Phase 5**: 15-30 minutes
- **Phase 6**: 30-60 minutes (often requires back-and-forth)
- **Phase 7**: 15-20 minutes

**Total**: 2.5-4 hours of interactive work, spread over 1-2 weeks.

---

## Output Integration

Once PRD is finalized:

1. **Store PRD in project repo** (e.g., `docs/PRD.md`).
2. **Pass to Phase-Gated Delivery**:
   ```
   Run Phase-Gated Delivery with PRD: docs/PRD.md
   ```
3. **Phase-Gated Delivery uses PRD to**:
   - Define architecture and design documents.
   - Set acceptance criteria per phase.
   - Measure success in evaluation gate.
   - Guide scope decisions.

---

## Next Steps

1. **Read the first prompt** in `prompts/01-kickoff.md`.
2. **Run it with Copilot** (copy-paste into Copilot or chat interface).
3. **Capture your responses** in the working PRD.
4. **Move to the next prompt** when Phase 1 is complete.

---

## FAQ

**Q: Can I skip phases?**
A: Not recommended. Each phase builds on prior ones. If earlier phases are done informally, formalize them before moving on.

**Q: What if requirements change mid-way?**
A: Update the PRD. This methodology supports iteration. Document the change and rationale.

**Q: How detailed should the PRD be?**
A: Detailed enough that an independent implementation team could build from it without asking questions. If there are gaps, Phase 6 (Review & Refine) will surface them.

**Q: Can multiple people provide input?**
A: Yes. Gather their perspectives separately, then synthesize in Phase 6 (Review & Refine).

**Q: What if Phase-Gated Delivery doesn't fit my needs?**
A: That's fine. The PRD is implementation-methodology-agnostic. Use it with other methodologies or for internal planning.

---

## See Also
- `templates/PRD-TEMPLATE.md` — The output format for all PRDs.
- `prompts/` — The 7 phase prompts for interactive gathering.
- `../phase-gated-delivery/METHODOLOGY.md` — Next methodology after PRD is complete.

