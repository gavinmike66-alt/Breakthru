---
description: Parse free-text rep daily reports into structured data. Use when the user pastes or provides a rep's daily notes, end-of-day summary, or activity log.
---

# Daily Report Parser

Parse the provided rep daily report into structured output.

## Expected Input

Reps submit daily notes in varied free-text formats. Common elements include:
- Account names visited
- Key contacts spoken with
- Orders placed or commitments secured
- Issues or follow-ups needed
- New placements or distributions gained
- Competitive activity observed

## Output Format

For each account visited, extract:

| Field | Description |
|-------|-------------|
| Account Name | Name of the retail account |
| Contact | Key person spoken with |
| Activity Type | Visit, call, email, delivery ride-along |
| Orders/Commits | What was sold or committed |
| New Placements | New SKUs or displays placed |
| Follow-ups | Action items with due dates |
| Competitive Intel | Competitor activity noted |
| Notes | Anything else relevant |

## Instructions

1. Read the full text before parsing — reps often reference the same account multiple times
2. Normalize account names (strip extra whitespace, fix obvious typos if context makes it clear)
3. Flag any items that need manager follow-up with **[MGR ACTION]**
4. If the rep mentions a supplier program by name, tag it with **[PROGRAM: name]** so it can cross-reference with program-tracker
5. Summarize total accounts visited and key wins at the top
