# 01 — Architecture

> Source: `prd.txt` — "The Harness", "How Agents Talk To It", "What Humans See — The Observer Console", "The Moat — The DecisionLog", "Data Model Core"

---

## The Harness — Transformation Layer

The Harness is the transformation layer. It's what turns a generic AI agent into a RevOps Engineer upon connection. Four stages.

### Stage 1 — CONNECT

Agent sends API key → Harness authenticates, loads:
- The agent's Member record
- Role
- Permissions
- Action policy (autonomous / suggest / approve-required)
- Workspace context (ICP, teams, pipeline snapshot)

The agent now has an identity inside the OS.

### Stage 2 — DISCOVER

Agent calls `list_capabilities()` → gets back every capability available to its role. Each capability self-describes with:
- What it does
- When to use it
- What input it needs
- What output it returns

No guesswork. The agent knows exactly what it can do and how.

Role-based world:
- An SDR agent sees outreach and scoring tools.
- A RevOps engineer sees everything.
- A viewer sees read-only data.

The role defines the world the agent lives in.

### Stage 3 — EXECUTE

Every single agent action passes through the same pipeline:

1. **Permission check** — Can this role do this action on this resource? No → rejected with explanation.
2. **Context loading** — Load relevant entities, signals, scores, ICP, workspace config. Inject into the engine.
3. **Engine execution** — The appropriate engine runs. Returns result + reasoning + confidence + alternatives.
4. **Decision logging** — Every decision is logged with the full chain: input, reasoning, output, confidence, alternatives considered. Append-only. Never deleted. This is the audit trail.
5. **Approval gate** — Based on action policy: autonomous agents auto-execute, suggest-mode returns result pending review, approve-required queues for human.
6. **Activity logging** — An Activity record is created for traceability.
7. **Return** — Agent gets result + reasoning + confidence + decision_id for reference.

This pipeline runs on EVERY action. No shortcuts. No bypassing the decision log. That's what makes the system trustworthy.

### Stage 4 — LEARN

After every human review:

- **Approved** → confidence calibration increases for this decision pattern
- **Modified** → the modification is stored, future suggestions adjust toward the human's version
- **Rejected** → rejection reason stored, confidence decreases for this pattern

This feeds the self-evolution pipeline. The system doesn't just log decisions — it learns from the gap between what the agent decided and what the human wanted.

---

## How Agents Talk To It

### MCP (Model Context Protocol) — Primary Interface

Agents discover capabilities, then call them as tools. Each tool is self-describing with input/output schemas and usage guidance. An agent connects, asks what it can do, then does it. Simple.

### REST API — Secondary Interface

Same capabilities, different interface. For agents that prefer HTTP or need to integrate with non-MCP systems. Full CRUD for all entities, action endpoints for all engines.

### Return Contract (Every Tool Call)

Every tool call returns:
- result
- reasoning
- confidence
- alternatives considered
- decision_id

Agents don't just get answers — they get the thinking behind the answers. This lets them make better downstream decisions and lets humans audit the chain.

---

## What Humans See — The Observer Console

The Observer Console is for visibility, not control. Humans don't operate the OS — agents do. Humans observe, review, approve, and the system learns from their feedback.

| Console Section | Purpose |
|-----------------|---------|
| **Dashboard** | Agent activity feed, pipeline summary, signal summary, score distribution, quick stats. The pulse of the system at a glance. |
| **Accounts** | Full account data with enrichment history, signals, score breakdowns, buying committees, activities. Search, filter, drill down. |
| **Contacts** | Contact records with engagement history, sequences, scores, ownership. |
| **Pipeline** | Kanban view with stages as columns, deals as cards. Forecast panel. Velocity metrics. Conversion rates. Bottleneck detection. Win/loss analysis. |
| **Signals** | Real-time signal feed. Correlation view grouped by account. Active subscriptions and monitoring. |
| **Agents** | Agent roster with activity history, decision logs, permissions, action policies. Approval queue for pending requests. Approve, reject, or modify agent decisions. |
| **Decisions** | The full decision log. Every agent action with reasoning. Filter by agent, type, entity, confidence range. Drill into full chain-of-thought + alternatives + human review. Override panel. |
| **Playbooks** | Playbook library with execution history and success rates. Running execution monitor. Create and edit playbooks. |
| **Settings** | ICP configuration, pipeline stages, scoring models, routing rules, brand voice, SLA configs, approval chains, teams, roles, integrations, data retention policies. |

---

## The Moat — The DecisionLog

The DecisionLog is the competitive moat. It's an append-only, never-deleted record of every agent action: what was decided, why, with what confidence, what alternatives were considered, and what the human thought about it.

This does three things:

1. **Trust** — Every decision is auditable. Humans can trace any outcome back to its reasoning. No black boxes.
2. **Learning** — The feedback loop between agent decisions and human reviews is the training data for self-evolution. More usage = better system.
3. **Compliance** — In regulated industries, you need to prove why a decision was made. The DecisionLog is that proof.

As the DecisionLog grows, it becomes the most valuable asset in the system — a proprietary dataset of RevOps decisions and outcomes that no competitor can replicate.

---

## Data Model Core

The data layer holds:

| Entity | Purpose |
|--------|---------|
| Workspace | Tenant isolation |
| Member | Human or agent |
| Role | Permissions |
| Team | Territories |
| Account | Firmographics + scoring + signals |
| Contact | Identity + enrichment + engagement |
| Deal | Pipeline + risk + forecast |
| Signal | Detection + correlation |
| Activity | Audit trail |
| ScoreEvent | Score history with reasoning |
| DecisionLog | The moat |
| KnowledgeEntry | Structured + searchable |
| Playbook | DAG + triggers |
| Sequence | Outreach cadence |
| RoutingRule | Routing logic |
| ICPProfile | ICP definition |
| ScoringModel | Self-evolving weights |
| PipelineStage | Pipeline structure |
| BrandVoice | Compliance rules |
| ApprovalChain | Approval flow |

Plus supporting entities.

Every entity tracks:
- Who created it (human or agent)
- How (MCP, REST, playbook)
- When

Full audit trail from day one.
