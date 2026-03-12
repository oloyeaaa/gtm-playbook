# Campaign Playbook — End-to-End Cold Outreach Process

How to plan, build, launch, and close a cold outreach campaign from scratch. This is the master process — every campaign (C002, C003, C004, and future) follows these steps.

---

## Phase 0: Campaign Design (1-2 hours)

Before touching any tool, answer these 7 questions:

### 1. What's the signal?

Every campaign needs a buying signal — a reason this person needs your offer RIGHT NOW. Without a signal, you're just cold blasting.

| Signal Type | Example | Detection |
|---|---|---|
| Hiring signal | Posting for SDR/BDM | LinkedIn Jobs, Indeed |
| Funding signal | Raised a round | Signalbase, Crunchbase, press |
| Leadership change | New sales/marketing leader | LinkedIn job changes |
| Content signal | Posted about a pain you solve | LinkedIn, Twitter |
| Capacity gap | Hiring delivery roles, no sales roles | LinkedIn Jobs |
| No signal (volume play) | None — rely on ICP fit alone | Existing lists, Sales Navigator |

**Rule:** Signal-led campaigns outperform volume plays. Always try to find a signal first. C002 (no signal) got 5% reply rate. C004 (hiring signal) targets 8-12%.

### 2. What's the offer?

| Offer Type | When to Use | Example |
|---|---|---|
| Free lead magnet | Building trust, high volume | Free GTM audit (C002) |
| Paid service | Signal proves need, shorter cycle | Outbound system build (C004) |
| Conversation starter | High-value targets, low volume | Personalised insight email (C003) |

**Rule:** Free offers get more replies but longer sales cycles. Paid offers get fewer replies but close faster. Match to your signal strength.

### 3. Who's the ICP?

Define for each segment:
- **Industry vertical** (e.g., recruitment agencies, B2B agencies)
- **Company size** (e.g., 5-50 employees)
- **Buyer persona** (e.g., founder/MD — NOT the HR person posting the job)
- **Geography** (e.g., UK)
- **Pain point** (e.g., no outbound infrastructure)
- **Disqualifiers** (e.g., 100+ employees, already using outbound tools, B2C)

### 4. How many segments?

Max 3 segments per campaign. Each segment gets:
- Its own sub-campaign in SmartLead
- A segment-specific Email 2 (the proof/insight email)
- Its own A/B subject line test

### 5. What's the sequence?

Standard: 4 emails over 12-14 days.

| Email | Day | Purpose | Personalisation |
|---|---|---|---|
| 1: Hook | 0 | Signal reference + offer | Signal-specific ({{role_hiring}}, {{funding_amount}}, etc.) |
| 2: Proof | 3 | Social proof + segment insight | Segment-specific (different per vertical) |
| 3: ROI / Logic | 7 | Business case or case study | Generic (same across segments) |
| 4: Breakup | 12 | Final touch, door stays open | Generic |

### 6. What's the A/B test?

Test ONE variable per segment: **subject line**. 2 variants each. Winner metric: **reply rate** (not open rate — open tracking is OFF).

### 7. What does success look like?

Set targets before launch:

| Metric | Benchmark |
|---|---|
| Bounce rate | <3% |
| Reply rate | 5-8% (volume), 8-12% (signal-led) |
| Positive reply rate | 60-85% of total replies |
| Calls booked | 40-60% of positive replies |
| Close rate | 30-50% of calls |

---

## Phase 1: Lead Sourcing (2-3 days)

### Step 1: Signal Detection

Use the signal from Phase 0 to find companies showing buying intent:

| Signal | Source | Search Query |
|---|---|---|
| Hiring SDR/BDM | LinkedIn Jobs, Indeed | "Business Development Manager" + [vertical] + UK |
| Funding | Signalbase, Crunchbase | Filter by round size, date, geography |
| Leadership change | LinkedIn | Job title changes in last 90 days |
| Content signal | LinkedIn, Twitter | Keywords: "struggling with pipeline", "need more leads" |

### Step 2: Founder/Decision-Maker Identification

For each company from Step 1:
- Find the **founder, MD, or CEO** on LinkedIn (this is who you email)
- Never email HR, the recruiter who posted the job, or a junior employee
- Use Sales Navigator for advanced search + filtering

