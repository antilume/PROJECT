# AxiomAX — What Agents Automate

**Every RevOps decision, process, and action that agents execute autonomously. Not about replacing tools — about automating work.**

---

## Revenue Decisions Agents Make

Every decision includes reasoning, confidence, and alternatives. Humans review where needed. System learns from feedback.

| Decision | What the Agent Decides | Triggers When |
|----------|----------------------|---------------|
| Lead qualification | Is this lead worth pursuing? Score + ICP fit + signals → yes/no + reasoning | New contact created, signals change |
| Lead priority | Which leads should we work first? Rank by score × signal intensity × ICP fit | Daily, or when new leads arrive |
| Lead routing | Who should own this lead? Territory + skill + capacity + ICP-weighted matching | New lead qualified, or re-routing needed |
| Account tiering | Is this account A/B/C/D? Composite of ICP fit + engagement + revenue potential + signals | Account enriched, quarterly review |
| Deal risk assessment | Is this deal at risk? Stage age + engagement drop + missing champion + competitor signals | Deal stage change, weekly review, signal detected |
| Deal next action | What should happen next with this deal? Analyze stage + health + history → specific action | Agent checks pipeline, or deal stalls |
| Forecast category | Commit, best case, upside, or pipeline? Deal analysis + historical patterns + confidence | Forecast cycle, deal changes |
| Discount approval | Should this discount be granted? Margin analysis + deal strategic value + policy check | Discount requested in deal |
| Outreach approach | What channel, tone, and message for this contact? Context + signals + stage + role + ICP | Agent decides to reach out |
| Churn intervention | Is this customer about to churn? Health score + usage drop + support signals → intervene or not | Health score drops, usage signals detected |
| Expansion opportunity | Should we pursue expansion? Usage growth + new department signals + license trends | Signal detected, quarterly review |
| Sequence enrollment | Should this contact enter a sequence? Which one? Lead stage + intent + ICP fit → sequence selection | Lead qualified, signal triggers |
| Signal actionability | Is this signal worth acting on? Intensity + freshness + correlation + account context → act/ignore/watch | Signal detected |
| Playbook selection | Which playbook applies here? Trigger match + account context + historical success rate | Event occurs, agent requests |
| Escalation trigger | Does this need human attention now? SLA breach + risk threshold + policy → escalate or handle | SLA timer fires, risk threshold crossed |
| Territory rebalance | Are territories balanced? Load analysis + opportunity distribution → rebalance recommendation | Monthly, or on team changes |
| Scoring model adjustment | Are our scores accurate? Approval rate analysis + outcome tracking → weight adjustments | Periodic self-evolution cycle |
| Renewal strategy | How do we retain this account? Health + usage + contract terms + champion status → strategy | Renewal window opens |
| Competitive displacement | Is a competitor threatening this deal? Competitor mentions + lost deals + market signals → counter strategy | Competitor signal detected |
| Budget allocation | Where should we invest SDR/AE time? Pipeline coverage + territory opportunity + close rates → allocation | Weekly planning, pipeline review |

## End-to-End Processes Agents Run

Not individual actions — full multi-step workflows that agents execute from start to finish.

### Inbound Lead Response
Lead arrives → enrich company + contact → score lead → check ICP fit → detect signals → route to right rep → draft personalized outreach → check brand compliance → auto-send or queue for approval → log everything. Agent handles the entire flow. Human only sees the result (or approves the outreach).

### Outbound Prospecting
Agent identifies target accounts (ICP match from discovery) → enrich each account → map buying committee → score each account → detect signals → prioritize by composite score → draft personalized sequences per contact → compliance check → enroll in sequences → monitor engagement → adjust approach based on response. Entire outbound motion automated.

### Pipeline Review
Agent scans all open deals → score deal risk for each → identify stalled deals → detect at-risk deals → calculate next-best-action for each → flag deals needing attention → generate pipeline health report → recommend forecast adjustments. What a RevOps manager spends hours on, the agent does continuously.

### Churn Prevention
Agent monitors all customer accounts → detect health score drops → identify churn signals (usage decrease, support spikes, champion departure) → score churn risk → trigger retention playbook → draft personalized retention outreach → propose remediation actions → escalate to CSM if high risk. Catches churn before it happens.

