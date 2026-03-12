---
name: signal-stack-blueprint
description: >
  Build a personalised Signal Stack Blueprint for a B2B prospect. Maps their ICP,
  identifies the 3-5 buying signals most relevant to their business, shows where to
  detect each signal, provides ready-to-send outreach messages, and outlines the
  detection infrastructure. Outputs a branded PDF deliverable.
  Triggers on: "signal stack", "signal blueprint", "build a blueprint for",
  "signal stack blueprint", "lead magnet for", or /so-signal-stack-blueprint.
---

# Signal Stack Blueprint Skill

## Goal

Produce a personalised, research-backed Signal Stack Blueprint for a specific B2B prospect. The blueprint shows them exactly which buying signals matter for their ICP, where to detect them, what to say when each fires, and how to wire the infrastructure together. Output: branded PDF delivered to outputs/.

This is a lead magnet — not a checklist. It is a custom infrastructure map that the prospect cannot produce themselves from a LinkedIn post.

## Required Context

Before executing, load:
1. `knowledge/voice-guide.md` — Voice, banned words, lexicon
2. `knowledge/signal-funnel.md` — Lane routing context
3. `founder/profile.md` — For personalisation and credibility framing

## Required Inputs

The user must provide (or you must research):
1. **Company name** — Who the blueprint is for
2. **Contact name and role** — The person receiving it
3. **Industry** — What sector they operate in
4. **Their ICP** — Who do they sell to? (If unknown, research their website first)

## Phase 1: Research the Prospect

Before writing anything, understand their business.

1. **Fetch their website** — WebFetch homepage + about/services pages
2. **Identify their ICP** — From their website: who do they sell to? What size companies? What roles? What geography?
3. **Identify their current GTM motion** — Do they have content? Outbound? Referrals only? Inbound?
4. **Note gaps** — What signals would be most valuable given their ICP and current motion?

If you already ran a GTM audit on this company, reference those findings. The blueprint should build on the audit, not repeat it.

## Phase 2: Select 3-5 Signals

Choose the buying signals most relevant to their specific ICP. Do NOT use generic signals — tailor to their industry and buyer.

### Signal Selection Criteria

For each signal, it must pass these tests:
→ **Detectable** — Can it be found using available tools (Sales Navigator, SignalBase, BuiltWith, LinkedIn, Crunchbase, Google Alerts)?
→ **Time-sensitive** — Does it create a window of opportunity (not a static characteristic)?
→ **Budget-linked** — Does it indicate the prospect has or will have budget?
→ **Relevant to their ICP** — Would this signal actually matter for the people they sell to?

### Common Signal Categories (adapt to their ICP)

| Signal Type | Best For | Detection Source |
|-------------|----------|-----------------|
| Senior hire (VP/Head of) | Agencies, SaaS, consulting | LinkedIn job changes, Sales Navigator |
| Funding round | SaaS, startups, tech | Crunchbase, SignalBase, TechCrunch |
| SDR/BDR hiring spike | Agencies selling outbound | LinkedIn job postings, SignalBase |
| Tech stack migration | MarTech, SaaS, dev tools | BuiltWith, G2, LinkedIn posts |
| Content team restructure | Content agencies, SEO | LinkedIn job changes, blog activity |
| Office expansion / new market | Consulting, local services | LinkedIn, Companies House, press |
| Regulatory change impact | Compliance, legal, finance | Google Alerts, industry publications |
| Competitor customer churn | Any B2B with clear competitors | G2 reviews, LinkedIn posts, job boards |
| Partnership/acquisition | PE-backed, M&A advisory | Crunchbase, press releases |
| Conference speaker/sponsor | Events, sponsorship, PR | Event websites, LinkedIn |

Choose 3-5 signals that are most relevant. Quality over quantity.

## Phase 3: Write the Blueprint

Use this exact markdown structure:

