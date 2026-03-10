---
name: program-consolidation
description: Consolidates supplier program data across multiple formats into a unified tracking view. Use when the user provides program data from one or more suppliers, or asks to merge, consolidate, or organize program tracking. Triggers on phrases like "consolidate programs", "supplier program update", "load program data", "here's the [supplier] program", or any paste of supplier incentive program details.
metadata:
  author: Mike Gavin
  version: 1.1.0
  plugin: program-tracker
---

# Program Consolidation

Consolidate supplier program data from varied formats into a unified tracking view.

## Context

BBG manages 21 active supplier programs. Each supplier provides program details in their own format — some as spreadsheets, some as PDFs, some as email text. Fields, naming conventions, and goal structures vary widely.

For known supplier format patterns, see `references/supplier-formats.md`.

## Unified Schema

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
6. Group output by status: At Risk first, then Behind, On Track, Complete
7. If a supplier format is new or ambiguous, ask the user to clarify field mappings rather than guessing

## Error Handling

**Unknown supplier format**: Do not guess field mappings. Ask: "I don't have a format pattern for [supplier]. Can you tell me which column/field represents the goal target and current progress?"

**Missing progress data**: Mark Status as **[NO DATA]** and include the program in output — don't skip it. Flag with **[NEEDS UPDATE]**.

**Overlapping programs from same supplier**: Flag as **[POSSIBLE DUPLICATE]** and list both — let the user decide which is current.

**Missing dates**: Note **[DATE UNKNOWN]** in Program Period. Still include the program — assume active unless told otherwise.