### Expansion Selling
Agent monitors customer accounts → detect expansion signals (usage growth, new department, additional licenses, product adoption) → score expansion potential → identify right contacts → draft expansion proposal → check pricing rules → propose timing and approach. Finds revenue that's sitting on the table.

### Deal Acceleration
Agent monitors deal progression → detect stalls (stage age beyond norm) → analyze why (missing champion? competitor? budget timing?) → recommend specific acceleration actions → draft exec outreach if needed → schedule follow-ups → propose discount if strategic. Moves stuck deals forward.

### Win/Loss Analysis
Agent tracks closed deals → analyze win patterns (what ICP traits, signals, actions correlate with wins) → analyze loss patterns (what went wrong, which competitors, which stages) → update scoring model weights → update ICP criteria → generate competitive intelligence → adjust playbook strategies. Every win and loss makes the system smarter.

### Onboarding Automation
New customer signed → agent creates onboarding plan → assigns implementation tasks → monitors progress → tracks milestone completion → detects delays → escalates if SLA at risk → triggers adoption playbooks → monitors health score from day one. No customer falls through the cracks.

### Renewal Management
Agent tracks contract dates → identifies upcoming renewals 90/60/30 days out → assesses account health → determines renewal risk → creates renewal strategy → drafts renewal communication → proposes pricing adjustments → coordinates with CS team → auto-escalates at-risk renewals. Never miss a renewal.

### Quarterly Business Review
Agent compiles QBR data → pipeline performance vs target → win/loss analysis → territory health → forecast accuracy review → scoring model performance → playbook success rates → recommendations for next quarter → generates QBR document. What takes a RevOps team a week, the agent does in minutes.

### Territory Planning
Agent analyzes territory distribution → deal load per rep → revenue per territory → coverage gaps → ICP concentration by geography → proposes territory rebalance → simulates impact → recommends team structure changes. Strategic territory optimization, not just round-robin.

### Competitive Intelligence
Agent monitors competitor mentions in lost deals → tracks competitor signals across accounts → identifies which competitors appear where → analyzes win rate against each competitor → recommends counter-positioning → updates playbooks with competitive responses. Real-time competitive awareness.

### Data Hygiene
Agent scans all records → detects incomplete fields → identifies stale data → finds duplicates → enriches where possible → flags what needs human input → updates data quality scores → maintains data lineage. The data stays clean without anyone thinking about it.

### Compliance Monitoring
Agent checks all outgoing communications → validates against brand voice rules → scans for prohibited phrases → ensures regulatory compliance (industry-specific) → flags violations → suggests corrections → logs compliance scores. Every message is brand-safe.

### Forecast Calibration
Agent tracks forecast accuracy over time → compares predictions to actuals → adjusts confidence intervals → identifies systematic biases (always over-forecast? under-forecast?) → recalibrates models → proposes forecast methodology changes. Forecasts get more accurate every cycle.

## Continuous Monitoring Agents Do

Background processes that never stop. Agents watch, detect, and act.

| What's Monitored | What Agent Does | When It Acts |
|-----------------|-----------------|-------------|
| New lead arrivals | Auto-enrich + score + route | Immediately |
| Signal changes on accounts | Re-score + re-prioritize + notify owner | On signal detection |
| Deal stage stagnation | Flag stalled deals + recommend actions | Daily scan |
| Health score drops | Trigger retention playbook | On threshold breach |
| SLA timers | Escalate breached SLAs | On timer expiry |
| Pipeline coverage gaps | Alert if coverage below threshold | Weekly check |
| Scoring model drift | Detect if approval rates diverge from confidence | Periodic analysis |
| Data freshness | Flag records not enriched in 90+ days | Weekly scan |
| Sequence performance | Identify underperforming sequences | Weekly analysis |
| Routing imbalance | Detect rep overload or underload | Daily check |
| Approval queue age | Escalate stale approval requests | On timer |
| Competitor activity | Monitor competitor signals across pipeline | Continuous |
| ICP fit changes | Re-evaluate accounts when ICP updates | On ICP change |
| Playbook success rates | Flag playbooks below threshold | Weekly analysis |
| Knowledge base gaps | Identify queries with no good answers | On failed knowledge search |
| Forecast vs actual | Track accuracy + recalibrate | Post-close analysis |

## Agent-to-Agent Handoffs

