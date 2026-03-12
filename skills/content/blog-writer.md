---
name: blog-writer
description: >
  Write research-backed blog posts for gtmsignalstudio.com optimised for both
  SEO and AEO (AI citation). Includes meta description, internal link suggestions,
  and a companion LinkedIn teaser post. Triggers on: "blog post about", "write a
  blog", "article about", "pillar article", "blog for the website", or /blog-writer.
---

# Blog Writer

## Goal

Research a topic, then produce a complete blog post optimised for both Google
rankings and AI agent citations, plus meta description, internal link map, and
companion LinkedIn teaser post.

## Required Context

Before executing, load:
1. `knowledge/voice-guide.md` — Voice standards, banned words, preferred lexicon
2. `departments/content-media/references/aeo-guide.md` — AEO structure, schema markup, question clusters
3. `departments/content-media/references/blog-structure.md` — Blog format, title formulas, publishing checklist
4. `knowledge/signal-types.md` — Signal categories (for topic relevance)
5. `brands/gss/brand_assets/brand-guidelines.md` — Brand colours, formatting (only if visual elements needed)

## Step 1: Classify the Input

Determine what the user has provided:

**A. Topic only** ("write a blog about domain burn")
→ Full research required. Proceed to Step 2.

**B. Topic + angle** ("blog about why SDR hires fail, from the infrastructure perspective")
→ Targeted research. Proceed to Step 2 with angle locked.

**C. Topic + source material** ("turn this YouTube script into a blog post")
→ Skip research. Extract key points from source. Proceed to Step 4.

**D. Content pillar request** ("write the AEO pillar article for question cluster 2")
→ Load AEO question clusters from aeo-guide.md. Proceed to Step 2 with pillar constraints.

If pillar article (D): word count target is 1,500+ (AEO minimum). All other types: 950-1,100 words.

## Step 2: Research

Research the topic before writing. Check local references first, then search externally.

### 2a: Internal Research (check first — saves tokens)

Scan these for relevant data:
- `knowledge/signal-types.md` — Does this topic map to a signal category?
- `departments/content-media/references/aeo-guide.md` — Is there a question cluster this maps to?
- `examples/alluvium-build.md` — Any relevant anonymised proof points?
- Existing blog posts or newsletters in project files

Extract:
- Specific numbers or metrics
- Frameworks already documented
- Proof points (anonymised)
- Question clusters this post should target

### 2b: External Research (if gaps remain)

Search for 3-5 external sources. Prioritise:
1. Industry research and reports (specific data points)
2. Platform documentation (Apollo, Clay, Smartlead — for technical accuracy)
3. Competitor analysis (what others say about this topic — find the gap)

For each source, extract:
- One specific statistic or data point
- The conventional wisdom (so we can challenge or build on it)
- Any gaps in their coverage (our angle)

Do NOT extract generic advice. Only extract specific, citable information.

### 2c: Research Summary

Before writing, compile a brief:

```
TOPIC: [topic]
ANGLE: [the specific position we're taking]
PRIMARY KEYWORD: [target keyword for SEO]
SECONDARY KEYWORDS: [2-3 supporting terms]
AEO QUESTION: [the question a prospect would ask an AI agent]
DATA POINTS: [3-5 specific numbers/facts from research]
GAP: [what others miss that we'll address]
PILLAR: [diagnosis | system | signal | proof | perspective]
```

Present this to the user for approval before writing. Wait for confirmation.

## Step 3: Title Selection

Generate 3 title options using these formulas:

**The Diagnostic:**
```
[Problem] Is Not a [Wrong Diagnosis]. It's a [Correct Diagnosis].
```

**The Framework:**
```
[Framework Name]: [Benefit/Outcome]
```

**The Symptom:**
```
[Symptom] — [What It Actually Means]
```

**The Numbers:**
```
[Number] [Metric] > [Number] [Metric]. Here's Why.
```

**The Contrarian:**
```
Why [Common Practice] Is [Negative Outcome]
```

Rules for titles:
- Primary keyword in the first 3 words where possible
- Under 60 characters (SEO meta title limit)
- No banned words
- No clickbait — diagnostic, not sensational

Present 3 options. Recommend the strongest. Wait for user selection (or proceed if user said "just write it").

## Step 4: Write the Blog Post

