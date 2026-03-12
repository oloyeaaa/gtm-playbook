---
name: linkedin-creator
description: >
  Use when asked to write a LinkedIn post, LinkedIn carousel, or any LinkedIn content.
  Triggers on: "LinkedIn post", "write a post about", "carousel about",
  "post about", "LinkedIn content", "social post", or /linkedin-post.
  Handles both standard posts (under 1,300 chars) and multi-slide carousels.
---

# LinkedIn Creator Skill

## Goal

Produce a ready-to-publish LinkedIn post or carousel that sounds exactly like [Your Name] wrote it. Clinical. Specific. Diagnostic. Zero generic marketing language.

## Required Context

Before executing, load:
1. `knowledge/voice-guide.md` — Voice characteristics, banned words, preferred lexicon
2. `departments/content-media/references/linkedin-formats.md` — All 6 post format structures
3. `brands/gss/brand_assets/brand-guidelines.md` — Colours and typography (for carousels only)

## Step 1: Classify the Request

Determine output type:

- **Standard post** — Single text post, under 1,300 characters
- **Carousel** — Multi-slide visual sequence, 5-10 slides, 1080x1080px each

If the user does not specify, default to standard post.

## Step 2: Select Pillar and Format

If the user specifies a pillar and format, use those.

If not, classify the topic:

| Topic involves... | Pillar | Best Formats |
|-------------------|--------|--------------|
| Pain, symptoms, audits | Diagnosis | Audit, Diagnostic Question |
| How things work, infrastructure | System | Concept Breakdown, Audit |
| New mental models, frameworks | Signal | Concept Breakdown, Unpopular Take |
| Results, build documentation | Proof | Build Log, Before/After |
| Challenging conventional thinking | Perspective | Unpopular Take, Concept Breakdown |

Select the pillar and format that fits. State your selection before writing.

## Step 3: Write the Hook

The hook is the first line. It determines whether the post gets read.

Rules:
- 3 words maximum on line 1 (forces mobile scroll)
- 3-6 words total for the hook statement
- Creates a pattern interrupt
- NOT a question (unless Diagnostic Question format)
- No banned words

Hook formulas:

```
[Diagnostic statement.]       → "Your outbound is broken."
[Counter-intuitive claim.]    → "Sending more emails won't help."
[Specific number + fact.]     → "87 emails. 12 replies."
[Named problem.]              → "Domain Burn is silent."
[Direct address of pain.]     → "You've been burned before."
```

## Step 4: Write the Body

Follow the exact structure for the selected format:

**Format 1 — THE AUDIT:** Hook → "Here is what I find when I audit [X]:" → 5-7 arrow bullet findings → one-sentence reframe → soft CTA or none

**Format 2 — THE BEFORE/AFTER:** "Before The Signal Stack:" → 5 arrow bullets → blank line → "After The Signal Stack:" → 5 arrow bullets → one-sentence factual closer

**Format 3 — THE CONCEPT BREAKDOWN:** Hook → one-sentence definition → "Most [X] do Y. Signal-Led [X] do Z." → breakdown (numbered or bullets) → one-sentence implication

**Format 4 — THE UNPOPULAR TAKE:** Controversial statement → "I know that's not what you want to hear." → 3-5 argument points → evidence (numbers) → restate take with confidence

**Format 5 — THE BUILD LOG:** "Build Log: [what]. [time]." → context (2-3 lines) → what was built (arrow bullets) → result (numbers) → one-sentence lesson

**Format 6 — THE DIAGNOSTIC QUESTION:** Direct question → 4-5 sub-questions (arrow bullets) → "If you can't answer yes to all five, [reframe]."

Writing rules for ALL formats:
- Short lines. Maximum 8-10 words per line.
- High whitespace. Blank line every 1-3 lines.
- Arrow bullets (→) not dashes or dots.
- No emojis. No exclamation marks. No hashtags.
- Every line earns its place. Cut ruthlessly.

## Step 5: Write Carousel Slides (If Carousel)

Only execute this step if output type is carousel.

Carousel structure:
- Slide 1: Hook slide (bold statement, 3-6 words, brand colours)
- Slides 2-8: One point per slide (headline + 1-2 supporting lines)
- Final slide: CTA slide (what to do next)

