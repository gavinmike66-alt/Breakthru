---
description: Consolidate supplier program data across multiple formats into a unified view. Use when the user provides program data from one or more suppliers, or asks to merge/consolidate program tracking.
---

# Program Consolidation

Consolidate supplier program data from varied formats into a unified tracking view.

## Context

BBG manages 21 active supplier programs. Each supplier provides program details in their own format — some as spreadsheets, some as PDFs, some as email text. Fields, naming conventions, and goal structures vary widely.

## Common Fields to Extract

Regardless of supplier format, extract and normalize:

| Field | Description |
|-------|-------------|
| Supplier | Brand/supplier name |
| Program Name | Official program name |
| Program Period | Start and end dates |
| Goal Type | Volume, distribution, display, feature, mix |
| Goal Target | Numeric target or placement count |
| Current Progress | Where we stand vs goal |
| % to Goal | Calculated completion percentage |
| Incentive | Payout structure (per-case, flat, tiered) |
| Key Accounts | Target accounts if specified |
| Rep Assignment | Which rep(s) own this program |
| Status | On Track / At Risk / Behind / Complete |
| Notes | Special conditions, exclusions, deadlines |

## Instructions

1. Accept data in whatever format the user provides — paste, file reference, or description
2. Map supplier-specific fields to the unified schema above
3. Calculate % to Goal where both target and progress are available
4. Flag programs that are **Behind** (below 70% of time-proportional goal) with **[AT RISK]**
5. Flag programs expiring within 2 weeks with **[DEADLINE]**
6. Group output by status (At Risk first, then Behind, On Track, Complete)
7. If a supplier format is new or ambiguous, ask the user to clarify field mappings rather than guessing
