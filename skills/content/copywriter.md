---
name: copywriter
description: >
  Cross-cutting copy optimization skill. Evaluates and improves hooks, titles,
  subject lines, and CTAs for all content types (blog, newsletter, LinkedIn,
  YouTube). Generates 3 scored alternatives per element using the 4U+S framework.
  Triggers on: invocation by any content agent between writing and image generation
  steps, or directly via "optimize copy", "score this hook", "copywriter", or /copywriter.
---

# Copywriter Skill

## Goal

Take any draft content and optimize the elements that determine whether someone stops scrolling: the hook, the title/subject line, and the CTA. For each element, generate 3 alternatives, score all options (including the original) using the 4U+S framework, and present the results for user selection. Minimum score to ship: 15/20.

## Required Context

Before executing, load:
1. `knowledge/voice-guide.md` — Voice characteristics, banned words (33), preferred lexicon

## Step 1: Receive and Classify

Receive the draft content and identify:

→ **Content type:** blog | newsletter | linkedin | youtube
→ **Draft hook/opening:** Extract the current hook
→ **Draft title/subject line:** Extract the current title or subject line
→ **Draft CTA:** Extract the current call-to-action
→ **Topic and angle:** Understand the core argument

If content type is not provided, classify from structure:
→ Markdown with H1 + meta description + schema = blog
→ "The GTM Signal #" or subject line present = newsletter
→ Under 1,300 characters, arrow bullets = linkedin
→ Timestamp sections + diagram instructions = youtube

## Step 2: Extract Elements

Pull out exactly the elements to optimize:

**Element 1 — Hook/Opening:**

| Content Type | What to Extract | Constraints |
|-------------|----------------|-------------|
| LinkedIn | First 1-2 lines before "See more" fold | Max 200 chars. 3 words max on line 1. |
| Newsletter | First paragraph (the pattern interrupt) | 80-120 words. No "Welcome to issue #X." |
| YouTube | Script hook section (0:00-0:30) | Under 75 words (30 seconds read-aloud). |
| Blog | Opening hook paragraph after H1 | 2-3 sentences. No throat-clearing. |

**Element 2 — Title/Subject Line:**

| Content Type | What to Extract | Constraints |
|-------------|----------------|-------------|
| LinkedIn | SKIP — LinkedIn has no title | — |
| Newsletter | Subject line | Under 44 chars. No "newsletter" word. No emojis. |
| YouTube | Video title | Under 60 chars. Front-load keyword. |
| Blog | H1 headline | Under 60 chars. Primary keyword in first 3 words. |

**Element 3 — CTA:**

| Content Type | What to Extract | Constraints |
|-------------|----------------|-------------|
| LinkedIn | Closing lines | Conversational. No "Let's connect." No vendor energy. |
| Newsletter | Primary CTA (reply question) + Secondary (link) | Primary = question. Secondary = one line. |
| YouTube | End-of-script action | Subscribe + one specific next step. |
| Blog | Dual CTA (question + link) | Primary = diagnostic question. Secondary = single link. |

Present the extracted originals before proceeding.

## Step 3: Score the Originals

Score each original using the **4U+S Framework:**

| Criterion | Question | Score |
|-----------|----------|-------|
| **U**rgent | Does it create timeliness? Reader feels "I need this now"? | 1-4 |
| **U**nique | Is the angle novel? Could a competitor have written this? | 1-4 |
| **U**seful | Does it promise practical, applicable value? | 1-4 |
| **U**ltra-specific | Numbers, names, concrete details? Not vague? | 1-4 |
| **S**ignal | Matches [Company] voice? Clinical, diagnostic, not hype? | 1-4 |

**Total: /20. Ship threshold: 15+. Below 15: must revise.**

Show the breakdown for each original.

## Step 4: Generate Alternatives

For each element, generate exactly 3 alternatives using the formulas below. Select formulas that fit the topic — do not force-fit.

### Hook Formulas

**LinkedIn:**
→ The Data Drop: `[Surprising Stat]. [Implication].`
→ The Contrarian Claim: `Everything you know about [topic] is wrong.`
→ The "Nobody Talks About": `The [adjective] [noun] nobody talks about.`
→ The Status Threat: `[X]% of [peers] are doing [thing]. You are probably not.`
→ The False Agreement: `[Common statement]. Wrong.`
→ The Confession: `I [did/believed something embarrassing]. [Transition to lesson].`
→ The Specific Timestamp: `[Time] ago, I [situation]. Today, [result]. Here is what changed:`

**Newsletter:**
→ Open with a specific, surprising statistic from research
→ Open with a diagnostic observation ("Here is what I keep finding...")
→ Open with a counter-intuitive statement
→ Open with a concrete scenario the reader recognises

**YouTube:**
→ The Problem Statement: `[Problem] is costing you [specific consequence].`
→ The Counter-Intuitive Open: `[Common advice] is the reason [bad outcome].`
→ The "I tested" Open: `I tested [approach] for [time]. Here is what happened.`

**Blog:**
→ The Diagnostic Open: `[Problem] is not a [wrong diagnosis]. It is a [correct diagnosis].`
→ The Data Open: `[Surprising stat]. [What it means].`
→ The Pattern Interrupt: `[Common belief]. The data says otherwise.`

### Title/Subject Line Formulas

**Newsletter Subject Lines:**
→ The Surprising Stat: `[Counter-intuitive number]: [implication]`
→ The Parenthetical Kicker: `[Statement] ([unexpected qualifier])`
→ The "I was wrong": `I was wrong about [topic]`
→ The PAS Micro: `[Pain in 3 words]. [Promise].`

