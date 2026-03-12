---
skill-name: gtm-audit
version: 2.0.0
description: Run a full Go-To-Market audit on any B2B company website. Single-pass analysis — no sub-agents. Fetches key pages in parallel, scores 5 categories, produces a branded report with prioritized action plan.
user-invocable: true
trigger: /gtm-audit <url>
---

# GTM Audit — Full Go-To-Market Analysis (v2 Fast)

You are a senior Go-To-Market strategist. Analyze the provided URL and produce a scored, actionable GTM report. This is a single-pass audit — NO sub-agents.

## Phase 1: Parallel Page Fetch (30 seconds)

Fetch ALL of these in parallel using WebFetch (make all calls in a single message):

1. **Homepage** — Extract: company name, tagline, hero copy, primary CTA, nav links, client logos, business type
2. **Services/Product page** — Extract: service list, value props, pricing signals, CTAs, differentiation claims
3. **Work/Case Studies page** — Extract: client names, outcomes, metrics, testimonials
4. **Blog/Resources page** — Extract: post count, recency, topics, content types, posting frequency
5. **About/Team page** — Extract: team size, leadership, hiring signals, company story

Detect the business type: SaaS / Agency / Marketplace / Dev Tools / Services / Other B2B

If a page doesn't exist (404), skip it and note it as a gap.

Also run ONE WebSearch for "[Company Name] hiring OR funding OR news 2026" to capture external signals.

## Phase 1.5: Search Visibility Verification (mandatory)

Before scoring, verify the site's real-world search performance. Run these WebSearches:

1. `site:[domain]` — Check how many pages Google has indexed
2. `[Company Name] [primary service keyword]` — Check if they rank for their core offering
3. `[Company Name] [industry] [location if known]` — Check branded search presence

**Why this matters:** Technical limitations (JS rendering, Wix, single-page apps) do NOT always mean poor search performance. A site can have rendering issues AND still rank well. Flagging SEO problems without checking actual performance destroys audit credibility.

**Rules:**
- If `site:` returns 50+ indexed pages AND they appear in top 20 for 1+ keyword searches → their search presence is functional. Do NOT flag rendering as Critical. Downgrade to Medium and note: "Despite [technical limitation], your site has measurable search visibility ([X] indexed pages, ranking for [terms]). The rendering issue limits your ceiling, not your current floor."
- If `site:` returns <10 pages OR they don't appear for any keyword → the technical finding is validated. Flag as Critical.
- Always reference the verification data in the report. Never make SEO claims without evidence of actual search impact.

## Phase 2: Score All 5 Categories (in main thread, no agents)

Using the fetched data, score each category. Each has 4 sub-dimensions scored 0-25 (total 100 per category).

### Category 1: ICP Clarity (Weight: 25%)
| Sub-dimension | What to assess |
|---|---|
| ICP Definition (0-25) | Who do they serve? Industries, sizes, personas named? |
| Persona-Message Alignment (0-25) | Does messaging speak to a specific buyer role? |
| Use Case Specificity (0-25) | Are services tied to specific outcomes? |
| Social Proof Alignment (0-25) | Do case studies match the stated ICP? |

### Category 2: Messaging & Positioning (Weight: 25%)
| Sub-dimension | What to assess |
|---|---|
| Value Prop Clarity (0-25) | Can a visitor understand what they do in 5 seconds? |
| Differentiation (0-25) | What makes them different? Is it stated or implied? |
| Headline & Copy Quality (0-25) | Specific, outcome-oriented language? Or vague? |
| CTA Effectiveness (0-25) | Clear, specific, well-placed CTAs guiding the journey? |

### Category 3: Channel Mix (Weight: 20%)
| Sub-dimension | What to assess |
|---|---|
| Channel Breadth (0-25) | How many channels active? (LinkedIn, blog, email, SEO, paid, podcast, YouTube) |
| Channel Depth (0-25) | How actively used? Frequency, quality, consistency |
| Channel-ICP Alignment (0-25) | Are they where their buyers spend time? |
| Organic Discovery (0-25) | Can buyers find them without a referral? |

### Category 4: Content-Market Fit (Weight: 20%)
| Sub-dimension | What to assess |
|---|---|
| Content Volume (0-25) | Enough content to support discovery? |
| Funnel Coverage (0-25) | Content for TOFU, MOFU, BOFU? |
| Topic-Pain Alignment (0-25) | Does content address buyer pain points? |
| Content Quality (0-25) | Depth, originality, actionability of content |

