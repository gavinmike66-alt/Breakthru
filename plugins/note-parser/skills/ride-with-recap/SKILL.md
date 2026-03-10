---
name: ride-with-recap
description: Parses ride-with notes into a structured field coaching summary. Use when the user provides notes from a ride-with (field visit accompanying a rep). Triggers on phrases like "ride-with recap", "field visit notes", "rode with [rep]", "recap my ride-with", or any coaching observation notes from a day in the field.
metadata:
  author: Mike Gavin
  version: 1.1.0
  plugin: note-parser
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

Two lists:
- **Rep actions**: numbered, with due dates where mentioned
- **Manager actions**: numbered, with due dates where mentioned

## Instructions

1. Separate factual observations from coaching assessments
2. Frame development areas constructively — these recaps may be shared with the rep
3. Connect observations to specific selling competencies (e.g., needs assessment, closing, relationship building, product knowledge)
4. Flag urgent account issues with **[URGENT]**
5. If a program was discussed or worked during the ride-with, tag it **[PROGRAM: name]**

## Error Handling

**No rep name provided**: Prompt the user — "Which rep was this ride-with with?" before proceeding.

**Notes too sparse to coach from**: Flag as **[INSUFFICIENT DATA]** on the relevant section rather than fabricating observations. Note what additional context would help.

**Conflicting observations**: If notes contradict themselves, note the conflict and ask the user to clarify before finalizing.