Follow this structure exactly:

### 4a: The Short Answer (AEO layer)

First 2-3 sentences must directly answer the AEO question identified in Step 2.
This is the section AI agents will extract and cite.

Requirements:
- Directly answers the target question
- Contains a specific, quotable statement
- Includes the primary keyword
- Could stand alone as a complete answer
- Under 50 words

### 4b: Hook

The opening line after The Short Answer. Pattern interrupt.

- 1 sentence maximum
- Clinical observation, not a question (unless diagnostic question format)
- Creates recognition: reader thinks "that's me"

### 4c: Problem Statement

Name the pain. 3-4 sentences.

- Specific symptoms, not categories
- Include at least one number
- Name the tools or situations they'd recognise
- End with the misdiagnosis ("The problem isn't X. It's Y.")

### 4d: Why Conventional Solutions Fail

2-3 paragraphs explaining what they've tried and why it didn't work.

- Name the common advice
- Explain why it's insufficient (not wrong — insufficient)
- Build toward the actual root cause
- Use data points from research

### 4e: The Concept/Framework

Main teaching section. This is the core value.

- Name the concept or framework clearly
- Define it in one sentence
- Explain how it works in 3-5 specific steps
- Use the preferred lexicon (Signal, Infrastructure, Protocol, etc.)
- Include at least one concrete example (anonymised)

### 4f: Evidence

Proof section. 1-2 paragraphs.

- Specific numbers from research or anonymised client work
- Before/after comparisons where possible
- Never use real client names — role/industry descriptors only
- Data speaks. Commentary is minimal.

### 4g: Implication

"What this means for you" section. 2-3 sentences.

- Restate the choice (continue current path vs. build infrastructure)
- Name the specific consequence of inaction
- Name the specific outcome of action
- No hype. Just the diagnostic reality.

### 4h: CTA

Two CTAs. Always these two:

```markdown
---

**Get weekly Signal-Led GTM breakdowns**

Every Tuesday. One insight. No fluff.

Subscribe to The GTM Signal → [newsletter link]

**Ready to build your Signal Stack?**

If you're generating £50k-£150k/mo and your pipeline still depends on
referrals and founder effort — this is what the Signal Stack is built for.

→ 21-day build
→ 3 hours of your time total
→ Full infrastructure handoff

Learn more → [work-with-me link]
```

## Step 5: AEO Optimisation Layer

After writing the post, add AEO elements:

### 5a: FAQ Section

Add 3-5 related questions and answers at the bottom of the post (before CTA).
These target the question cluster identified in Step 2.

Format:
```markdown
## Frequently Asked Questions

**[Question 1]**
[2-3 sentence direct answer. Specific. Quotable.]

**[Question 2]**
[2-3 sentence direct answer.]
```

Rules:
- Questions must be phrased as a prospect would ask an AI agent
- Answers must be self-contained (make sense without reading the full post)
- Include specific numbers or frameworks in answers
- No filler. Every answer must be citable.

### 5b: Schema Markup

Generate Article Schema + FAQ Schema for the post:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "[Post Title]",
  "author": {
    "@type": "Person",
    "name": "[Your Name]",
    "jobTitle": "Founder, [Your Company]",
    "url": "https://gtmsignalstudio.com/about"
  },
  "publisher": {
    "@type": "Organization",
    "name": "[Your Company]",
    "url": "https://gtmsignalstudio.com"
  },
  "datePublished": "[YYYY-MM-DD]",
  "description": "[Meta description]",
  "about": {
    "@type": "Thing",
    "name": "[Primary topic]"
  }
}
</script>
```

Generate FAQ Schema separately for the FAQ section.

## Step 6: Companion Outputs

### 6a: Meta Description

Write a meta description for the post:
- 150-160 characters exactly
- Includes primary keyword
- Diagnostic tone — names the problem
- Ends with implied value (not a CTA)

Generate 2 options. Recommend the strongest.

### 6b: Internal Link Suggestions

Suggest 3-5 internal links based on the post content:

```
INTERNAL LINKS:

