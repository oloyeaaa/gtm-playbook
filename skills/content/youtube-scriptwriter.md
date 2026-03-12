---
name: youtube-scriptwriter
description: >
  Use when asked to write a YouTube video script. Triggers on: "youtube script",
  "write a script about", "video script", "youtube content", or /youtube-script.
  Produces structured talk-track scripts with timestamp sections and diagram instructions.
---

# YouTube Scriptwriter Skill

## Goal

Produce a ready-to-record YouTube video script that sounds exactly like [Your Name] speaking — clinical, specific, diagnostic, but conversational. This is talk-track, not essay. The viewer should feel like they are being taught by someone who has done the work, not someone selling a course.

## Required Context

Before executing, load:
1. `knowledge/voice-guide.md` — Voice characteristics, banned words, preferred lexicon
2. `knowledge/signal-types.md` — Signal categories for topic classification

## Step 1: Classify the Input

Determine input mode:

- **Mode A — Fresh topic**: Topic only. Research needed before scripting.
- **Mode B — Repurpose blog post**: Source blog post provided. Restructure for video (shorter sections, more hooks, talk-track voice, diagram focus).
- **Mode C — Content feed topic**: Topic pulled from `knowledge/topics/content-topics.md`. Research first, then script.

If the user provides a blog post or source material, default to Mode B. Otherwise, default to Mode A.

## Step 2: Research (Mode A and C Only)

If fresh topic or content feed topic, research using Perplexity. Focus on:

- 2-3 specific statistics or data points (numbers are retention anchors in video)
- Real examples or case studies (anonymised — no real client names)
- Counter-intuitive finding or contrarian angle (this becomes the hook)

Skip research entirely for Mode B — the blog post IS the research.

## Step 3: Write the Hook (0:00–0:30)

The hook determines whether the viewer stays. It must create a pattern interrupt within the first 10 seconds.

Rules:
- Open with a bold statement, not a question (questions feel weak on video)
- 1-2 sentences maximum
- Must be specific — name a number, a symptom, or a broken assumption
- Never open with "Hey guys" or "Welcome to my channel"
- The hook should make the viewer think: "Wait, really?"

Hook formulas:

```
[Specific number + surprising fact]     → "87 emails outperformed 1,000. Here's why."
[Counter-intuitive claim]               → "Your pipeline isn't broken. Your timing is."
[Named pain point]                      → "Domain burn is killing your outbound. Silently."
[Challenge a belief]                    → "More leads won't fix this."
```

## Step 4: Write the Script Body

### Section 1 — Context (0:30–1:30)

Set up why this matters. Who is this for. What problem are we solving.

- 2-3 short paragraphs
- Name the target viewer ("If you're running outbound for a B2B company...")
- State what most people get wrong (this is the "before" state)

**Diagram instruction:** Note what the Excalidraw should show during this section (e.g., "Show the broken pipeline: static list → generic email → silence").

### Section 2 — Core Content (1:30–6:00)

The meat. 3-4 key points, each clearly labelled.

Structure per point:
1. State the point (one sentence)
2. Explain why it matters (2-3 sentences, conversational)
3. Give a specific example or number
4. Transition to next point

Writing rules:
- Short sentences. 8-12 words average.
- Conversational cadence. Write how you speak, not how you write.
- Use rhetorical questions sparingly for retention ("So what does this actually mean?")
- Each point should map to a section of the Excalidraw diagram
- Arrow bullets (→) for lists, not dashes

**Diagram instruction:** For each key point, note what the Excalidraw should show (e.g., "Point 2: Show signal detection → qualification → timing window").

### Section 3 — CTA + Close (6:00–7:00)

One clear takeaway. One call-to-action.

- Restate the core insight in one sentence
- Tell the viewer what to do differently starting now
- CTA: Subscribe, comment, or check the link in description
- Do NOT oversell. One CTA only. Keep it brief.

## Step 5: Write Diagram Instructions

After the script, include a dedicated diagram section:

```
## Diagram Brief

Canvas: 1920x1080 (16:9)
Style: [Company] brand (dark navy #07202b, Signal Orange #f17021 accents)
Type: [flowchart / comparison / system map / process]

### Section 1 (0:30–1:30): [Description of what to show]
### Section 2 (1:30–3:30): [Description of what to show]
### Section 3 (3:30–6:00): [Description of what to show]

Note: Diagram should work as a single static image that the presenter walks through section by section.
```

## Step 6: Quality Gates

Run every gate before delivering. All must pass.

**Gate 1 — Voice Check:**
- [ ] Zero banned words (scan against full list in voice-guide.md)
- [ ] No exclamation marks
- [ ] No emojis
- [ ] Clinical tone, not enthusiastic
- [ ] Conversational cadence — sounds spoken, not written

**Gate 2 — Specificity Check:**
- [ ] Contains at least 2 specific numbers or data points
- [ ] Names at least one specific tool, symptom, or metric
- [ ] Could NOT have been scripted by a generic content agency
- [ ] Real examples (anonymised if needed), not hypotheticals

**Gate 3 — Structure Check:**
- [ ] Hook is under 30 seconds when read aloud (~75 words max)
- [ ] Total script is 1,000-1,200 words (~7-8 min read-aloud)
- [ ] 3-4 key points in core content (not more, not less)
- [ ] Each section has a diagram instruction
- [ ] Single CTA at the end

**Gate 4 — Signal Logic Check:**
- [ ] Prioritises precision over volume
- [ ] Positions infrastructure as solution (not tactics, not hacks)
- [ ] Viewer leaves with a new mental model, not just information

## Step 7: Output

```markdown
## YouTube Script: [Topic]

**Input mode:** [A: Fresh / B: Repurpose / C: Feed topic]
**Duration:** ~[X] minutes
**Word count:** [count]

---

### HOOK (0:00–0:30)

[Hook text]

### CONTEXT (0:30–1:30)

[Context text]

[DIAGRAM: Description of what to show]

### POINT 1: [Title] (1:30–X:XX)

[Point text]

[DIAGRAM: Description of what to show]

### POINT 2: [Title] (X:XX–X:XX)

[Point text]

[DIAGRAM: Description of what to show]

### POINT 3: [Title] (X:XX–X:XX)

[Point text]

[DIAGRAM: Description of what to show]

### CTA + CLOSE (X:XX–X:XX)

[Close text]

---

## Diagram Brief

[Full diagram specification]

---

## YouTube Metadata

**Title:** [Under 60 characters]
**Description:** [SEO-optimised, includes timestamps]
**Tags:** [5-8 relevant tags]

---

**Quality gates:** All passed.
```

## Rules

1. Never start with "Hey guys", "What's up", or any generic YouTube opener.
2. Never use hedge phrases: "I think", "perhaps", "maybe", "in my opinion".
3. Never use vendor energy: "smash that like button", "ring the bell".
4. Write for spoken delivery — short sentences, natural pauses, breathing room.
5. Numbers must be specific (not "significant improvement" — say "8.4% vs 0.3%").
6. All data must be real or clearly omitted. Never fabricate proof points.
7. The script should work as a standalone read — if someone reads the transcript, it should still deliver value.
8. Always anonymise. Never use real client names. Use role/industry descriptors.

## Self-Improvement

After each run:
- If the user edits the script, note what they changed and why.
- If a banned word slipped through, add it to a local watchlist.
- If a section consistently gets trimmed, adjust the word count guidance.
- If a hook style resonates (user feedback), save as proven example.
- Log improvements in `knowledge/learnings/`.
