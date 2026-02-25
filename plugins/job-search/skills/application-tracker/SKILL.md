---
description: Track job applications, contacts, and follow-ups. Use when the user discusses job applications, interview status, networking contacts, or follow-up tasks related to job searching.
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
2. Highlight overdue follow-ups (next action date has passed)
3. When summarizing, group by status and sort by next action date
4. Track networking contacts separately — a contact may span multiple companies
5. Keep compensation details if shared but don't prompt for them