### Step 3: Email Verification

| Tool | Use |
|---|---|
| Hunter.io | Find email + verify (primary) |
| Prospeo | Backup verification |
| Snov.io | Backup finder |

**Rule:** Only include verified emails. Guessing = bounces = domain reputation damage.

### Step 4: CSV Preparation

One CSV per segment. Required columns:

```
first_name, last_name, email, company_name, [signal_variable], industry, company_size, linkedin_url, signal_source, signal_date
```

The `[signal_variable]` column is campaign-specific:
- C002: none (volume play)
- C003: `funding_amount` (funding signal)
- C004: `role_hiring` (hiring signal)

### Step 5: Dedup

Before uploading, cross-check against:
1. All active campaign lead lists (don't email someone already in a sequence)
2. Campaign-Tracker in Airtable (don't email anyone who already replied)
3. DM list (don't email anyone getting LinkedIn DMs this week)
4. Bounce list from previous campaigns

**Rule:** Never email + DM the same person in the same week.

---

## Phase 2: SmartLead Setup (1-2 hours)

### Step 1: Create Sub-Campaigns

One sub-campaign per segment in SmartLead:
- Naming: `C00X-[letter]-[segment-name]` (e.g., C004-A-recruitment)
- Upload CSV to each sub-campaign

### Step 2: Load Sequences

For each sub-campaign:
1. Enter Email 1 (same across segments, uses signal variable)
2. Enter Email 2 (segment-specific proof/insight email)
3. Enter Email 3 (same across segments)
4. Enter Email 4 (same across segments — breakup)
5. Set delays: Day 0, Day 3, Day 7, Day 12

### Step 3: Configure A/B Subject Lines

- 2 variants per sub-campaign
- Winner metric: reply rate
- Let SmartLead auto-split 50/50

### Step 4: Sending Settings

| Setting | Value |
|---|---|
| Send days | Tue-Thu |
| Send window | 8am-11am recipient timezone |
| Warmup volume | 2/day per mailbox (Week 1-2) |
| Ramp volume | 5/day per mailbox (Week 3) |
| Cruise volume | 8/day per mailbox (Week 4+) |
| Open tracking | OFF |
| Link tracking | OFF |

### Step 5: Pre-Publish Checklist

Run the full checklist from `founder/playbooks/smartlead-pre-publish.md`:
- All variables render correctly (especially custom signal variables)
- No broken curly brackets
- Subject lines are correct for each variant
- Sequence timing is right
- Sending schedule matches plan
- Lead list count matches expected

---

## Phase 3: Launch & Warmup (Week 1-2)

### Day 1: Launch Segment A Only

- Start at warmup volume (2/day per mailbox)
- Segment A should be your highest-volume or safest segment
- Monitor SmartLead dashboard daily

### Daily Monitoring Checklist (5 min/day)

Run `python departments/sales-outreach/tools/smartlead.py check` or `/so-smartlead-monitor`

Check:
- [ ] Bounce rate (<3% — if higher, pause and clean list)
- [ ] Spam reports (0 — if any, investigate immediately)
- [ ] New replies (triage and respond same-day)
- [ ] Sending volume (on schedule?)

### Reply Handling (same-day, every time)

| Triage | Action | Timeline |
|---|---|---|
| Interested / "yes" / "tell me more" | Book call or deliver lead magnet | Within 2 hours (P004 rule) |
| Question | Answer + restate the offer | Same day |
| OOO | Note return date, follow up after | Set calendar reminder |
| Not interested | Respond politely, mark lost | Same day |
| Bounce | Remove from list | Immediate |

**Critical rule:** Reply speed = close speed. 67% of replies arrive within 2 hours of send (P004). Your response should be same-day — ideally within hours.

---

## Phase 4: Scale (Week 2-4)

### Week 2: Add Segment B

- Only if Segment A bounce rate is <3%
- Increase volume to 5/day per mailbox
- Monitor for 2-3 days before proceeding

### Week 3+: Add Segment C

- Only if overall bounce rate stays <3%
- Increase volume to 8/day per mailbox (cruise)
- All segments now live

### Weekly Review (every Saturday or Monday)

Run `python departments/sales-outreach/tools/smartlead.py dashboard`

Review:
1. **Reply rate by segment** — which ICP converts best?
2. **A/B test results** — kill losing variant once clear winner (30+ sends per variant minimum)
3. **Reply speed** — are replies coming within 2 hours?
4. **Pipeline flow** — are replies converting to calls?
5. **Bounce rate** — still <3%?

Decisions:
- Kill losing A/B variant
- Double down on best segment (increase volume)
- Pause worst segment if <2% reply rate
- Adjust Email 2 copy if one segment underperforms

---

## Phase 5: Close (Day 14-30)

### For Free Offer Campaigns (C002 model)

```
Reply "yes" > Deliver lead magnet (audit PDF) same day > Short email with 3 key findings + Calendly > Call > Proposal > Close
```

- Audit delivery: same-day (run `/so-gtm-audit`, generate PDF)
- Follow-up after delivery: Day +2, reference strongest finding + Calendly link
- If no call booked after 5 days: send Signal Stack Blueprint (second lead magnet)

### For Paid Offer Campaigns (C004 model)

```
Reply > Book 15-min discovery call (Calendly) > Scope the build > Send proposal > Close
```

- Discovery call: 15 min, understand their situation, recommend core (lower price) or premium
- Proposal: same-day after call, using `founder/playbooks/proposal-template.md`
- Post-proposal sequence: Day +3, +7, +14 follow-ups

### Pipeline Tracking

Move every lead through Airtable Sales Pipeline stages:
`prospect > outreach-sent > audit-sent > blueprint-sent > final-touch > conversation > call-booked > proposal > won > lost > parked`

Stage timers and health rules are in `founder/playbooks/pipeline-plan.md`.

---

## Phase 6: DM Supplement (Optional, Day 16+)

For leads who completed the email sequence without replying:

1. Wait 2+ days after Email 4 (breakup)
2. Send a LinkedIn DM referencing the signal (not the emails)
3. One message only — not a DM sequence
4. Never exceed 12 DMs/day (LinkedIn flags higher volume)

**Rule:** DMs are second-chance outreach for email non-responders. Never DM someone who replied to email (even "not interested").

---

## Phase 7: Post-Campaign Review (Day 30)

### Metrics Review

Fill in the campaign metrics table in the campaign.md doc.

### Knowledge Base Updates

After every campaign, update:

1. **Learnings** (`knowledge/learnings/sales-outreach.md`) — what worked, what didn't, surprising data
2. **Patterns** (`knowledge/patterns/outreach-patterns.md`) — only when 3+ learnings confirm a pattern
3. **Memory** (`memory/outreach-systems.md`) — campaign summary, key stats, status
4. **Content topics** (`knowledge/topics/content-topics.md`) — any insight worth turning into content

### Questions to Answer

- Which segment had the highest reply rate? Why?
- Which subject line won? Does this confirm an existing pattern (P003)?
- What was the conversion rate from reply to call? From call to close?
- Did signal-led targeting outperform volume? By how much?
- What would you change for the next campaign?

---

## Campaign Naming Convention

| ID | Type | Signal | Status |
|---|---|---|---|
| C001 | GTM Audit (Sniper) | Pre-audited | Completed |
| C002 | GTM Audit Offer (Volume) | None | Live |
| C003 | Funding Signal (Sniper) | Funding round | Live |
| C004 | Outbound System Build | Hiring SDR/BDM | Planning |
| C005+ | [Next campaign] | [Next signal] | — |

---

## Quick Reference: Campaign Launch Checklist

- [ ] 7 design questions answered (Phase 0)
- [ ] Leads sourced and verified (Phase 1)
- [ ] CSVs deduped against all active campaigns
- [ ] SmartLead sub-campaigns created
- [ ] Sequences loaded with segment-specific Email 2
- [ ] A/B subject lines configured
- [ ] Sending schedule set (Tue-Thu, 8-11am)
- [ ] Open tracking OFF, link tracking OFF
- [ ] Pre-publish checklist passed (every variable renders correctly)
- [ ] Calendar events created for all milestones
- [ ] SmartLead check script running 2-3x daily
- [ ] Reply handling process clear (same-day response)

---

## One-Line Summary

> Find the signal. Write the sequence. Launch small. Scale what works. Close fast.
