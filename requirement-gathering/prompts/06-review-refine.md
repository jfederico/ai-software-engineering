# Prompt 6: Review and Refine - Align Everything

**Phase**: 6 / 7
**Goal**: Review complete PRD for gaps, conflicts, and refinement.
**Estimated Time**: 30-60 minutes
**Output**: Refined PRD with resolved contradictions and closed gaps.

---

## How to Use This Prompt

Copy the **Copilot Prompt** below.
This is the quality check phase. Copilot will review your PRD holistically 
and identify gaps or conflicts that need resolution.

---

## Copilot Prompt

```
We're in Phase 6: Review and Refine.
We've gathered all your requirements, scope, users, and constraints.
Now let's step back and make sure it's all coherent.

I'm going to review what we have and ask clarifying questions.
We may iterate here—that's normal. This phase ensures your PRD is solid.

Let me start by summarizing what we have:

[Summary of PRD from Phases 1-5]

Now let me ask some review questions:

1. "SCOPE vs TIMELINE check:
   Based on your team size, skills, timeline, and constraints,
   does the scope from Phase 2 still feel achievable?
   
   If not, what should we de-scope?
   What features could move to v2?
   Is the timeline realistic?"

2. "REQUIREMENT conflicts:
   Are there any requirements that work against each other?
   
   Examples:
   - Require local-only data but also need cloud sync?
   - Require 99.9% uptime but with minimal team/cost?
   - Require support for 10+ file types but short launch date?
   
   Let me identify potential conflicts..."

3. "USER NEEDS gaps:
   For each user persona, can they achieve their goal with your scope?
   
   Example: If users need to collaborate in real-time, 
   but you're scoping a single-user tool, that's a gap.
   
   Are there use cases we forgot?"

4. "SUCCESS METRICS:
   How will you know v1 is successful?
   
   Not just 'people use it' but specific, measurable goals:
   - User adoption target? (10 users? 1,000?)
   - Retention rate?
   - Feature usage targets?
   - Performance targets from Phase 4?
   - Revenue or cost targets?
   - User satisfaction score?
   
   What matters most to you?"

5. "ARCHITECTURE PREFERENCES:
   From Phase 4, we know your deployment model.
   Do you have preferences on:
   - Technology stack? (Python? JavaScript? Go?)
   - Architecture style? (Monolithic? Microservices?)
   - Database? (SQL? NoSQL? Vector DB?)
   - UI framework? (Web? Native? CLI?)
   
   Or should implementation decide?"

6. "RISKS & ASSUMPTIONS:
   What could go wrong?
   
   - Technical risks: 'Vector databases might not scale as we expect'
   - Market risks: 'Users might not want local-only (want cloud features)'
   - Resource risks: 'Key person might leave'
   - Dependency risks: 'Ollama might not work on all platforms'
   
   What worries you most?"

After I answer all review questions, I'll synthesize any changes.

Then ask: "Do you feel this PRD is complete and coherent?
Any last things to clarify before we finalize?"

If yes: "Great! Phase 6 complete. Ready to finalize the PRD in Phase 7."

If no: "What still feels unclear? Let's clarify it now."

Iterate until you're satisfied.
```

---

## Notes for Better Results

- **Be critical**: Phase 6 is where you catch problems before implementation.
- **Ask 'what if'**: "What if we don't have time for feature X?" or "What if this requirement doesn't pan out?"
- **Refine ruthlessly**: It's OK to change scope, timeline, or requirements here. Better now than mid-implementation.
- **Validate with stakeholders**: If you have a team or stakeholders, this is a good time to pressure-test with them.

---

## What Comes Next

Move to Phase 7: `07-finalize-prd.md`

