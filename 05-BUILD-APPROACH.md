# 05 — Build Approach

> Source: `prd.txt` — "Build Approach", "OSS & ML Components"

---

## Part A — Build Order

Build the OS in layers. Each layer enables the next. Start with data and auth — nothing works without a foundation. Then CRUD and UI — you need to see what you're building. Then engines — the intelligence. Then orchestration — automation. Then the harness and MCP — agent access. Polish continuously.

### The Order That Works

```
Layer 1 — FOUNDATION
  schema, seed data, auth, app shell

Layer 2 — VISIBILITY
  CRUD APIs, UI tabs, basic interactivity

Layer 3 — INTELLIGENCE
  enrichment, scoring, signals engines

Layer 4 — REVENUE OPERATIONS
  routing, outreach, pipeline, forecast engines

Layer 5 — AUTOMATION
  playbooks, approval chains

Layer 6 — AGENT ACCESS
  harness, MCP server, polish
```

Ship. Break. Fix. Ship again. The OS evolves — and so does the build process.

---

## Part B — OSS & ML Components

Use whatever open-source components make sense. No NIH (Not Invented Here) syndrome. Some that fit:

| Purpose | Component | Notes |
|---------|-----------|-------|
| MCP — agent interface | `@modelcontextprotocol/sdk`, `mcp-framework` | Standard agent interface |
| ML Scoring | PyCaret, XGBoost, LightGBM, etc. | Scoring models that self-evolve |
| Explainability | SHAP | Every score has factor contributions |
| NLP | `compromise` | Text processing for enrichment and parsing |
| Web Scraping | `cheerio`, `puppeteer` | Data acquisition for enrichment and signals |
| Vector Search | Custom index on SQLite | No external vector DB needed for prototype |
| DAG Execution | Custom executor inspired by Temporal/n8n patterns | Simplified for RevOps |
| Graph Relationships | Adjacency list in SQLite | Concept graphs for knowledge |
| Confidence Calibration | Platt scaling + isotonic regression | scikit-learn patterns |

### Selection Principle

If a better OSS tool exists for a job, use it. The goal is the best working system, not building everything from scratch. But build the RevOps logic natively — that's the product.