Slide specifications:
- Dimensions: 1080x1080px
- Background: #07202b (dark navy)
- Headline text: White (#ffffff), bold
- Accent elements: #f17021 (signal orange)
- Slide number: Top-left, orange text (e.g., "3/8")
- Arrow or indicator: Bottom-right for navigation

For each slide, output:

```
SLIDE [N]/[TOTAL]
Headline: [Main text — bold, large]
Supporting: [1-2 lines — smaller, white]
Visual note: [Any specific layout instruction]
```

## Step 6: Quality Gates

Run every gate before delivering. All must pass.

**Gate 1 — Voice Check:**
- [ ] Zero banned words (scan against full list in voice-guide.md)
- [ ] No exclamation marks
- [ ] No emojis
- [ ] No hashtags
- [ ] Clinical tone, not enthusiastic
- [ ] Axiomatic statements, not hedged opinions

**Gate 2 — Specificity Check:**
- [ ] Contains at least one specific number
- [ ] Names at least one specific tool, symptom, or metric
- [ ] Could NOT have been written by a generic marketing agency
- [ ] Target reader thinks "this is my exact situation"

**Gate 3 — Signal Logic Check:**
- [ ] Prioritises precision over volume
- [ ] Positions infrastructure as solution (not tactics, not hacks)
- [ ] Repels wrong buyers (volume chasers, beginners)
- [ ] Attracts right buyers (Scale Death Zone founders)

**Gate 4 — Format Check:**
- [ ] Standard post: Under 1,300 characters
- [ ] Hook: 3 words maximum on first line
- [ ] High whitespace throughout
- [ ] Follows the selected format structure exactly

## Step 7: Output

**For standard posts:**

```markdown
## LinkedIn Post: [Topic]

**Pillar:** [pillar]
**Format:** [format name]
**Characters:** [count]

---

[THE COMPLETE POST]

---

**Quality gates:** All passed.
```

**For carousels:**

```markdown
## LinkedIn Carousel: [Topic]

**Pillar:** [pillar]
**Slides:** [count]

---

[SLIDE-BY-SLIDE BREAKDOWN]

---

**Quality gates:** All passed.
**Next step:** Generate slide visuals using infographic-builder skill or design tool.
```

## Rules

1. Never start with "I" on the first line.
2. Never use hedge phrases: "I think", "perhaps", "maybe", "in my opinion".
3. Never use vendor energy: "We'd love to", "Feel free to", "Don't hesitate".
4. Never end with "Let's connect" or "DM me" unless explicitly requested.
5. If the output sounds like it could have come from any agency, rewrite it.
6. Always anonymise. Never use real client names. Use role/industry descriptors.
7. Numbers must be specific (not "significant improvement" — say "8.4% vs 0.3%").
8. All LinkedIn image assets must have "gtmsignalstudio.com" overlaid at the bottom centre (Signal Orange #f17021, 18px Arial, 20px from bottom edge). This is the brand URL and is mandatory on every LinkedIn visual.

## Proven Examples

### Diagnostic Pattern — "Signal vs. Characteristic" (High Engagement)

This post resonated strongly with the audience. Use it as the benchmark for diagnostic-format posts.

**Format:** Concept Breakdown
**Pillar:** Signal
**Pattern:** Observation → Reframe → Paired comparison → Arrow list (wrong) → Arrow list (right) → Data point → CTA
**Reference image:** `departments/content-media/references/examples/linkedin-diagnostic-signal-vs-characteristic.png`

```
A job title is not a Signal.

Most agency founders treat them the same.

Here is the difference:

A characteristic describes who someone is.

A Signal describes what just changed.

"CEO of a 20-person marketing agency": Characteristic.

Static. True yesterday. True today. True next year.

"CEO of a 20-person marketing agency who just hired a VP of Sales" : Signal.

Time-stamped. Urgent. Indicates a problem that exists right now.

The first tells you who they are.

The second tells you why they will reply.

Most outbound targets characteristics.

That is why they gets ignored.

→ Job title is a characteristic
→ Company size is a characteristic
→ Industry is a characteristic
→ Technology used is a characteristic

None of these indicate timing.

A Signal does.

→ Just hired a VP of Sales: Building a pipeline, needs infrastructure
→ Just raised a round: Has budget, has pressure to grow
→ Actively hiring SDRs: Outbound motion starting, probably no system yet
→ Just migrated off HubSpot: Tech stack in flux, open to new tools

Same person. Different moment.

The moment is everything.

87 precision emails to Signal-triggered contacts outperform 1,000 emails to a static list.

Every time.

Follow me for more Signal-Led GTM conversations.
```

**Why it works:**

→ Opens with a 7-word diagnostic statement (hook)
→ Paired comparison makes the concept immediately tangible
→ Two arrow lists create visual rhythm (wrong → right)
→ Ends with a specific number (87 vs 1,000) — proof, not opinion
→ Zero banned words, zero emojis, zero exclamation marks
→ Reader leaves with a new mental model, not a vague takeaway

---

## Self-Improvement

After each run:
- If the user edits the post, note what they changed and why.
- If a banned word slipped through, add it to a local watchlist.
- If a format consistently gets edited the same way, update the format rules.
- Log improvements in `knowledge/learnings/`.
