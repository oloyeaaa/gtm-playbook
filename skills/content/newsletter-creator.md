---
name: newsletter-creator
description: >
  Use when asked to write a newsletter, Beehiiv content, email newsletter,
  or "The GTM Signal" issue. Triggers on: "newsletter about", "write a newsletter",
  "Beehiiv", "GTM Signal issue", "email newsletter", or /newsletter.
  Researches the topic first, then structures as hook → insight → framework → CTA.
---

# Newsletter Creator Skill

## Goal

Produce a structured, research-backed newsletter issue for "The GTM Signal" on Beehiiv. Output is a complete draft ready to paste into Beehiiv. Target: 800-1,100 words. Structure: Hook → Insight → Framework → CTA.

## Required Context

Before executing, load:
1. `knowledge/voice-guide.md` — Voice, banned words, lexicon
2. `departments/content-media/references/content-week.md` — Newsletter section of weekly workflow

## Step 1: Research the Topic

Before writing anything, gather current information on the topic.

Research process:
1. Search for 3-5 recent, high-quality sources on the topic
2. Extract specific data points: numbers, stats, quotes, findings
3. Identify what the conventional wisdom says vs what the data shows
4. Find the angle that maps to Signal-Led GTM thinking

What to look for:
- Industry statistics that support precision over volume
- Examples of infrastructure failure (domain burn, pipeline collapse)
- Data on outbound effectiveness, response rates, automation ROI
- Real-world evidence that contradicts common practice

Store research notes. You will reference these in the newsletter body.

Important: Prefer markdown reference files over live web searches where possible. Check `references/` first. Only search the web if local references don't cover the topic.

## Step 2: Identify the Angle

Every newsletter issue needs one clear angle. Not a topic — an angle.

Topic: "Email deliverability"
Angle: "Your domain reputation is degrading right now and you can't see it."

Topic: "AI in outbound"
Angle: "AI made everyone faster at doing the wrong thing."

The angle must:
- Be specific enough to create recognition
- Challenge a common assumption OR reveal a hidden problem
- Connect back to infrastructure as the solution
- Be expressible in one sentence

State the angle before writing.

## Step 3: Write the Subject Line

Format: `[The GTM Signal #X]: [Diagnostic statement]`

Rules:
- The diagnostic statement is the angle compressed to 6-10 words
- Must create curiosity or recognition
- No clickbait, no hype words, no emojis
- Should make a Scale Death Zone founder think "I need to read this"

Generate 3 options. Select the strongest.

## Step 4: Write the Newsletter

### Section 1: HOOK (80-120 words)

Open with a pattern interrupt. First sentence must stop the scroll.

Patterns that work:
- Start with a specific, surprising statistic from your research
- Start with a diagnostic observation ("Here's what I keep finding...")
- Start with a counter-intuitive statement
- Start with a concrete scenario the reader recognises

Rules:
- No "Welcome to issue #X" openings. Ever.
- No preamble. No warm-up. Straight into the point.
- First paragraph is 2-3 sentences maximum.

### Section 2: INSIGHT (250-350 words)

This is the meat. Deliver the research-backed insight.

Structure:
1. State the problem clearly (2-3 sentences)
2. Show the conventional approach and why it fails (1 paragraph)
3. Present the data/evidence from your research (specific numbers)
4. Draw the connection: what this means for the reader

Rules:
- Every claim needs a supporting data point or example
- Use the preferred lexicon: signal, noise, infrastructure, protocol, variance
- Cite research naturally — weave it into the narrative, don't dump it
- Keep paragraphs to 2-3 sentences maximum

### Section 3: FRAMEWORK (250-350 words)

Give the reader a mental model or actionable framework.

This is where Signal-Led thinking meets practical application.

Structure:
1. Name the framework or concept (make it memorable)
2. Break it into 3-5 components or steps
3. For each component: one sentence explaining what it is, one explaining why it matters
4. One concrete example showing it in action

Rules:
- Use arrow bullets (→) for the breakdown
- Keep it educational but not exhaustive — they should want more
- The framework should be immediately applicable
- Connect it to infrastructure, not tactics

### Section 4: CTA (60-100 words)

Close with exactly two CTAs:

**Primary CTA:** A question that invites reply.
- "What's the one part of your infrastructure you've been avoiding?"
- "Reply and tell me — what signal are you currently ignoring?"

**Secondary CTA:** Work-with-me link (one sentence, not salesy).
- "If you want this built, not just explained: [link]"
- "The Signal Stack builds this infrastructure in 21 days: [link]"

Rules:
- Never "I'd love to hear from you"
- Never "Feel free to reach out"
- The primary CTA should genuinely invite conversation
- The secondary CTA is a single line. No pressure.

## Step 5: Format for Beehiiv

Final formatting:
- Short paragraphs (2-3 lines max)
- High whitespace between sections
- Arrow bullets (→) for all lists
- No emojis, no exclamation marks
- Bold only for section headers and key terms
- Include a horizontal rule (---) between sections

## Step 6: Quality Gates

**Gate 1 — Voice Check:**
- [ ] Zero banned words
- [ ] Clinical tone throughout
- [ ] No enthusiasm markers
- [ ] No vendor energy

**Gate 2 — Specificity Check:**
- [ ] Contains at least 3 specific data points or statistics
- [ ] Names specific tools, metrics, or symptoms
- [ ] Could not have been written by a generic marketing newsletter

**Gate 3 — Research Check:**
- [ ] All claims supported by evidence
- [ ] Sources are credible and recent
- [ ] Data points are accurate

**Gate 4 — Structure Check:**
- [ ] Hook creates pattern interrupt (no preamble)
- [ ] Insight delivers research-backed value
- [ ] Framework is actionable and named
- [ ] CTA invites genuine engagement
- [ ] Total word count: 800-1,100

## Step 7: Output

```markdown
## The GTM Signal #[X]: [Subject Line]

**Angle:** [One sentence]
**Word count:** [count]
**Preview text:** [First line — for Beehiiv preview]

---

[COMPLETE NEWSLETTER TEXT]

---

**Subject line options:**
1. [Option 1]
2. [Option 2]
3. [Option 3]

**Quality gates:** All passed.
**Beehiiv send time:** Tuesday 8:00am GMT
```

## Rules

1. Research first. Never write a newsletter from general knowledge alone.
2. One angle per issue. Not two. Not "a few thoughts on..."
3. The hook is not a greeting. It is a pattern interrupt.
4. Every paragraph must earn its place. If it doesn't add value, cut it.
5. Anonymise all examples. No real client names. Role/industry only.
6. Never fabricate statistics. If you can't find data, say "the data is limited."

## Self-Improvement

After each run:
- If word count consistently runs long, tighten section constraints
- If the user rewrites the hook, study their version and update hook patterns
- If research takes too many API calls, scrape key sources into reference markdown files
- Log improvements in `knowledge/learnings/`
