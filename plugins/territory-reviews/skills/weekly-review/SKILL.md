---
name: weekly-review
description: Builds a weekly territory review from rep activity and performance data. Use when the user asks for a weekly review, territory summary, or weekly recap. Triggers on phrases like "weekly recap", "territory review", "week in review", "build the weekly", "pull together the week", or "what happened this week".
metadata:
  author: Mike Gavin
  version: 1.1.0
  plugin: territory-reviews
---

# Weekly Territory Review

Build a weekly territory review for Palm Beach County.

## Expected Input

The user will provide some combination of:
- Rep daily report summaries (parsed or raw)
- Sales/volume data for the week
- Program progress updates
- Account-level activity or issues
- Prior week's review for comparison

## Output Format

### Territory Snapshot

| Metric | This Week | Prior Week | Change |
|--------|-----------|------------|--------|
| Total Accounts Visited | | | |
| Total Orders | | | |
| New Placements | | | |
| Open Follow-ups | | | |

### Rep Activity Summary

For each rep (Anthony, Erin, Cato, Brandon, Leslie):
- Accounts visited / target
- Key wins
- Issues or gaps
- Program contributions

### Program Progress
- Programs with notable movement this week
- At-risk programs needing attention

### Key Wins
Bulleted list of the week's highlights — 3-5 items max.

### Action Items for Next Week
Numbered list with owner and priority. Revenue-driving actions first.

## Instructions

1. If data is incomplete, work with what's available and note what's missing at the top
2. Compare to prior week where data exists — trend direction matters more than absolute numbers
3. Keep tone factual and action-oriented — this is for leadership review
4. Don't editorialize on rep performance here — save that for rep-performance skill
5. Prioritize action items by impact: revenue-driving first, then program deadlines, then admin

## Error Handling

**Missing rep data**: Note the gap — "No data received for [rep] this week" — rather than omitting them.

**No prior week for comparison**: Leave Change column blank, note "Prior week not available."

**Conflicting numbers**: Flag with **[VERIFY]** and show both figures rather than choosing one.
