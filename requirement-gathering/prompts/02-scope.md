# Prompt 2: Scope Definition - What's In and Out?

**Phase**: 2 / 7
**Goal**: Define the features and boundaries of v1.
**Estimated Time**: 20-30 minutes
**Output**: Feature list, scope boundaries, out-of-scope list, and rationale.

---

## How to Use This Prompt

Copy the **Copilot Prompt** section below into your Copilot chat.
Answer questions about what features are included in your v1 release.
Copilot will help you prioritize and justify your scope choices.

---

## Copilot Prompt

```
We're now in Phase 2: Scope Definition.
Your kickoff from Phase 1 captured your core idea.
Now we'll define what features are in v1, what's out, and why.

This is important because:
- Scope defines effort and timeline.
- Clear boundaries prevent scope creep.
- Knowing what's NOT in v1 is as important as what IS.

Ask these questions one at a time:

1. "Looking at your solution from Phase 1, 
   what are the 5-10 core features or capabilities a user needs 
   to get value from your software on day one? 
   List them briefly."

2. "For each core feature you listed, 
   describe what 'done' looks like. 
   Example: 'Users can upload PDF documents' (done = file upload succeeds, file is processed)."

3. "Are there features you COULD build but are choosing to defer? 
   What are they, and why are they not in v1? 
   Examples: 'User accounts' (deferring until we have 10+ users) 
   or 'Multi-language support' (starting with English only)."

4. "What 'nice-to-have' features might make users happier, 
   but aren't essential for v1 to work? 
   (Examples: dark mode, mobile UI, advanced analytics, integrations)"

5. "Are there absolute constraints that will limit scope? 
   (Examples: 'Must work offline', 'Must cost less than $100k', 'Must launch in 6 months', 'Must run on Raspberry Pi')"

After I answer, synthesize into:

## Features In V1
[List of core features with "done" criteria]

## Features Deferred (Future Phases)
[Nice-to-haves and future expansion]

## Out of Scope
[Explicit non-goals, things you're NOT building]

## Scope Boundaries
[Key constraints that shaped these choices]

Then ask: "Does this scope feel right? 
Is it achievable? 
Are we missing anything critical?"

Refine based on my feedback.

When satisfied, confirm: "Phase 2 complete. 
Your scope is locked. 
Ready for Phase 3: Users and Use Cases when you are."
```

---

## Notes for Better Results

- **Ruthlessly prioritize**: If everything is "must have," nothing is. Scope is about trade-offs.
- **Think MVP**: What's the absolute minimum for users to see value?
- **Future path**: It's OK to defer features to later phases if they don't block core value.
- **Constraints are features**: If you must launch in 3 months, that shapes scope. Be explicit.

---

## What Comes Next

Move to Phase 3: `03-users-usecases.md`