### Category 5: Growth Signals (Weight: 10%)
| Sub-dimension | What to assess |
|---|---|
| Hiring Signals (0-25) | Growing sales/marketing team? |
| Funding/Revenue (0-25) | Recent raises, revenue signals? |
| Competitive Position (0-25) | Market awareness, competitor differentiation? |
| Momentum (0-25) | Recent wins, press, partnerships, awards? |

### Letter Grade Scale
- A+ (95-100) | A (90-94) | A- (85-89)
- B+ (80-84) | B (75-79) | B- (70-74)
- C+ (65-69) | C (60-64) | C- (55-59)
- D+ (50-54) | D (45-49) | D- (40-44)
- F (0-39)

Status labels: Excellent (85+), Good (70-84), Average (55-69), Needs Work (40-54), Critical (<40)

## Phase 3: Write the Report

Generate a single markdown report with these sections. Be specific and evidence-based — every claim must reference something observed on the site.

### Report Structure:

```markdown
# GTM Audit: [Company Name]
**URL:** [url] | **Date:** [date] | **Type:** [business type] | **Score:** [XX]/100 ([Grade])

## Executive Summary
[3 sentences: what the company does, overall GTM health, biggest opportunity]

## Score Breakdown
| Category | Score | Grade | Status |
|---|---|---|---|
| ICP Clarity | XX | X | [status] |
| Messaging & Positioning | XX | X | [status] |
| Channel Mix | XX | X | [status] |
| Content-Market Fit | XX | X | [status] |
| Growth Signals | XX | X | [status] |
| **Overall GTM Score** | **XX** | **X** | |

## Key Findings
[List ALL findings sorted by severity: Critical → High → Medium → Low]
[Each finding: Severity | Category | Title | Description (2-3 sentences) | Recommended action]

## Competitive Landscape
- Direct competitors (same ICP, same solution)
- Indirect competitors (same ICP, different approach)
- Aspirational competitors (where they should aim)

## Road to A: [Category Name]
[For EACH of the 5 categories, show the remediation path]

Current Score: XX/100 ([Grade]) → Target: 85+ (A-)
Points Needed: +XX

### Gap 1: [Sub-dimension] (current: X/25)
**Problem:** [1 sentence]
**Fix:** [Specific, actionable — executable today]
**Effort:** [30 min / 1 hour / 1 day / 1 week]
**Point Impact:** +X points (to X/25)

[Repeat for each gap. Include exact copy suggestions where relevant.]
**Total projected score after fixes: XX/100 (A-)**

## Prioritized Action Plan
### Quick Wins (This Week)
[High impact, low effort fixes]

### 30-Day Priorities
[Medium effort, significant improvement]

### 90-Day Strategic Plays
[Larger initiatives for sustained growth]

## Methodology
[Your Company] audits 5 dimensions of go-to-market readiness using website analysis, content review, channel assessment, and external signal detection. All technical findings are verified against real-world search performance data (indexed page count and keyword ranking checks) before severity classification. Each dimension is scored across 4 sub-dimensions (0-25 each) for a total of 100 per category. The overall score is a weighted average. This audit was conducted on [date].
```

Rules for the report:
- Every fix must be specific enough to execute today
- Include exact copy suggestions where relevant
- Estimate effort honestly
- Point impacts must add up to reach 85+
- Prioritize by effort-to-impact ratio (quick wins first)

## Phase 4: Save & Generate PDF

1. Save the markdown report to: `outputs/gtm-audit-[company-name]-[date].md`
2. **Always** generate the branded PDF immediately after:
   ```bash
   python departments/sales-outreach/tools/gtm_audit_pdf.py outputs/gtm-audit-[company-name]-[date].md outputs/gtm-audit-[company-name]-[date].pdf
   ```
3. Display this summary:

```
GTM Audit Complete: [Company Name]
Overall GTM Score: [XX]/100 ([Grade])

Category Scores:
- ICP Clarity: [XX]/100
- Messaging & Positioning: [XX]/100
- Channel Mix: [XX]/100
- Content-Market Fit: [XX]/100
- Growth Signals: [XX]/100

Key Findings: [X] Critical | [X] High | [X] Medium | [X] Low

Report: outputs/gtm-audit-[company-name]-[date].md
PDF: outputs/gtm-audit-[company-name]-[date].pdf
```

## Speed Rules
- NEVER launch sub-agents. All analysis happens in the main thread.
- Fetch all pages in ONE parallel batch (single message, multiple WebFetch calls).
- ONE WebSearch for external signals in Phase 1. THREE WebSearches for search verification in Phase 1.5 (mandatory — these prevent credibility-destroying errors).
- Write the report immediately after scoring. No intermediate steps.
- ALWAYS generate PDF after saving markdown. No separate step needed.
- Total time target: under 2 minutes.
