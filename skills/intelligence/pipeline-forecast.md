---
name: bi-pipeline-forecast
description: >
  Data-driven pipeline projection using real conversion rates from [Company] outreach
  data. Calculates expected audits, conversations, and revenue from remaining
  leads. Triggers on: "pipeline forecast", "forecast", "how many audits",
  "projected revenue", "pipeline projection", or /bi-pipeline-forecast.
---

# Pipeline Forecast

## Goal

Project future pipeline output (audits, conversations, proposals, revenue) using real conversion rates from [Company]'s own data. Replace guesswork with math.

## Required Context

Load before executing:

1. `departments/business-intelligence/references/metrics-definitions.md` -- KPI definitions and conversion benchmarks
2. `founder/goals/active-sprint.md` -- Sprint targets
3. `founder/playbooks/pipeline-plan.md` -- Pipeline stages and pricing
4. `knowledge/patterns/outreach-patterns.md` -- Proven patterns (reply rates, timing)

## Data Collection

### Step 1: Current Pipeline Snapshot

Query Airtable Campaign-Tracker ([YOUR_TABLE_ID]):
- Count leads by Email Status: Sent, Opened, Replied, Bounced
- Count leads by DM Status: Sent, Replied, Ignored
- Count by Priority: Hot, Warm, Cold, Parked

### Step 2: Historical Conversion Rates

Pull from SmartLead and Airtable to calculate actual rates:

```
CONVERSION FUNNEL:
Emails Sent → Reply Rate = replies / sent
Reply → Audit Request Rate = audit_yes / total_replies
Audit Delivered → Conversation Rate = conversations / audits_delivered
Conversation → Call Rate = calls_booked / conversations
Call → Proposal Rate = proposals / calls
Proposal → Win Rate = wins / proposals
```

Use [Company]'s own data. If insufficient data for a stage, use these conservative defaults:
- Reply rate: 5% (from C002 actual)
- Audit acceptance: 67% (6/9 from C002 actual)
- Audit → Conversation: 30% (estimated, update when data available)
- Conversation → Call: 50% (estimated)
- Call → Win: 33% (estimated)
- Average deal value: £497 (mid-range from pricing menu)

### Step 3: Calculate Projections

```
Remaining unsent leads × Reply rate = Expected replies
Expected replies × Audit acceptance = Expected audit requests
Expected audit requests × Audit→Conversation = Expected conversations
Expected conversations × Conversation→Call = Expected calls
Expected calls × Call→Win = Expected wins
Expected wins × Average deal value = Expected revenue
```

Also calculate:
- **Time to close** -- Based on average days per stage, when will the next win happen?
- **Sprint feasibility** -- Can we hit sprint targets with current pipeline?
- **Bottleneck analysis** -- Which conversion step has the biggest drop-off?

### Step 4: Scenario Analysis

Run 3 scenarios:

| Scenario | Assumption |
|----------|------------|
| Conservative | Use lowest observed conversion rates |
| Expected | Use average conversion rates |
| Optimistic | Use best observed conversion rates + C004 launch |

## Output Format

```
============================================
PIPELINE FORECAST — [DATE]
============================================

CURRENT PIPELINE
- Total leads loaded: [X]
- Emails sent: [X] | Remaining: [X]
- Replies received: [X] | Reply rate: [X]%
- Audits requested: [X] | Delivered: [X]
- Active conversations: [X]
- Calls booked: [X]
- Proposals sent: [X]

CONVERSION RATES (from real data)
- Sent → Reply: [X]% (n=[X])
- Reply → Audit Yes: [X]% (n=[X])
- Audit → Conversation: [X]% (n=[X], or estimated*)
- Conversation → Call: [X]% (n=[X], or estimated*)
- Call → Win: [X]% (estimated*)
* Insufficient data — using conservative estimate. Will update as data accumulates.

PROJECTIONS
                    Conservative    Expected    Optimistic
Remaining replies:  [X]             [X]         [X]
New audit requests: [X]             [X]         [X]
New conversations:  [X]             [X]         [X]
Calls booked:       [X]             [X]         [X]
Wins:               [X]             [X]         [X]
Revenue:            £[X]            £[X]        £[X]

SPRINT FEASIBILITY (Day [X]/30)
- Audits target (5): [X] delivered + [X] projected = [AHEAD/ON TRACK/BEHIND]
- Conversations target (5): [X] active + [X] projected = [AHEAD/ON TRACK/BEHIND]
- Client target (1): [X] won + [X] projected = [AHEAD/ON TRACK/BEHIND]

BOTTLENECK
The biggest drop-off is [stage → stage] at [X]%.
→ Recommendation: [specific action to improve this conversion]

TIME TO NEXT WIN
Based on current velocity: [X] days to next expected win ([date]).
Based on optimistic velocity: [X] days ([date]).

ACTIONS TO IMPROVE FORECAST
1. [Highest impact action] — Would add [X] expected [audits/conversations/wins]
2. [Second action] — Would add [X] expected [outcome]
3. [Third action] — Would add [X] expected [outcome]
```

## Auto-Update

Every time this skill runs, compare new conversion rates to stored rates in `metrics-definitions.md`. If a rate changes by more than 10 percentage points with n >= 10, update the reference file.

## Quality Gates

- [ ] All conversion rates cite sample size (n=X)
- [ ] Estimated rates are clearly marked with asterisk
- [ ] Three scenarios shown (not just one optimistic number)
- [ ] Sprint feasibility explicitly answered
- [ ] At least one specific action to improve the bottleneck
- [ ] Revenue projection uses actual pricing from proposal-template.md

## Rules

1. Never project from estimated rates without flagging them. Real data > assumptions.
2. Small sample sizes get wide ranges, not single numbers. "3-8 expected" beats "5.5 expected."
3. Update conversion rates every time new data comes in. Stale rates produce stale forecasts.
4. Time-to-close matters more than total-wins. A founder needs to know WHEN, not just HOW MANY.
5. Always surface the bottleneck. The weakest conversion step is the highest-leverage fix.
