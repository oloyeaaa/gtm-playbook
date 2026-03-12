---
name: icp-research-agent
description: >
  Research what ICPs are talking about, asking, and struggling with across
  communities and forums. Produces structured topic bank with sources, dates,
  angles, and urgency ratings. Pushes to Airtable and feeds content agents.
  Use when: "research icps", "icp research", "find topics", "what are icps
  talking about", "topic research", "research agent", or /icp-research-agent.
---

# ICP Research Agent Launcher

## Goal

Run the ICP research pipeline to find data-driven content topics from real ICP conversations and push them to the topic bank.

## Required Context

Before executing, load these files:

1. `departments/research-intelligence/agents/icp-research/agent.md` — Agent scope and ICP segment definitions
2. `departments/research-intelligence/agents/icp-research/routine.md` — 7-step execution routine
3. `knowledge/voice-guide.md` — Voice standards (for angle suggestions)
4. `knowledge/signal-types.md` — Signal categorisation
5. `knowledge/self-learning-protocol.md` — Post-execution improvement rules

Reference (load only if needed):
- `departments/research-intelligence/agents/icp-research/tools/run_icp_research.py` — Research tool implementation
- `departments/research-intelligence/tools/perplexity_research.py` — Base Perplexity wrapper (for debugging)

## Execution

Follow the 7-step routine in `departments/research-intelligence/agents/icp-research/routine.md`:

1. **Validate** — Confirm ICP segment(s), research scope, num_topics
2. **Research** — Run Perplexity calls via run_icp_research.py
3. **Structure** — Parse and validate findings
4. **Human review** — Present findings, get approval
5. **Push to Airtable** — Write approved topics to ICP-Research-Topics table
6. **Feed content agents** — Update knowledge/topics/content-topics.md
7. **Log + Improve** — Record execution, note improvements

## Default Inputs

If the user doesn't specify:
- icp_segment: `all` (both agency-founder and agency-buyer)
- research_scope: `all` (pain-points, questions, trends, hiring)
- num_topics: `5` per angle

## Rules

1. Never fabricate sources or data points — use real findings or omit
2. Always present findings for human review before pushing to Airtable
3. Each finding must have: topic, question, source, date, signal_type, suggested_angle, urgency
4. Deposit top findings in content-topics.md so content agents can use them immediately
5. Log every execution — even failed ones
