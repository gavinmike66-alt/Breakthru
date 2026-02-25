---
description: Parse ride-with recap notes into a structured field coaching summary. Use when the user provides notes from a ride-with (field visit with a rep).
argument-hint: [rep-name]
---

# Ride-With Recap Parser

Parse ride-with notes for "$ARGUMENTS" into a structured coaching recap.

## Expected Input

Free-text notes taken during or after a ride-with day with a rep. May include:
- Accounts visited together
- Rep selling behaviors observed (positive and areas for improvement)
- Coaching conversations had
- Account-level observations
- Action items agreed upon

## Output Format

### Ride-With Summary
| Field | Value |
|-------|-------|
| Rep | (name) |
| Date | (if mentioned) |
| Territory | (if mentioned) |
| Accounts Visited | (count) |

### Account Details
For each account visited:
- **Account**: name
- **Observations**: what happened, what was discussed
- **Rep Strengths**: positive behaviors demonstrated
- **Coaching Opportunities**: areas for development

### Coaching Summary
- Top 2-3 strengths observed
- Top 2-3 development areas
- Agreed-upon action items with deadlines

### Follow-Up Items
Numbered list of action items for both the rep and the manager.

## Instructions

1. Separate factual observations from coaching assessments
2. Frame development areas constructively — these recaps may be shared with the rep
3. Connect observations to specific selling competencies (e.g., needs assessment, closing, relationship building, product knowledge)
4. Flag urgent account issues with **[URGENT]**