**YouTube Titles:**
→ The Blueprint: `The [Adjective] [Topic] Blueprint for [Audience]`
→ The Exact Playbook: `The Exact [Process] I Used to [Result]`
→ The "Stop Doing X": `Stop [Common Practice] (Do This Instead)`
→ The "Why X Doesn't Work": `Why [Tactic] Doesn't Work (And What To Do Instead)`

**Blog Headlines:**
→ The Diagnostic: `[Problem] Is Not a [Wrong Diagnosis]. It Is a [Correct Diagnosis].`
→ The Numbers: `[Number] [Metric] > [Number] [Metric]. Here Is Why.`
→ The Data Study: `We Analyzed [Number] [Things]. Here Is What We Learned.`
→ The Contrarian: `Why [Common Practice] Is [Negative Outcome]`

### CTA Formulas (All Content Types)

→ The Soft Ask: `[Low-commitment verb] + [what they get]`
→ The Peer Proof: `Join [number] [peer title] who already [verb]`
→ The Conversational: `[Human phrasing of the ask]`
→ The Outcome CTA: `[Verb] + [the outcome, not the action]`
→ The Risk Reversal: `[Action]. [Explicit removal of risk].`

**CTA constraints by type:**
→ LinkedIn: Conversational. Never "DM me" or "Let's connect" unless requested.
→ Newsletter: Primary = reply-inviting question. Secondary = one-line work-with-me link.
→ Blog: Primary = diagnostic question. Secondary = single link.
→ YouTube: Subscribe + one specific next action.

## Step 5: Score All Alternatives

Score each alternative using the same 4U+S framework. Present comparison tables:

```
### Hook Options

| # | Hook | Urgent | Unique | Useful | Ultra-specific | Signal | Total |
|---|------|--------|--------|--------|----------------|--------|-------|
| 0 | [Original] | X | X | X | X | X | XX/20 |
| 1 | [Alt 1] | X | X | X | X | X | XX/20 |
| 2 | [Alt 2] | X | X | X | X | X | XX/20 |
| 3 | [Alt 3] | X | X | X | X | X | XX/20 |

→ Recommendation: Option [N] — [one-sentence reason]
```

Repeat for title/subject line (if applicable) and CTA.

## Step 6: Present for Selection

Present all scored options:

```
## Copywriter Report: [Content Type] — [Topic]

### Hook Options
[Scored table]
→ Recommendation: Option [N]

### Title/Subject Line Options (if applicable)
[Scored table]
→ Recommendation: Option [N]

### CTA Options
[Scored table]
→ Recommendation: Option [N]

---
To accept recommendations: "Use recommendations"
To pick specific options: "Hook 2, Title 1, CTA 3"
To revise: "Revise hook — more urgency"
```

Wait for user selection before proceeding.

## Step 7: Apply Selections

Replace the original elements with user's selections. Adjust surrounding sentences if needed for natural flow. Return the updated content to the calling agent.

## Quality Gates

**Gate 1 — Voice Compliance:**
- [ ] Zero banned words in all generated alternatives
- [ ] No exclamation marks
- [ ] No emojis
- [ ] Clinical, diagnostic tone — not enthusiastic, not salesy
- [ ] Arrow bullets (→) for any lists

**Gate 2 — Score Threshold:**
- [ ] All recommended options score 15+ out of 20
- [ ] If no option scores 15+, generate additional alternatives until threshold met

**Gate 3 — Constraint Compliance:**
- [ ] LinkedIn hooks: Under 200 chars, 3 words max on line 1
- [ ] Newsletter subjects: Under 44 chars, no "newsletter" word, no emojis
- [ ] YouTube titles: Under 60 chars, keyword front-loaded
- [ ] Blog headlines: Under 60 chars, keyword in first 3 words if possible
- [ ] CTAs match content-type constraints

**Gate 4 — Differentiation:**
- [ ] All 3 alternatives use different formulas
- [ ] No alternative is a trivial rewording of the original
- [ ] Each offers a meaningfully different angle

## Output

```markdown
## Copywriter Report: [Content Type] — [Topic]

**Elements optimized:** Hook, Title/Subject, CTA
**Score threshold:** 15/20 (4U+S)

---

[HOOK OPTIONS TABLE]
→ Recommendation: Option [N] ([score]/20)

[TITLE/SUBJECT LINE OPTIONS TABLE — if applicable]
→ Recommendation: Option [N] ([score]/20)

[CTA OPTIONS TABLE]
→ Recommendation: Option [N] ([score]/20)

---

**Quality gates:** All passed.
```

## Rules

1. Never use any of the 33 banned words. No exceptions.
2. Never use exclamation marks, emojis, or hashtags.
3. Never generate clickbait. Every hook must deliver on its promise in the content.
4. Never use hedge phrases: "I think", "perhaps", "maybe", "in my opinion."
5. Never use vendor energy: "We'd love to", "Feel free to", "Don't hesitate."
6. Scoring must be honest. Do not inflate scores. If the original is best, say so.
7. If all 4 options score below 15, generate 3 more. Repeat until one clears 15.
8. Always present the original as Option 0. The user may prefer it.
9. All alternatives must be immediately usable — no placeholders.
10. For LinkedIn: never start the hook with "I" on line 1.

## Self-Improvement

After each run:
→ If user consistently picks originals, study what alternatives lack. Update formula selection.
→ If user favours a specific formula, weight it higher for future runs.
→ If a generated option scores 18+ and user selects it, save topic + formula + output as a proven example below.
→ If a banned word slips through, log the failure.
→ If user edits a selected option, note what changed. Update the formula.
→ Log improvements in `knowledge/learnings/`.

### Proven Examples

(None yet — add after first successful runs.)
