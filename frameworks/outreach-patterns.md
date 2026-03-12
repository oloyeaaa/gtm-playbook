# Outreach Patterns

Proven patterns for sales and outreach. Extracted when 3+ similar learnings emerge.

---

<!-- Append new patterns below this line -->

## P001: The GTM Audit Trust Bridge (2026-03-10)

**Pattern:** Free GTM audit offered via cold email → reply "yes" → branded PDF delivered → Calendly link for walkthrough call.

**Evidence:** 5/5 replies from C002 campaign said yes to audit. All received branded PDFs within hours. Conversion from cold email to engaged prospect in one step.

**Why it works:**
1. Subject line creates curiosity ("Scored [Company] out of 100")
2. Audit proves competence without a pitch — the report IS the value
3. Low ask ("yes" is easier than "book a call")
4. PDF delivery is instant — momentum stays high
5. Calendly link in delivery email converts warm interest to call

**Template:** Cold email (score hook) → Reply "yes" → Audit + PDF (same day) → Short reply with 3 key findings + Calendly → Call → Proposal

**Rule:** Never pitch in the audit delivery email. Lead with their strongest hidden asset, explain the core problem, give 3 quick wins, then offer the walkthrough.

---

## P002: The Hidden Differentiator Pattern (2026-03-10)

**Pattern:** Every B2B company has at least one genuinely strong proof point that is invisible on their website.

**Evidence:** 5 out of 5 audits confirmed this:
- Techplus: 100% client retention, 6-8 week deployment (on Odoo directory, not website)
- Fire on the Hill: Siemens Gamesa, Amadeus, Alcatel Lucent (logos but no case studies)
- Honeycomb: 3,000+ newsletter subscribers, ex-Bain/McKinsey trainers (on Substack, not main site)
- Milk & Honey: strong PR client list (audit score 49/100)
- Transaction Focus: niche expertise (audit score 32/100)

**Implication for sales:** The audit's highest-value moment is telling the prospect what they already have but aren't showing. This creates trust ("he actually looked at my business") and urgency ("I need to fix this"). Lead every delivery email with their hidden strength.

**Implication for content:** This pattern is a repeatable content angle — "Your best differentiator is invisible" works as LinkedIn, blog, and newsletter content.

---

## P003: The Score Hook — Curiosity-Driven Subject Lines (2026-03-10)

**Pattern:** Subject lines that include a specific score ("Scored [Company] out of 100") outperform generic openers ("quick question") in data-oriented segments.

**Evidence:**
- C002-A (SaaS/Tech): "Scored out of 100" = 6.7% reply rate. "Quick question" = 0%. (30 sends each)
- C002-B (Agency): "Quick question" = 6.5%. "Go-to-market — honest take" = 3.4%. (Score hook not tested in this segment)
- C002-C (Consulting): Both variants tied at 6.7%. (30 sends each)

**Why it works:**
1. A number creates specific curiosity — "what's MY score?"
2. It implies you've already done work (invested effort = credibility)
3. It's personal — their company name + a score feels bespoke, not mass-blast
4. The number anchors the conversation — they reply to learn more, not to buy

**Rule:** Use the score hook for analytical ICPs (SaaS founders, consultants). Test "quick question" for relationship-first ICPs (agency founders). Never use both on the same person.

---

## P004: The 2-Hour Reply Window (2026-03-10)

**Pattern:** Most cold email replies arrive within 2 hours of delivery. Follow-up speed determines conversion.

**Evidence:**
- 6 of 9 replies (67%) arrived within 2 hours of send
- Average reply time: 2.3 hours across all segments
- Fastest: <1 minute (Kirsty, Charles, Mahesh — replied immediately)
- Slowest: 12 hours (Kaiyan — said "no", so slower reply = weaker intent signal)

**Implication for operations:** The audit delivery window is same-day, not next-day. When a reply comes in at 10am, the audit should be generated and sent back by 2pm. Waiting 48 hours kills momentum.

**Implication for tooling:** Built `smartlead.py check` to surface new replies with content and auto-triage. Run this 2-3x daily during active campaign periods. Future: auto-trigger audit generation on "audit_yes" triage.

**Rule:** Reply speed = close speed. Same-day audit delivery is non-negotiable.

---

## P005: The Invisible Website Pattern — Wix JS-Rendering (2026-03-10)

**Pattern:** B2B service companies built on Wix (JS-rendered) have their entire content invisible to search engines. This is the #1 technical GTM killer.