Multiple agents can collaborate through the OS. One agent's output becomes another's input.

```
SDR Agent: "I enriched and scored this lead. Score 87, high-intent signals. Routing to Sarah."
    ↓
AE Agent (Sarah's assistant): "New lead assigned. Drafting personalized outreach based on signals and ICP match."
    ↓
CS Agent: "Deal closed. Monitoring account health. Expansion signals detected at Day 45."
```

The OS coordinates. Agents don't need to talk to each other directly — they read and write to the same data layer, the same decision log, the same activity stream. One agent enriches, another scores, another routes, another drafts. Each does its specialty. The OS orchestrates the handoff.

## Reasoning Chains Agents Build

Every action generates a reasoning chain. These chains are composable and referenceable.

**Example — Lead Scoring Reasoning:**
```
Lead: john@techcorp.io
ICP Fit: 94/100 — SaaS, 200-500 employees, Series B, US-based. Matches 6/7 ICP criteria.
Signals: 3 high-intent signals in 14 days (pricing page visit, demo request, job posting for integration role)
Engagement: 4 web visits, 2 content downloads, 1 webinar attendance
Risk: No champion identified yet, early stage
Composite Score: 87/100 → Tier A
Confidence: 0.91
Recommendation: Prioritize outreach. Route to senior AE with SaaS expertise.
Alternatives considered: Tier B (if signals decay), Watch (if no engagement in 7 days)
```

**Example — Deal Risk Reasoning:**
```
Deal: TechCorp Enterprise — $120K, Negotiation stage
Risk Level: HIGH
Stage Age: 18 days (norm: 12 days) — 50% over expected
Champion Engagement: Dropped 60% in last 2 weeks
Competitor: CompetitorX mentioned in last call
Missing: Legal review not started, procurement contact unknown
Risk Factors: [stall, champion_disengaged, competitor_present, process_incomplete]
Recommended Actions: 1) Executive sponsor meeting this week, 2) Re-engage champion with new value prop, 3) Request procurement intro
Confidence: 0.85
```

These aren't black-box outputs. They're arguments. Humans can read them, audit them, agree or disagree with specific factors. The system learns from which factors humans emphasize or override.

## What Agents Learn Over Time

The self-evolution isn't abstract. These are the specific things that improve:

- **Which ICP criteria actually predict closed-won** — the scoring model learns from outcomes, not assumptions
- **Which signals matter most for conversion** — signal weight adjusts based on which signals precede wins
- **Which outreach approaches work for which personas** — the outreach engine learns from open/reply rates
- **Which routing assignments lead to fastest closes** — the routing engine learns from rep performance by account type
- **Which playbook steps fail most** — playbook success rates identify weak steps
- **When to trust the model vs. flag for human review** — confidence calibration learns the boundary
- **What knowledge agents actually need** — knowledge gaps are identified from failed queries
- **How each workspace makes decisions** — the system calibrates to each org's culture and preferences
- **Which competitive responses win** — win/loss analysis feeds back into playbook strategies
- **Seasonal patterns in pipeline and close rates** — forecast models learn cyclical patterns

Every week of usage makes the system marginally better. After months, it's deeply calibrated to the specific organization. That's the compound value.

## Orchestration Patterns

How agents sequence their work. These are the meta-patterns:

**Reactive** — Agent waits for events (new lead, signal, stage change) and responds. Most day-to-day work.

**Proactive** — Agent identifies opportunities without being triggered (daily scan for stalled deals, weekly data hygiene, monthly territory review). The agent doesn't wait for things to happen.

**Scheduled** — Recurring processes (forecast reviews, QBR prep, scoring model retraining, data freshness checks). Time-based automation.

**Cascading** — One action triggers a chain (signal detected → re-score → re-prioritize → draft outreach → enroll in sequence). Events cascade through the OS.

**Collaborative** — Multiple agents work on the same account/deal from different angles. SDR enriches, AE drafts, CS monitors. OS coordinates.

**Human-in-loop** — Agent does the work, human approves. Over time, as confidence builds, more actions move to autonomous. Trust is earned, not assumed.

---

*This file is about WHAT agents automate — the decisions, processes, and reasoning. For HOW the engines work, see `prd/AXIOMAX.md`. For data models and API details, see `prd/01-ARCHITECTURE.md` through `prd/06-JOB-POOL.md`.*
