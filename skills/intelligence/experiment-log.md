---
name: bi-experiment-log
description: >
  Track A/B tests and experiments across outreach, content, and pipeline.
  Log hypotheses, results, and conclusions. Auto-promotes to knowledge/patterns/
  after 3+ confirmations. Triggers on: "log experiment", "experiment result",
  "a/b test result", "what experiments", "experiment log", or /bi-experiment-log.
---

# Experiment Log

## Goal

Track every experiment [Company] runs — subject line A/B tests, content format tests, outreach timing tests, CTA variations — in a structured format. When an experiment produces 3+ consistent results, automatically extract it as a proven pattern in `knowledge/patterns/`.

## Required Context

Load before executing:

1. `departments/business-intelligence/references/metrics-definitions.md` -- KPI definitions
2. `knowledge/patterns/outreach-patterns.md` -- Existing proven patterns (avoid duplicates)
3. `knowledge/patterns/content-patterns.md` -- Existing content patterns

## Experiment Lifecycle

```
HYPOTHESIS → DESIGN → RUN → MEASURE → CONCLUDE → (PROMOTE or DISCARD)
```

### Logging a New Experiment

When the user says "log experiment" or reports an A/B test result:

1. Assign an experiment ID: `EXP-[DEPT]-[NNN]` (e.g., EXP-SO-001, EXP-CM-001)
2. Capture the structured entry (see format below)
3. Append to `departments/business-intelligence/outputs/experiment-log.md`
4. Check if this confirms or contradicts an existing pattern

### Experiment Entry Format

```markdown
## EXP-[DEPT]-[NNN]: [Short Title]

**Date:** [YYYY-MM-DD]
**Department:** [cm / so / ri / pe / fo]
**Category:** [subject-line / email-copy / content-format / timing / cta / channel / segment / other]
**Status:** [running / concluded / promoted / discarded]

### Hypothesis
[What we believed would happen and why]

### Design
- **Control (A):** [what was tested as baseline]
- **Variant (B):** [what was tested as alternative]
- **Metric:** [primary metric to measure — e.g., reply rate, click rate, engagement]
- **Sample size:** [how many in each group]
- **Duration:** [how long the test ran]

### Results
| Variant | Sample | Metric | Result |
|---------|--------|--------|--------|
| A (control) | [n] | [metric] | [value] |
| B (variant) | [n] | [metric] | [value] |

**Winner:** [A / B / No significant difference]
**Confidence:** [High (n>50, >20% difference) / Medium (n>20, >10% difference) / Low (n<20 or <10% difference)]

### Conclusion
[One sentence: what we learned]

### Related Patterns
- Confirms: [pattern ID, if any]
- Contradicts: [pattern ID, if any]
- New signal: [if this suggests a new pattern]
```

## Auto-Promotion Protocol

After logging an experiment result, check:

1. **Count confirmations** -- How many experiments support this same conclusion?
2. **Check confidence** -- Are the confirmations high or medium confidence?
3. **Check for contradictions** -- Does any experiment contradict this conclusion?

### Promotion Rules

| Confirmations | Confidence | Contradictions | Action |
|---------------|-----------|----------------|--------|
| 3+ | All High or Medium | 0 | **PROMOTE** to knowledge/patterns/ |
| 3+ | Mixed (some Low) | 0 | Flag for review, don't auto-promote |
| 3+ | Any | 1+ | **DO NOT PROMOTE** — conflicting evidence |
| 2 | Any | 0 | Note as "emerging pattern" — needs 1 more confirmation |
| 1 | Any | 0 | Just log it — too early to conclude |

### How to Promote

When promoting, create or update the appropriate pattern file:

1. Determine department: `knowledge/patterns/outreach-patterns.md` or `content-patterns.md`
2. Assign next pattern ID (e.g., P009)
3. Write the pattern in the existing format:
   ```
   ## P[NNN] — [Pattern Name]
   **Evidence:** EXP-[IDs] (N experiments, N total samples)
   **Finding:** [One sentence]
   **Implication:** [What to do with this knowledge]
   ```
4. Update the experiment entries to `Status: promoted` with link to pattern ID

## Querying the Log

When the user asks "what experiments are running" or "experiment status":

1. Read `departments/business-intelligence/outputs/experiment-log.md`
2. Summarise:
   - Running: [count] experiments
   - Concluded (awaiting promotion): [count]
   - Promoted to patterns: [count]
   - Discarded: [count]
3. For running experiments, show:
   - ID, title, how long it's been running, current sample size
   - Whether it's approaching statistical significance

## Seeding from Existing Data

On first run, seed the experiment log with known results from existing [Company] data:

- C002 segment A/B results (consulting vs agency vs recruitment reply rates)
- C002 subject line A/B results (if variant data available from SmartLead)
- Content format performance (LinkedIn post vs article engagement)
- DM vs Email channel comparison

These get logged as `Status: concluded` experiments with real data.

## Quality Gates

- [ ] Every experiment has a clear hypothesis (not just "let's try X")
- [ ] Sample size is recorded (results without sample size are anecdotes, not experiments)
- [ ] Confidence level is honest (small samples = low confidence, period)
- [ ] Promotion only happens at 3+ confirmations with no contradictions
- [ ] Contradicting evidence is never hidden — it's surfaced and investigated

## Rules

1. An experiment without a hypothesis is just random testing. Always state what you expect and why.
2. Small sample results are signals, not conclusions. Log them but don't promote them.
3. Never cherry-pick. If 2 experiments confirm and 1 contradicts, the pattern is unproven.
4. The goal is truth, not confirmation. A disproven hypothesis is as valuable as a proven one.
5. Every promoted pattern must have a clear "what to do with this" implication — abstract knowledge without action is trivia.
6. When an experiment contradicts a promoted pattern, flag it immediately and investigate. Patterns can be demoted.
