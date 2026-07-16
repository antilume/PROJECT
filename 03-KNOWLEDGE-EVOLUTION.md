# 03 — Knowledge System & Self-Evolution

> Source: `prd.txt` — "Knowledge System — The Retrieval Problem", "Self-Evolution — The OS That Gets Smarter"

---

## Part A — Knowledge System: The Retrieval Problem

Most knowledge systems dump documents into context windows. That's catastrophic for agents — it floods their working memory, wastes tokens, and degrades reasoning.

AxiomAX solves this differently:

### Principle 1 — Knowledge is a tool, not context

Agents don't receive knowledge passively. They actively query it when needed.

- `search_knowledge(query)` returns structured, compressed answers — not raw documents.
- `ask_revops(question)` returns expert guidance with reasoning and references.

### Principle 2 — GraphRAG architecture

1. Vector search finds relevant entries by semantic similarity.
2. Graph traversal follows relationships between concepts (e.g., "lead scoring" → "ICP fit" → "scoring model" → "weights").
3. LLM synthesis compresses everything into one actionable response.

Multi-hop reasoning without multi-page context.

### Principle 3 — Per-agent knowledge views

Different roles see different slices.
- An SDR agent doesn't need to see forecast methodology details.
- A RevOps engineer doesn't need cold email templates in their default view.

Role-based knowledge scoping prevents context pollution.

### Principle 4 — Evolutionary

- Knowledge entries that are frequently used in approved decisions get promoted to "validated" status.
- Entries associated with rejected decisions get flagged for review.
- The knowledge base improves itself.

---

## Part B — Self-Evolution: The OS That Gets Smarter

Every decision an agent makes gets logged with: input, reasoning, output, confidence, alternatives considered. When humans review those decisions, the feedback becomes training signal.

### Mechanism 1 — Scoring weight adjustment

When humans consistently modify scores for a certain factor, the system adjusts that factor's weight. If ICP fit is always overridden, it's weighted differently. The scoring model converges toward human judgment over time.

### Mechanism 2 — Playbook optimization

Playbook success rates are tracked. Steps that frequently fail get flagged. Execution patterns that lead to approvals get reinforced. Playbooks evolve toward what works.

### Mechanism 3 — Confidence calibration

Platt scaling adjusts confidence scores so they reflect reality. If an agent says "90% confident" but humans only approve 60% of those decisions, the confidence gets calibrated downward. Over time, confidence becomes accurate — 0.8 confidence means roughly 80% approval rate.

### Mechanism 4 — Knowledge promotion

Knowledge entries used in approved decisions gain status. Entries in rejected decisions get reviewed. The knowledge base self-curates.

### Mechanism 5 — Hot reload

Updated models deploy without restart. The system improves continuously, no downtime.

---

## Why Self-Evolution Is The Differentiator

The self-evolution mechanism is what separates AxiomAX from a static tool. It's not just an OS — it's an OS that learns. Every interaction makes it slightly better. Over months of use, it becomes deeply calibrated to each workspace's specific patterns, ICP, and decision culture.

### What Agents Learn Over Time (specific improvements)

- Which ICP criteria actually predict closed-won — the scoring model learns from outcomes, not assumptions
- Which signals matter most for conversion — signal weight adjusts based on which signals precede wins
- Which outreach approaches work for which personas — the outreach engine learns from open/reply rates
- Which routing assignments lead to fastest closes — the routing engine learns from rep performance by account type
- Which playbook steps fail most — playbook success rates identify weak steps
- When to trust the model vs. flag for human review — confidence calibration learns the boundary
- What knowledge agents actually need — knowledge gaps are identified from failed queries
- How each workspace makes decisions — the system calibrates to each org's culture and preferences
- Which competitive responses win — win/loss analysis feeds back into playbook strategies
- Seasonal patterns in pipeline and close rates — forecast models learn cyclical patterns

Every week of usage makes the system marginally better. After months, it's deeply calibrated to the specific organization. That's the compound value.
