---
name: application-tracker
description: Tracks job applications, contacts, and follow-ups during an active job search. Use when the user discusses job applications, interview status, networking contacts, or follow-up tasks related to job searching. Triggers on phrases like "log this application", "job search update", "interview follow-up", "track this role", or "where am I with [company]".
metadata:
  author: Mike Gavin
  version: 1.1.0
  plugin: job-search
---

# Application Tracker

Track and organize job search activity.

## Data to Track

For each application:

| Field | Description |
|-------|-------------|
| Company | Company name |
| Role | Job title |
| Date Applied | When the application was submitted |
| Source | Where the job was found (LinkedIn, referral, company site, etc.) |
| Status | Applied / Phone Screen / Interview / Offer / Rejected / Withdrawn |
| Contacts | People connected with at this company |
| Next Action | What needs to happen next |
| Next Action Date | When it needs to happen |
| Notes | Interview feedback, compensation details, observations |

## Instructions

1. When the user provides application updates, parse and organize them
2. Highlight overdue follow-ups (next action date has passed) at the top
3. When summarizing, group by status and sort by next action date within each group
4. Track networking contacts separately — a contact may span multiple companies
5. Keep compensation details if shared but don't prompt for them
6. Never surface job search activity in field sales contexts — this plugin is strictly personal

## Error Handling

**Duplicate company entries**: Flag as **[POSSIBLE DUPLICATE]** — same company may have multiple roles. Confirm before merging.

**No next action defined**: Prompt: "What's the next step for [company]?" before closing out the update.

**Status unclear**: Default to the most conservative status and flag for confirmation.