**Evidence:**
- 3 of 6 audited sites were Wix/JS-rendered (Techplus, Fire on the Hill, Dragonfish UK)
- WebFetch returns CSS/JS framework code, not page content — same experience for Googlebot
- These companies invest in case studies, service pages, and thought leadership that nobody can find organically
- Dragonfish: 65+ enterprise clients, Culture Consultancy of the Year — but a CHRO Googling "culture consultancy UK" won't find them

**Implication for audits:** Always check if a site is Wix/JS-rendered early. BUT — verify actual search performance before assigning severity (see P008). If the site ranks despite rendering issues, downgrade to Medium. If search traffic is genuinely impacted, flag as Critical.

**Implication for sales:** This finding is only a "wow" moment if it's actually hurting them. Telling a founder "Google can't read your site" when they're getting 200+ clicks/month makes YOU look lazy, not them look broken (L017 — Honeycomb).

**Rule:** JS-rendering is a technical limitation, not automatically a Critical finding. Always run `site:domain.com` and keyword searches to verify real-world impact before scoring severity.

---

## P006: The Service Menu Overload (2026-03-10)

**Pattern:** B2B service companies list every service they offer (8-14+) instead of leading with 3 clear pillars. This overwhelms buyers and dilutes positioning.

**Evidence:**
- Dragonfish: 14+ services listed (Research, Diagnostics, Transformation, Values, Strategy, Board Reviews, Leadership, Manager Toolkits, PX, Onboarding, Networks, Customer-Centricity, Brand Engagement...)
- Honeycomb: 8+ services
- Fire on the Hill: multiple overlapping service lines
- Pattern confirmed across 4 of 6 audits

**Why it happens:** Founders want to show capability breadth. They fear turning away business by being specific. The result is a services page that reads like a capabilities deck, not a conversion page.

**Fix (same every time):** Group services into 3 pillars. Each pillar gets one page, one clear entry point, and one case study. The buyer self-selects in under 10 seconds.

**Rule:** If a site lists 5+ services without clear grouping, flag it as High severity. Recommend the 3-pillar structure.

---

## P007: Signal > Volume — Hiring Intent as Outreach Trigger (2026-03-10)

**Pattern:** A company actively hiring for a sales/BD role has already decided they need outbound. This is the strongest cold outreach signal because the budget is already allocated (the salary).

**Evidence:**
- C002 (no signal, volume play): 5% reply rate from 180 sent
- C003 (funding signal): qualitatively better engagement on personalised emails
- C004 (hiring SDR/BDM signal): hypothesis — 8-12% reply rate expected. To be validated.
- Logic: a job posting for "Business Development Manager" proves (1) they've decided to invest in outbound, (2) they have budget, (3) they need infrastructure for the hire. Referencing their specific job posting makes the email feel relevant, not random.

**Detection:** LinkedIn Jobs, Indeed, Reed — search for SDR, BDM, Business Development Manager + [vertical] + UK. Filter: posted within last 14 days.

**Hook formula:** "You're hiring a [role] — what outbound infrastructure will they walk into on day one?"

**Rule:** Always reference the specific signal in Email 1. The signal is what makes it not-cold. Validate this pattern when C004 data comes in — if reply rate exceeds C002's 5%, the pattern is confirmed.

---

## P008: Verify Before You Claim — The Credibility Tax (2026-03-11)

**Pattern:** Every unverified claim in an audit costs more credibility than ten accurate findings earn. One wrong finding makes the prospect dismiss the entire report.

**Evidence:**
- Deri Hughes (Honeycomb, 56/100) called the audit "garbage" and "simply untrue" after receiving it. Specific trigger: the audit flagged Wix JS-rendering as a critical SEO problem. Deri's reality: 200+ Google clicks/month, ranking for key search terms. The technical finding was real but the business impact claim was false.
- His reply included the line: "if you haven't even visited our website to check if the outputs are right you're just wasting an opportunity to prove you can actually deliver value." He's right.

**Why it matters:**
1. Consultants fact-check your work. They will verify every claim.
2. One wrong finding poisons the well — they stop reading after they find the first error.
3. The audit's entire purpose is to build trust. A lazy finding destroys trust faster than no audit at all.

**Fix:** Added Phase 1.5 to the GTM audit skill — mandatory `site:domain.com` search + keyword ranking checks before scoring. Takes 30 seconds. Prevents the single most damaging audit error.

**Rule:** Never present a technical finding as a business problem without verifying the business impact. "Your site uses JS rendering" is an observation. "Google can't find you" is a claim that requires evidence.
