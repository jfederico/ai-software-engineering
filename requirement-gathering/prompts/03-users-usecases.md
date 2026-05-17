# Prompt 3: Users and Use Cases - Who Uses It and How?

**Phase**: 3 / 7
**Goal**: Understand user personas, workflows, and use cases.
**Estimated Time**: 30-45 minutes
**Output**: User personas, use case scenarios, workflows.

---

## How to Use This Prompt

Copy the **Copilot Prompt** into your Copilot chat.
Think about who will actually use your software and how they'll interact with it.
Be as concrete as possible (avoid generic "users").

---

## Copilot Prompt

```
We're in Phase 3: Users and Use Cases.
We've defined your core idea and scope.
Now we'll understand WHO uses your software and HOW they use it.

This is critical because:
- Features are useless if users don't understand them.
- Different users have different workflows.
- Use cases drive design and priority.

Ask these questions one at a time:

1. "Who are the 2-4 primary user types for your software?
   Think about different roles or perspectives.
   Examples: 'researchers', 'business analysts', 'data scientists', 'teachers'
   
   For each user type:
   - What's their role or title?
   - What's their technical skill level (beginner, intermediate, expert)?
   - Why do they care about your software?"

2. "For each user type, describe a typical day or week.
   Where do they work? What tools do they use?
   What problems frustrate them?
   Example: A researcher spends 2 hours daily reviewing papers but can't search across their collection.
   They use Google Docs, Notion, and PDF readers currently."

3. "Now describe the PRIMARY use case in detail:
   - User: [role]
   - Situation: [context when they'd use your software]
   - Goal: [what they're trying to accomplish]
   - Steps: [how they'd interact with your software]
   - Outcome: [what success looks like]
   
   Example:
   User: Research manager
   Situation: Team needs to find relevant prior art before starting a new project
   Goal: Quickly find and summarize previous research
   Steps: (1) Upload folder of papers, (2) Ask question, (3) See cited sources, (4) Read summaries
   Outcome: Find the right papers in 30 min instead of 3 hours"

4. "Describe 2-3 additional use cases (secondary scenarios).
   What else would users do with your software?
   Are there edge cases or power-user workflows?"

5. "For each primary user type, what would make them successful?
   How will they measure if your software is worth their time?
   Examples: 'Faster than my old method', 'Fewer errors', 'Less training needed', 'Works offline'"

After I answer, synthesize into:

## User Personas
[2-4 personas with name, role, skill level, goals]

## Primary Use Case Scenario
[Detailed walkthrough of main workflow]

## Secondary Use Cases
[2-3 additional scenarios]

## Success Criteria (by user type)
[How each user measures success]

## User Workflows
[Diagram or narrative of how users interact with the system]

Then ask: "Does this represent how your real users would interact with the software? 
Any gaps or scenarios we missed?"

Refine based on feedback.

Confirm: "Phase 3 complete. 
Your user understanding is documented. 
Ready for Phase 4: Functional Requirements when you are."
```

---

## Notes for Better Results

- **Make users real**: Avoid "the user" or "anyone." Use personas with names and context.
- **Think workflows**: Features matter less than what users actually do with them.
- **Include friction**: What's hard or frustrating today that your software should solve?
- **Edge cases**: Don't just design for happy path. Think about when things go wrong.

---

## What Comes Next

Move to Phase 4: `04-requirements.md`

