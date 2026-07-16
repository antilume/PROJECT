# 00 — AxiomAX Overview

> Source: `prd.txt` — "What It Is", "What It Is NOT", "The Loop", "What Gets Replaced"

---

## What It Is

**AxiomAX — The RevOps Operating System for AI Agents.**

A harness where any AI agent plugs in and becomes a RevOps engineer — every revenue operation built natively, no external tools needed.

Infrastructure. Not an app. Not an agent. Not middleware. Not a wrapper around existing tools.

An operating system that gives AI agents (Claude Code, Hermes, custom — anything that speaks MCP) the full capability stack of an entire revenue organization. Scoring, enrichment, signals, routing, outreach, pipeline management, forecasting, playbooks, knowledge — all built in, all native, all executable by agents through MCP or REST, and skills, plugins and more needed to act as the elite revenue engineer from day 0.

Design principle: **Agent Experience (AX)**. Clay was built for humans who then added AI features. AxiomAX is built FOR agents from day zero. The agent IS the user. The entire system is designed around what an agent needs to see, do, learn, and decide to execute revenue operations autonomously.

No human clicks through a dashboard to get work done. An agent calls a tool, the system executes, reasoning is captured, humans review where needed, the system evolves. That's the model.

---

## What It Is NOT

- A dashboard for humans to click around in
- An AI agent itself — it's the infrastructure agents connect TO
- Middleware connecting to HubSpot MCP or ZoomInfo MCP or any other MCP — it BUILDS those functions natively
- A wrapper around existing RevOps tools — it REPLACES them
- Just API primitives — it's end-to-end functional
- Just for one type of agent — any agent that speaks MCP can connect

---

## The Loop

```
Agent connects via MCP
      ↓
Discovers what it can do (every capability self-describes)
      ↓
Executes RevOps primitives (score, enrich, route, draft, forecast, automate...)
      ↓
Every decision logged with full reasoning chain + confidence + alternatives
      ↓
Humans review where needed → feedback loops back into the system
      ↓
System self-improves from every interaction
      ↓
Agent gets smarter, scores get sharper, playbooks get tighter, OS evolves
```

This loop IS the product. The connect → discover → execute → learn cycle is what transforms a generic AI agent into an experienced RevOps/GTM Engineer. That transformation is the core value.

---

## What Gets Replaced

Every category below is built natively. No dependencies. No "integration required." When an agent needs to enrich a contact, it doesn't call ZoomInfo — it calls AxiomAX's enrichment engine which does web research and NLP extraction directly. When it needs to forecast, it doesn't pull from Clari — it runs AxiomAX's forecast engine with ML models.

| Category | What Dies | What AxiomAX Builds Natively |
|----------|----------|------------------------------|
| CRM | HubSpot, Salesforce | Account/Contact/Deal data model + full CRUD + relations + audit trail |
| Data Enrichment | ZoomInfo, Clearbit, Apollo, Cognism, Lusha | Web research → structured extraction with field-level confidence scores |
| Enrichment Orchestration | Clay | Waterfall enrichment across multiple sources, merge logic, best-data-wins |
| Scoring & Intent | 6sense, HubSpot scoring | ML scoring with factor breakdown and human-readable reasoning per score |
| Intent Signals | 6sense, Bombora, Demandbase, Warmly | Web monitoring → signal detection → multi-signal correlation → composite scoring |
| Lead Routing | LeanData, Chili Piper, Default | Rule engine with territory/ICP-weighted/round-robin/skill-based + reasoning |
| Sales Engagement | Outreach, Salesloft | LLM drafting + brand compliance + multi-step sequences + variant generation |
| Revenue Intelligence | Gong | Decision reasoning chains + conversation intelligence patterns + audit trail |
| Forecasting | Clari, BoostUp | ML + weighted forecast methods with confidence intervals and assumptions |
| Customer Success | Gainsight, Totango | Health scoring + churn prediction + expansion detection + renewal automation |
| CPQ | DealHub | Pricing rules + discount approvals + quote generation |
| Analytics & BI | Looker, Tableau | Pipeline analytics + funnel analysis + win/loss + territory performance |
| Workflow Automation | n8n, Zapier | DAG playbook engine with conditions, branches, approval gates |
| Buying Committee | UserGems, Champion | Committee mapping + role detection + influence scoring |
| Brand Compliance | Writer, Grammarly Business | Brand voice rules + prohibited phrases + tone enforcement + compliance scoring |
| Knowledge Management | Guru, Notion (for RevOps) | GraphRAG knowledge engine — agents query it, it doesn't flood their context |
