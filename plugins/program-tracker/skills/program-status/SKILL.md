---
name: program-status
description: Reports current status and progress of supplier incentive programs. Use when the user asks about program status, progress toward goals, upcoming deadlines, or which programs are at risk. Triggers on phrases like "where are we on programs", "which programs are at risk", "program deadline", "how are we tracking", "program update", or "[supplier] program status".
metadata:
  author: Mike Gavin
  version: 1.1.0
  plugin: program-tracker
---

# Program Status Check

Provide a status overview for supplier programs matching "$ARGUMENTS".

## Instructions

1. If the user provides updated data, parse it and report current status
2. If asking about a specific program or supplier, focus the response on that subset
3. Always lead with the bad news — At Risk and Behind programs first
4. For each program show: supplier, program name, goal type, target, progress, % to goal, status, days remaining
5. Suggest specific actions for at-risk programs — which accounts to target, which reps to focus
6. If no data has been provided in this session, ask the user to paste current program data before proceeding

## Output Format

### Status Dashboard

| Supplier | Program | Goal Type | Target | Progress | % to Goal | Status | Days Left |
|----------|---------|-----------|--------|----------|-----------|--------|-----------|

### At Risk — Action Required
For each at-risk program: what needs to happen, who owns it, by when.

### Upcoming Deadlines
Programs expiring within 14 days, sorted by closest deadline first.

### On Track
Brief list only — supplier, program, % to goal.

## Error Handling

**No data in session**: Don't fabricate status. Prompt: "Please paste the current program data so I can pull status."

**Partial data**: Work with what's available. Flag programs with missing data as **[NO DATA]** rather than estimating.

**Days remaining can't be calculated**: If end date is unknown, note **[DATE UNKNOWN]** rather than leaving the field blank.
