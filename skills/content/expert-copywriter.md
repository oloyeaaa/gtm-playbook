---
name: expert-copywriter
description: >
  Strategic copywriting intelligence for all [Company] departments. Produces a Copy Strategy
  Brief before writing begins — ICP psychology, narrative approach, storytelling patterns,
  and CTA strategy aligned to the correct funnel lane. Sits above cm-copywriter (which
  handles tactical scoring at Step 4). This skill operates at Step 2.5 (between research
  and writing). Triggers on: invocation by any content/sales/research agent before the
  writing step, or directly via "copy strategy", "story angle", "expert copywriter",
  "how should I frame this", or /cm-expert-copywriter.
---

# Expert Copywriter Skill

## Goal

Before any writing begins, produce a **Copy Strategy Brief** that tells the writing skill exactly how to approach the piece: who is reading this, what they fear, what they want, which storytelling pattern to use, and what CTA aligns with the correct funnel lane.

This skill does NOT write the content. It does NOT score headlines. It provides strategic direction that makes the writing skill's output sharper, more emotionally resonant, and more likely to drive action.

## Required Context

Before executing, load:
1. `knowledge/icp-psychology.md` -- ICP psychological model (fears, desires, internal monologue, language map, objection archaeology)
2. `knowledge/voice-guide.md` -- Voice characteristics, banned words, preferred lexicon
3. `knowledge/signal-funnel.md` -- 3-lane funnel (Authority, Outreach, Nurture), CTA rules, routing

## Inputs

When invoked, receive:

- **topic:** What the content is about
- **department:** `content` | `sales` | `research` | `founder` (determines which framework to load)
- **channel:** `linkedin` | `blog` | `newsletter` | `youtube` | `cold-email` | `dm` | `audit-delivery` | `report` | `founder-post`
- **funnel_lane:** `lane-1-authority` | `lane-2-outreach` | `lane-3-nurture` (determines CTA strategy)
- **source_data:** Any research findings, statistics, audit results, or campaign data available (optional but strongly preferred)
- **segment:** `consulting` | `agency` | `recruitment` | `it-services` | `general` (optional, defaults to general)

---

## Step 1: Load Department Framework

Based on the `department` input, activate the correct copy framework.

### Framework A: Content & Media

**Copy Mode:** Diagnostic Observer
[Your Name] is the person running audits, building systems, and sharing what he finds. He is not a guru prescribing from theory. He is not selling. He is teaching from real experience.

**Voice Calibration:**
- Clinical precision when presenting data
- Warmth when sharing the journey
- Never preachy, never prescriptive
- "I found this" not "You should do this"
- Uses "I" and "we" naturally -- this is personal brand content

**Story Templates Available:**
1. **The Audit Reveal:** "I audited [N] companies this week. [Surprising finding]." Best for LinkedIn Format 1 (The Audit) and blog Diagnosis pillars.
2. **The Build Log:** "I built [thing] in [time]. Here's what happened." Best for LinkedIn Format 5 (The Build Log) and blog System pillars.
3. **The Data Contradiction:** "[Common belief]. The data says [opposite]." Best for LinkedIn Format 4 (The Unpopular Take) and blog Perspective pillars.
4. **The Irony Hook:** "[Company type] that sells [X] doesn't do [X] for themselves." Best for any format. The strongest emotional hook in [Company]'s arsenal.

**CTA Rules (from Signal Funnel):**
- LinkedIn (Lane 1): Engagement CTAs only. "What's your experience?" or "Comment [WORD] and I'll send you [thing]." Newsletter link goes in COMMENTS, never in post body.
- Blog (Lane 1): Diagnostic question + single link to audit page. No vendor energy.
- Newsletter (Lane 3): Reply question + Calendly link. The newsletter IS the nurture channel. CTAs can be warmer.

### Framework B: Sales & Outreach

**Copy Mode:** Peer, Not Vendor
The email reads like one founder telling another what they noticed. Not a sales pitch. Not an agency proposal. One person saying "I saw something about your business and thought you should know."

**Voice Calibration:**
- Shorter sentences than content (under 80 words for Touch 1)
- No flattery ("I was impressed by your..." is banned)
- No superlatives ("best", "leading", "innovative" are banned)
- State facts, not opinions
- The ask is always small ("Want me to send it?" not "Book a call")

