![The GTM Playbook](banner.png)

# The GTM Playbook

**18 Claude Code skills. 7 proven patterns. The full campaign framework.**

Built from live outreach campaigns to B2B service companies. Not theory — every skill, every pattern, every framework came from real sends, real replies, and real audits.

I built this system on the side of a full-time job because I couldn't afford to hire an agency. Now I'm giving it away.

---

## What's Inside

### Skills (18 installable Claude Code skills)

Drop these into your `.claude/skills/` directory and they work immediately.

**Sales & GTM Auditing**
| Skill | What it does |
|-------|-------------|
| `gtm-audit` | Full 5-dimension audit. Scores any B2B company out of 100. |
| `gtm-icp` | ICP clarity analysis. Who are they targeting and how well? |
| `gtm-messaging` | Value prop, differentiation, headline clarity, CTA effectiveness. |
| `gtm-channels` | Channel mix audit. LinkedIn, blog, email, paid, partnerships. |
| `gtm-content` | Content-market fit. Does their content map to buyer pain points? |
| `gtm-signals` | Hiring, funding, tech stack, and competitive signals. |
| `gtm-report-pdf` | Generates branded PDF from any audit. Client-ready. |
| `signal-stack-blueprint` | Personalised signal detection plan for any prospect. |

**Content & Copywriting**
| Skill | What it does |
|-------|-------------|
| `expert-copywriter` | Copy strategy briefs. ICP psychology, narrative patterns, CTA alignment. |
| `copywriter` | Scores and optimises hooks, titles, subject lines, CTAs. |
| `blog-writer` | SEO + AEO optimised blog posts with schema markup. |
| `linkedin-creator` | LinkedIn posts and carousels. Multiple formats. |
| `newsletter-creator` | Newsletter issues with research, structure, and CTAs. |
| `youtube-scriptwriter` | Talk-track scripts with timestamps and diagram instructions. |

**Research & Intelligence**
| Skill | What it does |
|-------|-------------|
| `icp-research-agent` | Scans communities for what your ICP is talking about. |
| `linkedin-signal` | Scans a LinkedIn profile/company for buying signals and scores outreach readiness. |

**Business Intelligence**
| Skill | What it does |
|-------|-------------|
| `pipeline-forecast` | Projects audits, conversations, and revenue from real conversion rates. |
| `experiment-log` | Tracks A/B tests. Auto-promotes to proven patterns after 3+ confirmations. |

### Frameworks

The strategic thinking underneath the skills.

| Framework | What it is |
|-----------|-----------|
| `icp-psychology.md` | Fear hierarchy, desire hierarchy, internal monologue, language map, objection archaeology. Segment-specific psychology for agencies, consultancies, recruitment, IT services. |
| `signal-funnel.md` | 3-lane routing: Authority (LinkedIn), Outreach (email/DM), Nurture (newsletter). CTA rules per lane. |
| `voice-guide.md` | Tone calibration, banned words (33), preferred lexicon, writing rules. |
| `outreach-patterns.md` | 7 confirmed patterns from live campaigns with the data behind each one. |

### Playbooks

Step-by-step processes.

| Playbook | What it covers |
|----------|---------------|
| `campaign-playbook.md` | The 7-phase cold outreach process. Design, source, classify, enrich, setup, launch, scale, close. |
| `smartlead-pre-publish.md` | Pre-launch checklist for SmartLead campaigns. Catches the mistakes that kill deliverability. |

---

## The 7 Proven Patterns

These aren't best practices from a blog post. Each one is confirmed across 3+ data points from live campaigns.

| # | Pattern | What it means |
|---|---------|--------------|
| P001 | **Trust Bridge** | The free audit converts at 85% once someone replies. Audit first, sell second. Always. |
| P002 | **Hidden Differentiator** | Every company has a buried proof point. Finding it builds instant trust. |
| P003 | **Score Hook** | "Scored [Company] out of 100" as a subject line. 6.7% reply rate. |
| P004 | **2-Hour Window** | Most conversions happen within 2 hours of reply. Speed beats perfection. |
| P005 | **JS Rendering Gap** | JavaScript-rendered sites score near zero on technical SEO. Instant audit finding. |
| P006 | **Service Menu Overload** | Too many services listed. Fix: 3 pillars, 3 pages, 3 entry points. |
| P007 | **Signal Over Volume** | 300 signal-qualified leads beat 900 cold ones. Timing is everything. |

---

## How the Skills Chain Together

This is the part that matters. The skills aren't standalone — they compound.

```
ICP Research → Signal Detection → Lead Scoring → Outreach Sequencing
                                                        ↓
                                              Reply → GTM Audit
                                                        ↓
                                              Audit PDF → Follow-up
                                                        ↓
                                              Pipeline Forecast → Weekly Report
```

Your ICP research feeds your signal scanner. Your signals feed your lead scorer. Your scores feed your outreach sequences. Your outreach results feed your weekly report. The whole system compounds.

---

## Installation

### 1. Clone the repo

```bash
git clone https://github.com/[your-username]/gtm-playbook.git
```

### 2. Copy skills to your Claude Code project

```bash
cp -r gtm-playbook/skills/* your-project/.claude/skills/
```

### 3. Copy frameworks to your knowledge base

```bash
cp -r gtm-playbook/frameworks/* your-project/knowledge/
```

### 4. Start using

Open Claude Code in your project directory. The skills are now available as slash commands:

```
/gtm-audit          → Audit any company
/linkedin-signal    → Scan for buying signals
/expert-copywriter  → Get a copy strategy brief
/pipeline-forecast  → Project your pipeline
```

---

## Customisation

Every skill references knowledge files (ICP psychology, voice guide, signal funnel) that you should customise for your business:

1. **Edit `icp-psychology.md`** — Replace the fear/desire hierarchy with your ICP's actual psychology
2. **Edit `voice-guide.md`** — Set your tone, banned words, and preferred language
3. **Edit `signal-funnel.md`** — Map your own channels and CTA rules per lane
4. **Edit `outreach-patterns.md`** — Add your own proven patterns as you collect data

The skills read these files at runtime. Change the frameworks, and every skill adapts.

---

## Who This Is For

B2B service company founders (agencies, consultancies, recruitment firms, IT services) who:

- Need a GTM system but can't afford to hire one
- Want to run signal-led outreach instead of spray-and-pray
- Use Claude Code and want skills that actually do something
- Prefer evidence over theory

---

## Who Built This

I run go-to-market diagnostics for B2B service companies. I score them out of 100 across 5 dimensions and show them what to fix first.

I built this system because I couldn't afford the agency. Every skill came from a real problem I needed to solve. Every pattern came from a real campaign I ran.

The playbook is free because the audit is how I earn trust. If it helps you fix your GTM on your own — that's a win. If you want help — [get a free audit](https://partner.gtmsignalstudio.com/).

---

## Contributing

Found a bug? Have a pattern to add? Open an issue or PR.

If you're running these skills on your own campaigns and have data to share, I'd love to add your patterns to the collection. The more evidence, the stronger the playbook.

---

## License

MIT. Use it however you want. Attribution appreciated but not required.