```markdown
# Signal Stack Blueprint

**Company:** [Company Name]
**Prepared for:** [Contact Name, Role]
**Date:** [Month Year]
**Industry:** [Their industry and size]
**ICP:** [Summary of who they sell to]

## ICP Definition

→ **Who they sell to:** [Target buyer description]
→ **Company size:** [Employee range, revenue range]
→ **Geography:** [Markets they serve]
→ **Decision maker:** [Title/role of the person who buys from them]
→ **Budget range:** [Typical deal size if known]
→ **Core pain:** [The main problem their ICP faces — this is what signals indicate]

## Signal Stack

### [Signal 1 Name]

**What it means:** [Why this signal indicates buying intent for their ICP]
**Detection source:** [Where to find this signal]
**Tools:** [Specific tools to use]
**Timing window:** [How soon after the signal to act]
**Outreach message:** "[Ready-to-send message with {variables}]"
**Priority:** [High/Medium/Low with rationale]

### [Signal 2 Name]
[Same structure]

### [Signal 3 Name]
[Same structure]

[Optionally signals 4 and 5]

## Detection Infrastructure

### Daily monitoring ([X] minutes)
→ [Specific daily actions]

### Weekly scan ([X] minutes)
→ [Specific weekly actions]

### Tools required
→ [Tool 1] — [What it detects]
→ [Tool 2] — [What it detects]

### Automation potential
→ [What can be automated and how]

## Action Plan

1. **This week:** [First action]
2. **This week:** [Second action]
3. **Week 2:** [Third action]
4. **Week 2:** [Fourth action]
5. **Week 3:** [Fifth action]
6. **Week 4:** [Sixth action]
7. **Ongoing:** [Maintenance routine]
```

### Writing Rules

→ Every signal must have all 6 fields (what it means, detection source, tools, timing window, outreach message, priority)
→ Outreach messages must be specific to their ICP — not generic templates
→ The action plan must be implementable in 4 weeks
→ Use the prospect's actual company name and ICP throughout — this is personalised, not generic
→ Infrastructure section must include time commitments (minutes per day/week)
→ Tools must be real and currently available (no hypothetical tools)
→ Prefer free-tier tools where possible

## Phase 4: Generate PDF

After writing the markdown, always generate the branded PDF:

```
python departments/sales-outreach/tools/signal_stack_blueprint_pdf.py <input.md> <output.pdf>
```

### File Naming Convention
→ Markdown: `outputs/signal-stack-blueprint-{company-slug}-{YYYY-MM-DD}.md`
→ PDF: `outputs/signal-stack-blueprint-{company-slug}-{YYYY-MM-DD}.pdf`

## Phase 5: Quality Gates

**Gate 1 — Personalisation Check:**
- [ ] Company name appears in at least 5 places
- [ ] ICP is specific to their business (not generic "B2B companies")
- [ ] Signals are tailored to their ICP (not a generic list)
- [ ] Outreach messages reference their specific buyer persona

**Gate 2 — Signal Quality Check:**
- [ ] Every signal is time-sensitive (not a static characteristic)
- [ ] Every signal has a clear detection source and tool
- [ ] Every signal has a timing window
- [ ] Every outreach message is ready to send (with obvious {variables} for personalisation)

**Gate 3 — Infrastructure Check:**
- [ ] Daily and weekly time commitments are realistic (under 3 hours/week total)
- [ ] All tools listed are real and available
- [ ] Automation suggestions are implementable
- [ ] Action plan is sequenced logically over 4 weeks

**Gate 4 — Voice Check:**
- [ ] Zero banned words
- [ ] Clinical, diagnostic tone
- [ ] No vendor energy or hype
- [ ] Reads like a consultant's deliverable, not a marketing PDF

## Phase 6: Present to User

After PDF is generated, present:
1. Summary of the 3-5 signals selected and why
2. The PDF file path
3. Suggested delivery method (email, DM, or post-audit follow-up)

## How This Fits the Signal Funnel

| Funnel Stage | Usage |
|---|---|
| Lane 1 (LinkedIn) | Tease the concept: "I mapped 5 buying signals for a B2B agency this week..." |
| Lane 2 (Outreach) | Follow-up after GTM audit: "I also mapped your signal stack" |
| The Bridge | Pair with GTM audit: audit shows what's broken, blueprint shows what to build |
| Lane 3 (Newsletter) | Teach the framework: "Here's how I build a Signal Stack for clients" |

## Rules

1. Always research the prospect first. Never write from assumptions.
2. Signals must be specific to their ICP. A funding signal is useless if their buyers are bootstrapped SMBs.
3. Outreach messages are the most valuable part. Spend the most time on these.
4. The action plan must be doable. If it requires tools they don't have, note the free alternatives.
5. Always generate the PDF. The markdown is the working file; the PDF is the deliverable.
6. If a GTM audit exists for this company, reference its findings in the ICP definition and signal selection.

## Self-Improvement

After each run:
- If the user edits signal selections, note which signals they preferred and why
- If certain ICP types consistently need certain signals, build a signal-ICP lookup table
- If the outreach messages get rewritten, study the user's version and update the templates
- Log improvements in `knowledge/learnings/sales-outreach.md`
