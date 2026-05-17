# Prompt 5: Constraints - Real-World Limitations

**Phase**: 5 / 7
**Goal**: Identify budget, timeline, technical, and legal constraints.
**Estimated Time**: 15-30 minutes
**Output**: Documented constraints and implications for scope/timeline.

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
Be honest about constraints. They shape realistic scope and timeline.

---

## Copilot Prompt

```
We're in Phase 5: Constraints.
So far we've defined what you want to build.
Now we'll identify REAL-WORLD limitations that affect what's achievable.

Constraints are not failures—they're facts that shape good decisions.

Ask these questions one at a time:

1. "TIMELINE: When do you need v1 to be ready?
   - What's your target launch date?
   - Is this a hard deadline or flexible?
   - What's driving the timeline (market window, stakeholder commitment, other)?
   - Is it 3 months? 6 months? 1 year? Open-ended?"

2. "TEAM & BUDGET: 
   - How many people will build this?
   - What skills do you have (Python, JavaScript, DevOps, etc.)?
   - Are there budget constraints?
   - Is this a side project or full-time focus?
   - Will you hire contractors or use only existing team?"

3. "TECHNICAL CONSTRAINTS:
   - Must it use certain technology stacks or languages?
   - Are there existing systems it must integrate with?
   - Must it run on specific platforms (AWS, on-premises, local only)?
   - Are there performance or resource constraints?
   - Offline vs online requirement?
   
   Examples: 'Must be Python-based', 'Must run on Raspberry Pi', 'Cannot use third-party APIs'"

4. "COMPLIANCE & LEGAL:
   - Are there privacy/compliance requirements? (GDPR, HIPAA, SOX, etc.)
   - Data residency requirements? (must stay in-country, on-device, etc.)
   - Licensing constraints? (open-source, proprietary, etc.)
   - Regulatory approvals needed before launch?
   
   If none, that's fine—just confirm."

5. "DEPENDENCIES:
   - Does your software depend on other systems, services, or approvals?
   - Are there vendor relationships that matter?
   - Do you need approval from stakeholders before launch?
   
   Examples: 'Can't launch without legal approval', 'Depends on cloud partner's API'"

After I answer, synthesize into:

## Timeline Constraint
[Target launch date, flexibility, drivers]

## Team & Budget Constraint
[Resources available, skill set, budget implications]

## Technical Constraints
[Tech stack requirements, integrations, platform requirements]

## Compliance & Legal Constraints
[Privacy, licensing, regulatory requirements]

## Dependencies
[External blockers or approval gates]

## Implications
[How these constraints shape scope and timeline - let me calculate]

Then ask: "Are these constraints all the major ones?
Given these limits, do you think the scope from Phase 2 is still realistic?"

If scope needs adjustment, we can refine it now.

Confirm: "Phase 5 complete. 
Your constraints are documented. 
Ready for Phase 6: Review and Refine when you are."
```

---

## Notes for Better Results

- **Real vs aspirational**: Be honest. A 3-month timeline with one developer shapes different scope than a 2-year timeline with a team.
- **Constraints enable focus**: They're not limitations—they're guides for prioritization.
- **Ask questions if you're unsure**: "What's the timeline?" might surface important conversations with stakeholders.

---

## What Comes Next

Move to Phase 6: `06-review-refine.md`

