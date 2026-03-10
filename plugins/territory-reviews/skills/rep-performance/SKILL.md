---
name: rep-performance
description: Analyzes individual rep performance across activity, sales, and program execution. Use when the user asks about a specific rep's performance, needs a rep-level review, or is preparing for a coaching conversation. Triggers on phrases like "how is [rep] doing", "rep review", "coaching prep", "performance review for [rep]", "pull up [rep name]", or any request tied to one of the five reps: Anthony, Erin, Cato, Brandon, Leslie.
metadata:
  author: Mike Gavin
  version: 1.1.0
  plugin: territory-reviews
---

# Rep Performance Analysis

Analyze performance for "$ARGUMENTS".

## Output Format

### Activity Metrics
- Accounts visited vs target
- Call frequency and coverage
- New account activity
- Order volume and trends

### Program Execution
- Programs assigned and their status
- Contribution to team program goals
- Programs at risk under this rep

### Strengths
What this rep is doing well, supported by data or specific observations.

### Development Areas
Where performance gaps exist, with specific examples. Frame as opportunities, not criticisms — this output may be shared with the rep.

### Recommended Actions
Concrete next steps for coaching or support — tied to observed data, not generic advice.

## Instructions

1. Be data-driven — every observation should reference specific metrics or examples
2. If comparing to team averages, state the comparison explicitly
3. Separate what you know from what you're inferring — don't present assumptions as facts
4. Connect development areas to specific selling competencies: needs assessment, closing, relationship building, product knowledge, program execution
5. Keep coaching actions specific: "focus on X account type" beats "improve prospecting"

## Team Context

Reps: Anthony, Erin, Cato, Brandon, Leslie — Palm Beach County territory.

## Error Handling

**Rep name not recognized**: Confirm before proceeding — "Did you mean one of: Anthony, Erin, Cato, Brandon, Leslie?"

**Insufficient data to assess**: Flag the section as **[INSUFFICIENT DATA]** rather than generalizing. Note what data would make the assessment useful.

**No recent activity data**: Note the gap explicitly. Don't infer performance from old data without flagging the date range.