1. [Anchor text] → /[page-slug] (context: [why this link makes sense])
2. [Anchor text] → /[page-slug]
3. [Anchor text] → /work-with-me (always include this one)
```

Link to:
- Related blog posts (if they exist)
- The /work-with-me page (always)
- The newsletter signup (always)
- Any relevant case studies or resources

### 6c: Companion LinkedIn Post

Write a LinkedIn teaser post that drives traffic to the blog.

Requirements:
- Under 1,300 characters
- Hook is 3-6 words (first line)
- Does NOT repeat the blog post — teases the core insight
- Ends with: "Full breakdown on the blog. Link in comments."
- Follow the voice guide exactly
- Map to a content pillar and format from linkedin-formats.md

## Step 7: Quality Gates

Run every gate before delivering. All must pass.

**Gate 1 — Voice Check:**
- [ ] Zero banned words (scan the full document)
- [ ] No exclamation marks
- [ ] No emojis
- [ ] Clinical tone throughout — not enthusiastic, not salesy
- [ ] Axiomatic statements present
- [ ] Preferred lexicon used naturally

**Gate 2 — Specificity Check:**
- [ ] Contains at least 3 specific numbers
- [ ] Names specific tools, symptoms, or situations
- [ ] Could NOT have been written by a generic marketing agency
- [ ] Target reader thinks "this is my exact situation"
- [ ] Hard filter present (who this is NOT for)

**Gate 3 — SEO Check:**
- [ ] Primary keyword in title (first 3 words if possible)
- [ ] Primary keyword in first 100 words
- [ ] Primary keyword in at least one H2
- [ ] 2-3 secondary keywords used naturally throughout
- [ ] Word count: 950-1,100 words (or 1,500+ for pillar articles)
- [ ] Meta description: 150-160 characters with keyword

**Gate 4 — AEO Check:**
- [ ] Short Answer section directly answers the target AI question
- [ ] Short Answer is under 50 words and quotable
- [ ] FAQ section has 3-5 questions phrased as AI queries
- [ ] FAQ answers are self-contained and citable
- [ ] Article Schema + FAQ Schema generated
- [ ] Clear H2/H3 hierarchy for AI parsing

**Gate 5 — Signal Logic Check:**
- [ ] Prioritises precision over volume
- [ ] Positions infrastructure as the solution
- [ ] Repels wrong buyers, attracts right buyers
- [ ] Follows The Signal Stack framework where applicable

## Step 8: Output

Deliver the complete package:

```markdown
# BLOG POST: [Title]

**Primary keyword:** [keyword]
**Word count:** [count]
**Pillar:** [pillar]
**AEO question:** [target question]

---

## Meta Description

[Selected meta description — 150-160 chars]

---

## Blog Post

[Full post content with all sections]

---

## Schema Markup

[Article Schema JSON-LD]
[FAQ Schema JSON-LD]

---

## Internal Links

[Link suggestions with context]

---

## Companion LinkedIn Post

[Full LinkedIn teaser post]
**Characters:** [count]

---

## Publishing Checklist

- [ ] Post uploaded to WordPress
- [ ] Meta title set (under 60 chars)
- [ ] Meta description set
- [ ] URL slug: /blog/[keyword-slug]
- [ ] Featured image: 1200x630px, brand colours
- [ ] Schema markup added
- [ ] Internal links inserted
- [ ] External links open in new tab
- [ ] Newsletter CTA present
- [ ] YouTube embed added (if related video exists)
- [ ] LinkedIn teaser scheduled
```

## Rules

1. Always research before writing. No post goes out without data backing the claims.
2. The Short Answer section is mandatory. This is the AEO extraction point.
3. Never use real client names. Always anonymise with role/industry descriptors.
4. Every post must have both CTAs (newsletter + work-with-me). No exceptions.
5. Schema markup is not optional. Generate it for every post.
6. The LinkedIn companion post must tease, not repeat. Different angle, same core insight.
7. If the user provides source material (YouTube transcript, notes), use it as the foundation but still apply the full blog structure. Do not just reformat — restructure.

## Self-Improvement

After each run:
- If a title formula consistently wins, note it and prioritise in future suggestions
- If certain question clusters get requested repeatedly, pre-load that research
- If the AEO Short Answer gets revised by the user, study the revision and update the approach
- If schema markup patterns change (new schema types become relevant), update the template
- Track which internal links are suggested most — may indicate content gaps to fill
- Log improvements in `knowledge/learnings/`
