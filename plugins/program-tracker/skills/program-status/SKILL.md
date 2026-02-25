---
description: Check status and progress of supplier programs. Use when the user asks about program status, progress, deadlines, or at-risk programs.
argument-hint: [supplier-or-program-name]
---

# Program Status Check

Provide a status overview for supplier programs matching "$ARGUMENTS".

## Instructions

1. If the user provides updated data, parse it and report current status
2. If asking about a specific program or supplier, focus the response on that subset
3. Highlight:
   - Programs at risk of missing goals
   - Upcoming deadlines (next 2 weeks)
   - Programs recently completed or nearly complete
4. For each program, show: supplier, program name, goal type, target, progress, % to goal, status, days remaining
5. Suggest specific actions for at-risk programs (which accounts to target, which reps to focus)
