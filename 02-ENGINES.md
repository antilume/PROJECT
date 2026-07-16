# 02 — Engines

> Source: `prd.txt` — "Engines"

The intelligence layer. Each engine is a domain expert that takes input, applies reasoning, and returns structured output with explanation. No black boxes.

---

## ScoringEngine

Scores entities against ICP with ML weights + LLM reasoning. Every score comes with a full factor breakdown — which criteria matched, which didn't, how much each factor contributed. SHAP-style explainability. Scores aren't just numbers; they're arguments an agent can reason about and a human can audit.

**Score targets:**
- Leads
- Accounts
- Deal risk
- Customer health
- ICP fit

Each score type has its own model weights and thresholds. The weights self-evolve based on human feedback over time.

---

## SignalEngine

Monitors the web for buying signals. Detects:
- Intent
- Funding events
- Hiring spikes
- Job changes
- Usage patterns
- Churn indicators
- News events
- Product launches
- Partnerships
- Expansion signals

Each signal gets: type, intensity, summary, freshness, expiration.

**Correlation is the real power** — grouping related signals into clusters (funding + hiring = growth signal cluster) and computing a composite score with an interpretation an agent can act on. Example: "3 high-intent signals in 14 days, composite score 87 — recommend immediate outreach."

---

## EnrichmentEngine

Takes a domain or email → does web research → extracts structured firmographics/demographics using NLP → returns enriched entity with field-level confidence. Every field has a confidence score so agents know what to trust. Data lineage is tracked — where did each field value come from.

**Capabilities:**
- Waterfall enrichment — tries multiple sources in sequence
- Company hierarchy detection — maps parent/subsidiary relationships
- Buying committee mapping — identifies decision-makers, influencers, champions
- Technographics detection — reveals what tools a company uses

---

## RoutingEngine

Assigns leads to the right person/team.

**Supported modes:**
- Round-robin
- Territory-based
- ICP-weighted
- Skill-based

Every assignment comes with reasoning. Example: "Assigned to Sarah because: territory match (US-West), ICP score 92, she has 73% close rate with similar accounts."

**Additional behavior:**
- Routing rules configurable per workspace
- Lead-to-account matching auto-links new contacts to existing accounts
- SLA timers trigger escalations when leads sit too long

---

## OutreachEngine

Drafts personalized:
- Emails
- LinkedIn messages
- Call scripts
- Proposals

Uses LLM with full context: contact details, account signals, ICP match, previous interactions, pipeline stage. Every draft includes reasoning for why this approach was chosen.

**Brand compliance baked in:** Before any outreach goes out, the compliance engine checks against brand voice rules, prohibited phrases, tone guidelines. Returns a compliance score with specific flags and suggestions. A/B variant generation creates alternative versions for testing.

**Multi-step sequences** automate the full outreach cadence: first email, follow-up, break-up email, LinkedIn touch, call attempt — all sequenced with timing and conditions.

---

## PipelineEngine

Aggregates all deal data into pipeline views.

**Outputs:**
- Stage distribution
- Health metrics
- Velocity
- Aging
- Stuck deals
- At-risk deals
- Funnel analysis — conversion rates between stages, identifies bottlenecks
- Win/loss analysis — reveals why deals close or don't

**Next-best-action recommendations** tell agents what to do with each deal right now. Example: "Schedule executive meeting — deal has been in negotiation 12 days beyond average, champion engagement dropped."

---

## ForecastEngine

Revenue forecasting using ML models (LightGBM/XGBoost) plus weighted pipeline methods. Every forecast includes:
- Confidence intervals
- Key assumptions
- Risk factors

Not just a number — a defensible prediction with reasoning.

**AI-assisted forecasting considers:**
- Historical patterns
- Deal velocity
- Seasonal trends
- Current pipeline health

**Scenarios:** Commit vs. best-case vs. upside.

---

## KnowledgeEngine

The RevOps brain. Does NOT flood agent context windows with documents.

**Interface:**
- `search_knowledge(query)`
- `ask_revops(question)`

**GraphRAG execution:**
1. Vector search finds semantically relevant entries
2. Graph traversal follows concept relationships for multi-hop reasoning
3. LLM synthesis generates a compressed structured answer

The response is actionable and concise — always includes applicable playbooks, relevant tools, and data needed.

**Per-agent knowledge views:** Different agent roles see different knowledge slices.
- An SDR agent gets outreach tactics and scoring basics.
- A RevOps engineer gets the full depth.

No context pollution.

**Knowledge base covers:**
- Concepts
- Scoring methods
- Routing strategies
- Outreach tactics
- Forecast methods
- Signal guides
- Best practices
- Playbook templates

All structured and machine-readable.

---

## PlaybookEngine

Multi-step automation as DAGs — directed acyclic graphs. Not linear chains. Steps have dependencies, conditions, and branches.

**Example inbound lead playbook:** enrich → score → route → draft outreach → check compliance → auto-send or queue for approval. Each step's output feeds into the next.

**Triggers:**
- Events (new lead, signal detected, deal stage change)
- Scheduled (daily forecast review)
- Called directly by an agent

Execution is logged step by step. Success rates are tracked. Failed playbook steps trigger alerts.

**Approval gates** can be inserted at any step — pause execution, create an approval request, wait for human, then continue or branch based on the decision.

---

## HealthEngine

Customer health scoring with churn prediction.

**Monitors:**
- Engagement trends
- Support ticket patterns
- Usage signals
- Expansion indicators

Health scores come with reasoning. Example: "Churn risk elevated: login frequency down 40%, 2 support tickets this week, no expansion signals in 90 days."

**Lifecycle automation:**
- Tracks renewal timelines
- Triggers automated playbooks for at-risk accounts
- Detects expansion opportunities (usage increase, new department interest, additional licenses)

---

## ComplianceEngine

Brand voice enforcement across all generated content.

**Rule domains:**
- Tone
- Prohibited phrases
- Required disclaimers
- Industry-specific regulations

Every piece of outreach gets a compliance score before it's sent. The engine flags issues and suggests corrections.