**Email Copy Principles (from proven patterns):**
1. Lead with their specific signal (P007). Reference the job posting, the funding round, the role change. This proves you did work.
2. Include a specific number about their company (P003). "Scored [Company] out of 100" creates curiosity.
3. Under 80 words for Touch 1. Every word earns the next word.
4. The audit is the offer, not the service. The service comes after trust is built.
5. Never pitch in the audit delivery email. Lead with their strongest hidden asset, explain the core problem, give 3 quick wins, then offer the walkthrough.

**DM Copy Principles:**
- 3-touch sequence. Touch 1 = observation. Touch 2 = value. Touch 3 = breakup.
- Warmer and more personal than email ([Your Name]'s natural conversational voice)
- Never link to newsletter in DMs (signal-funnel rule)
- Maximum 3 sentences per DM

**CTA Rules (Lane 2):**
- Email: "Want me to send it?" or "Worth a look?" -- small asks only
- Audit delivery: "Happy to walk you through it -- here's my calendar" -- Calendly link
- Follow-up: Reference a specific finding from the audit. Never generic.

### Framework C: Research & Intelligence

**Copy Mode:** Analyst to Executive
The reader is a founder, not a data scientist. Present findings as implications, not metrics. Every number needs a "so what" sentence.

**Voice Calibration:**
- Authoritative but accessible
- Translate jargon into impact statements
- Lead with the implication, follow with the evidence
- Use severity framing ("critical", "high", "moderate") not just numbers

**Narrative Templates:**
1. **The "What This Means" Bridge:** Every data point gets a one-sentence implication. "3 of your 5 competitors are hiring SDRs. That means outbound pressure in your market is about to increase."
2. **The Severity Framing:** Instead of "Score: 32/100", write "Your GTM infrastructure is in the bottom third of the companies we've audited this quarter. The good news: the fix for your biggest gap takes 5 days."
3. **The Comparison Anchor:** "The average consulting firm scores 45/100. You scored 32. That's a 13-point gap concentrated in two areas."

### Framework D: Founder Operations

**Copy Mode:** Building in Public
[Your Name] sharing the real journey. Vulnerable about struggle, specific about learnings, never pretending to have all answers. This is the most personal framework.

**Voice Calibration:**
- More personal than cm- content. Uses "I" freely.
- References being a father, the day job, the financial constraints when relevant
- Still clinical when discussing data -- warmth is in the framing, precision is in the evidence
- Uses verbal tics sparingly ("if that makes sense") per founder profile
- Never self-pity. Honest about difficulty, but always moving forward.

**Story Templates:**
1. **The Honest Numbers:** "9 replies from 900 emails. That's a 1% response. But 6 of those 9 said yes to an audit within 2 hours. And that's the only number that matters."
2. **The Fear Confession:** "I nearly didn't send those emails. [Why]. Here's what happened when I did."
3. **The Lesson Learned:** "I made [mistake]. It cost [consequence]. Here's what I do differently now."
4. **The Build Diary:** "Week 3 of the sprint. [What happened]. [What I learned]. [What's next]."

---

## Step 2: Select Storytelling Pattern

Based on the topic, source data, and department framework, select the primary storytelling pattern.

### Pattern 1: The Inversion

**When to use:** You have a number that looks bad at first glance but contains a hidden win. Or a number that looks good but hides a problem.

**Structure:** Start with the big number (what failed or what looks impressive). Then zoom into the small number (what actually matters). The contrast is the story.

**Example (from real data):**
- Raw data: "5% reply rate from 900 leads, 6 said yes to audit"
- Inverted: "We sent 900 emails. 891 people ignored us. But the 9 who replied? 6 said 'send me the audit' within 2 hours. We didn't need the 891."

**Formula:**
```
[Big number that sets expectation]
[Flip: most of that number did X]
[But the small number did Y]
[And Y is what actually matters because Z]
```

### Pattern 2: The Cobbler's Children

**When to use:** You've found an irony -- a company that sells a service but doesn't use it themselves. This is the strongest emotional hook in B2B because it triggers Fear #1 (being exposed as a hypocrite).

**Structure:** Name the specific type of company. Name what they sell. Name the gap. Let the irony speak for itself. Never be cruel about it -- be the doctor delivering a diagnosis, not a critic.

**Example (from real data):**
- Raw data: "Consulting firms score avg 45/100, agencies avg 36/100"
- Storied: "The consulting firm that charges £2,000/day for strategy advice? Their website scores 32 out of 100. The communications agency that sells storytelling had zero published stories on their website."

**Formula:**
```
[The company type] that [what they charge for / sell]
[The gap: what they don't do for themselves]
[Optional: the specific number that proves it]
```

### Pattern 3: The Invisible Asset

**When to use:** You've found something genuinely impressive about a company that is hidden, buried, or invisible to their audience. This is the most trust-building pattern because you're telling them they're better than they think.

**Structure:** State the impressive fact first. Then reveal where it's hidden. The contrast between the fact's value and its visibility IS the story.

**Example (from real data):**
- Raw data: "Techplus has 100% client retention, visible only on Odoo directory page"
- Storied: "One company I audited has never lost a client. Not one. In their entire history. Where is this fact? Buried on a third-party directory page that gets 12 visits a month."

**Formula:**
```
[The impressive fact -- stated dramatically]
[The reveal: where it's actually located]
[The contrast: how few people see it vs. how many should]
```

---

## Step 3: Apply Narrative Quality Gate

Every piece of data in the source material must pass these 4 checks before it can appear in the copy. If a data point fails, rewrite it until it passes.

### Check 1: Does the number have a face?

- FAIL: "5% reply rate"
- PASS: "9 founders who replied within 2 hours"
- Rule: Replace percentages with people. Replace rates with actions.

### Check 2: Does the number have a consequence?

- FAIL: "32/100 audit score"
- PASS: "Google can't read a single word of their website"
- Rule: Every number must answer "so what?" in the same sentence or the next.

### Check 3: Does the number have a comparison?

- FAIL: "6 audits delivered"
- PASS: "6 audits delivered in 48 hours, all from a single email"
- Rule: Numbers in isolation are meaningless. Give them a reference point -- time, expectation, industry average, or the reader's own situation.

### Check 4: The Pub Test

- FAIL: "Our outbound campaign achieved a 5% response rate with an 85% audit acceptance conversion"
- PASS: "We emailed 900 founders. 9 replied. 6 wanted the audit. All 6 got it the same day."
- Rule: If someone wouldn't repeat this number to a friend over a drink, rewrite it. Conversational delivery beats analytical precision.

---

## Step 4: Determine CTA Strategy

Based on the `funnel_lane` and `channel` inputs, select the correct CTA approach. This MUST align with the Signal Funnel routing rules.

### Lane 1: Authority (LinkedIn, Blog, YouTube)

**Purpose:** Build engagement. Let the audience come to you.
**CTA style:** Questions, not asks. Invitations, not instructions.

- LinkedIn: "What's your experience with [topic]?" or "Comment [WORD] and I'll send you [resource]"
- Blog: Diagnostic question at the end. Single link to audit page. No "book a call" pressure.
- YouTube: Subscribe + "In the next video, I'll show you [specific next thing]"

**Never in Lane 1:**
- Link to newsletter in the post body (goes in comments only)
- "Book a call" or Calendly link
- Vendor energy of any kind

### Lane 2: Outreach (Cold email, DM, Audit delivery)

**Purpose:** Start conversations. Book calls. Build the trust bridge.
**CTA style:** Small asks that feel like favours, not commitments.

- Cold email Touch 1: "Want me to send it?" or "Worth a look?"
- Cold email Touch 2-3: Reference specific finding. "Noticed [X] about [Company]. Thought you should know."
- Audit delivery: "Happy to walk you through the 3 biggest findings -- here's my calendar." (Calendly link)
- DM: "Spotted something about [Company]. Mind if I share?"

**Never in Lane 2:**
- Link to newsletter
- Generic CTAs ("Let's connect")
- Pressure language ("Limited spots", "Act now")

### Lane 3: Nurture (Newsletter)

**Purpose:** Park warm leads until they're ready.
**CTA style:** Conversational. Reply-focused. Warmer than Lane 1 or 2.

- Primary: "Hit reply and tell me [question]" -- drives engagement and surfaces warm leads
- Secondary: Calendly link for readers who are ready now
- Tertiary: "Forward this to a founder who [specific situation]" -- organic growth

**Never in Lane 3:**
- Hard sells
- Urgency tactics
- "Limited time" framing

---

## Step 5: Produce the Copy Strategy Brief

Compile all decisions into a structured brief that the writing skill receives as additional context.

### Brief Format

```
COPY STRATEGY BRIEF
====================

TOPIC: [topic]
DEPARTMENT: [department] → Framework [A/B/C/D]
CHANNEL: [channel]
FUNNEL LANE: [lane] → [CTA approach]
SEGMENT: [segment] → [segment-specific psychology from icp-psychology.md]

ICP PSYCHOLOGY CUES
→ Primary fear to address: [from fear hierarchy]
→ Primary desire to promise: [from desire hierarchy]
→ Internal monologue entry point: [specific quote from icp-psychology.md]
→ Buying journey stage: [1-5] → Copy job: [what copy needs to do at this stage]

NARRATIVE APPROACH
→ Primary storytelling pattern: [Inversion / Cobbler's Children / Invisible Asset]
→ Story template: [specific template from the framework]
→ Data points to transform: [list raw data + suggested narrative treatment]

VOICE CALIBRATION
→ Mode: [Diagnostic Observer / Peer Not Vendor / Analyst to Executive / Building in Public]
→ Tone adjustments: [any channel-specific modifications]
→ Banned patterns for this piece: [specific things to avoid beyond the standard banned list]

CTA STRATEGY
→ Lane: [1/2/3]
→ CTA type: [question / small ask / reply prompt / Calendly]
→ Specific CTA suggestion: [draft CTA aligned to the lane and channel]
→ Anti-patterns: [what NOT to do with the CTA]

QUALITY REMINDERS
→ Every number must pass the 4-check narrative quality gate
→ Every claim must trace to evidence (never fabricate)
→ Voice guide banned words apply (33 words, no emojis, no exclamation marks)
```

---

## Quality Gates

Before delivering the brief, verify:

- [ ] Department framework matches the invoking agent's department
- [ ] ICP psychology cues reference specific entries from icp-psychology.md (not generic)
- [ ] Storytelling pattern selection is justified by the available source data
- [ ] CTA strategy aligns with the correct funnel lane (no newsletter links in Lane 2, no Calendly in Lane 1)
- [ ] Voice calibration includes channel-specific adjustments
- [ ] No banned words appear anywhere in the brief
- [ ] At least one specific data-to-narrative transformation is suggested (not just "use storytelling")

---

## Self-Improvement Protocol

### After Every Use

1. Did the writing skill produce stronger output with the brief vs. without? Note the difference.
2. Did the user edit or reject any psychology cues? If yes, update `knowledge/icp-psychology.md` with the correction.
3. Did the storytelling pattern fit the content? If a different pattern would have worked better, log it.

### Copy Performance Tracking

When engagement data is available (impressions, replies, opens, comments), log:

```
## [DATE] -- Copy Performance
Content type: [channel]
Storytelling pattern: [which pattern was used]
Framework: [A/B/C/D]
Segment: [which segment]
ICP psychology cue used: [which fear/desire/monologue entry]
Result: [engagement metric]
Pattern candidate: [yes/no -- does this confirm a reusable pattern?]
```

When 3+ entries show the same pattern outperforming, extract to `knowledge/patterns/content-patterns.md`.

### Voice Drift Detection

If any generated copy contains:
- A banned word from the voice guide
- Vendor energy (selling instead of teaching/diagnosing)
- A CTA that violates the funnel lane rules
- "Results" language instead of "evidence" language

Log the failure. If the same type of drift occurs 3+ times, add a new explicit check to the quality gates.

---

## Rules

1. **Never write the content.** This skill produces the brief. The writing skill (cm-blog-writer, cm-linkedin-creator, etc.) does the writing.
2. **Never score headlines.** That's cm-copywriter's job at Step 4. This skill operates at Step 2.5.
3. **Never fabricate psychology.** Every ICP insight must trace to `knowledge/icp-psychology.md`, which traces to real data.
4. **Always select a storytelling pattern.** "Just present the data" is not an acceptable narrative approach. Every number gets a story.
5. **Always check the funnel lane.** A beautiful CTA in the wrong lane is worse than a mediocre CTA in the right lane.
6. **Segment matters.** If the segment is known, use segment-specific psychology. Generic copy for a known segment is lazy copy.
7. **The brief is a tool, not a cage.** If the writing skill finds a better approach during drafting, it should adapt. The brief sets direction, not constraints.
