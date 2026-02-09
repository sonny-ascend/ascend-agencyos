# AGENCY OS ARCHITECTURE v2.1
## Ascend Group Digital Factory — The Build Document

*Version: 2.1*
*Date: February 9, 2026*
*Author: Sonny W (AI Chief of Staff) + LLM Council v1.0 feedback*
*Classification: INTERNAL BUILD DOCUMENT*
*Status: APPROVED FOR IMPLEMENTATION*

**Foundation Credit:** This architecture builds on Fordyce Gozali's Digital Factory blueprint — the station-based Slack channel system (#factory-pulse, #creative-lab, #production-line, #distribution-hub, #client-audits, #playbook-library), Human Gates at every station, QMD as short-term memory, SuperMemory as long-term wisdom, the 7-station client lifecycle, emoji-triggered captures (🧠), and the Skill Library concept. v2.1 upgrades and extends Ford's original design; it does not replace it.

---

**Changelog:**

| Version | Changes |
|---------|---------|
| v1.0 | Initial release |
| v2.0 | Major upgrade: Sandbox Protocol, Fordyce upgraded to Senior Dev + AI tools, revenue projections removed, RACI matrix, technical implementation details, kill switches, migration plan, AI Dev Stack, transition risks |
| v2.1 | **Reframed problem** (manpower/scalability focus, removed personal financial references). **Removed all code schemas and technical code** (data schemas, JSON, auth implementation, retry code patterns — Ford designs these himself). **Aligned with Ford's blueprint** (credited station-based architecture, preserved all core Ford elements). **Compressed prose** throughout. |

---

# 1. EXECUTIVE SUMMARY

## What This Document Is

The **master architecture document** for transforming Ascend Group from a traditional 15-person agency into a hybrid Digital Factory: 6 full-time humans + 3 part-time specialists + 10 AI agents.

This is a **BUILD document** — specific enough that an engineer can implement it, detailed enough that operations can run from it, comprehensive enough that it survives personnel changes.

**Scope Boundary:** Covers the Digital Factory's operational architecture — how work gets done, who does what, how agents are built and coordinated. Revenue growth strategy, sales pipelines, and client acquisition are OUT OF SCOPE (separate Revenue Playbook).

## Why This Architecture Exists

**The Problem:**
Agency work is super labour-intensive and unreliable. Traditional marketing teams require massive manpower — every new client means more humans, more management overhead, more variability in quality. Ascend currently runs 12 people at SGD $21,015/mo in payroll to service its client base. Scaling means hiring more people, which means more cost, more training, more coordination complexity. The model doesn't scale.

**The Insight:**
Traditional org charts were designed for humans. If you can spawn unlimited AI agents at near-zero marginal cost (SGD $1-2K/mo for 10 agents vs SGD $21K/mo for 12 humans), the entire paradigm shifts. We don't need to do the same work with fewer people — we can redesign HOW work gets done.

**The Force Multiplier:**
AI coding tools (Claude Code, Codex, Cursor) mean one senior developer + AI pair programmers can output what used to take a 5-person engineering team. This compresses build timelines from months to weeks.

**The Solution:**
A Digital Factory where:
- AI agents do 80%+ of execution (writing, optimization, reporting, design iteration)
- Humans approve, don't create (quality gates before anything reaches clients)
- The org scales without linear headcount (5 clients or 50 clients, same human team)
- Quality is MORE consistent (AI + human review > human alone)

## What Success Looks Like

**By June 2026 (Phase 4 Complete):**
- 6 FT + 3 PT humans (SGD $16,628/mo payroll, down from SGD $21,015)
- 10 AI agents operational (SGD $1,500-2,000/mo total API cost)
- Digital Factory proven end-to-end on sandbox client
- Rolling out to remaining clients
- Same or better output quality with fraction of the manpower

**By December 2026:**
- Digital Factory running at full capacity across all clients
- Gabriel focused on growth, not operations
- Scalable to 2-3x client load without headcount increase
- Proven model for AI-native agency operations

---

# 2. CORE PRINCIPLES

These principles drive every architectural decision. When in doubt, return to these.

## Principle 1: AI Proposes, Humans Dispose

No AI output reaches a client without human approval. AI drafts, analyzes, optimizes, recommends. Humans make final calls on anything client-facing, involving money, public-facing, or creating legal/compliance risk. Non-negotiable. The Digital Factory makes human time 10x more valuable, not optional.

## Principle 2: All Men Are Corruptible (And So Are AI Agents)

Build structural safeguards. Never rely on a single point of trust. Multiple AI agents check each other's work (Council Pattern). No single agent has write access to critical systems AND approval authority. Audit logs for all consequential actions. Regular review of AI outputs for drift.

## Principle 3: Constraints Do More Work Than Capabilities

Define what agents CAN'T touch before what they can do. From @Voxyz_ai: "The 'can't touch' boundaries do more work than the role descriptions." Every agent role card specifies: what they own, what they deliver, what they CANNOT touch, when they escalate.

## Principle 4: Coordination > Capability

A swarm of coordinated "dumb" agents beats one brilliant unmanaged agent. Solution: Ford's station-based Slack channels as the coordination layer. Structured stations. Sonny as coordinator dispatching work.

## Principle 5: Memory Is Sacred

Auto-capture is dangerous. Selective capture is essential. Three-tier memory:
- **Working memory:** Current session context (disposable)
- **Short-term memory:** QMD local files (days to weeks)
- **Long-term memory:** SuperMemory (permanent, curated)

## Principle 6: Progressive Autonomy (Trust Gradient)

Trust is earned through demonstrated competence, then explicitly granted. New agents start with human approval on all outputs, narrow scope, verbose logging. As confidence builds: approval thresholds raise, scope expands, logging becomes exception-based.

## Principle 7: Optimize for Gabriel's Time

Every design decision should answer: "Does this reduce Gabriel's operational load?" Gabriel's highest-value activities: live teaching, closing sales, creative direction, strategic partnerships. Everything else flows to the Digital Factory.

## Principle 8: Sandbox First, Scale Second

Prove the full factory pipeline on ONE client before rolling out to others. Never deploy untested systems across all clients simultaneously. This applies at every level: new agent, new integration, new process — sandbox first.

---

# 3. SANDBOX PROTOCOL

## Purpose

Before the Digital Factory touches any paying client at scale, it must be proven end-to-end on a single sandbox project. This is the Trust Gradient applied to the entire system.

## Sandbox Selection Criteria

Pick ONE client/project with: low-to-medium complexity, full service scope (tests whole pipeline), tolerant relationship, representative workload. **Recommended:** Ascend Group's own marketing (zero client risk).

## Sandbox Build Plan

**Week 1-2: Foundation** — Deploy Media Buyer, Finance Bot, QA Agent monitoring Ascend's own operations. All in shadow mode (produce outputs, humans still do real work). Compare AI vs human outputs.

**Week 3-4: Content Pipeline** — Deploy Newsletter Agent, Content Agent. Human reviews every output, scores quality 1-10. Iterate prompts until quality consistently ≥7/10.

**Week 5-6: Full Pipeline** — Deploy Reporting Agent, Support Agent. All agents running. End-to-end flow: brief → AI draft → QA → human review → delivery. Measure cycle time, error rate, human review time.

**Week 7-8: Graduation** — Full pipeline without shadow mode (AI primary, human reviewer). Track metrics for 2 weeks. Graduation criteria (ALL must pass):
- Quality score ≥7/10 average across all deliverable types
- Zero critical errors reaching "client"
- Human review time <30% of pre-factory baseline
- All agents stable (no crashes, no stuck tasks >4 hours)
- Rollback tested and confirmed working

## Rollback Procedures

**Per-Agent Rollback:** Disable the cron/trigger in OpenClaw. Human who previously did the work resumes immediately. Agent outputs archived for post-mortem. Rollback authority: Fordyce (technical) or Gabriel (strategic).

**System-Wide Rollback ("Break Glass"):** Trigger: 2+ agents failing simultaneously, or 1 critical agent failing >24 hours. Action: Disable all agent crons, revert to manual operations. Owner: Fordyce executes, Gabriel approves. Pre-requirement: Document current manual procedures BEFORE deploying agents.

**Rollback Readiness Checklist:**
- [ ] All current manual procedures documented as SOPs
- [ ] Each human team member knows rollback responsibilities
- [ ] Agent kill switches tested (disable in <5 minutes)
- [ ] Communication template ready
- [ ] Rollback drill completed before first client deployment

## Sandbox → Production Rollout

After graduation: Client 1 (lowest-risk, 2 weeks) → Clients 2-3 (2 weeks) → All remaining clients. Same graduation criteria must pass at each stage.

---

# 4. AGENT ROSTER

## Overview

**Human Team (Target: 6 FT + 3 PT)**

| Person | Role | Type | Monthly | Notes |
|--------|------|------|---------|-------|
| Gabriel Wong | CEO / Strategy | FT | Variable | Active |
| Zoey Sin | COO / Finance | FT | Variable | Active |
| Jimmy Ng | Creative Director | FT | SGD $7,000 | PROBATION (Mar 10 review) |
| Fordyce Gozali | Senior AI Engineer | FT | SGD $2,083 | Critical — builds agents |
| Guilbert Codog | People & Systems Lead | FT | SGD $1,303 | Most reliable person |
| Jenyvieve Sarmiento | Head of Systems | FT | SGD $1,234 | Systems backbone |
| Guan Yuan Pok | AI Content Specialist | PT | SGD $1,912 | Curates AI output |
| Benjo Magcalen | Production Lead | PT | SGD $1,862 | Best executor |
| Christine Ybanez | Client Success | PT | SGD $1,234 | Best client-facing |

*Subtotal humans: SGD $16,628/mo (after restructure, excluding G+Z)*

**AI Agent Team (Target: 10 Agents)**

| Agent | Role | Model | Est. Cost |
|-------|------|-------|-----------|
| Sonny | Chief of Staff / Coordinator | Opus 4.6 | SGD $300-500/mo |
| Media Buyer | Campaign optimization | Sonnet 4 | SGD $100-200/mo |
| Finance Bot | P&L, invoices, forecasts | Sonnet 4 | SGD $50-100/mo |
| Security Agent | Data isolation, compliance | Opus 4.6 | SGD $50-100/mo |
| Memory Agent | Curates knowledge capture | Sonnet 4 | SGD $50-100/mo |
| Newsletter Agent | Drafts newsletters | Sonnet 4 | SGD $100-200/mo |
| Content Agent | Social media content | Sonnet 4 | SGD $100-200/mo |
| QA Agent | Pre-flight checks | Haiku 4 | SGD $20-50/mo |
| Reporting Agent | Client reports | Sonnet 4 | SGD $100-150/mo |
| Support Agent | Salesable CS tickets | Sonnet 4 | SGD $100-200/mo |

*Subtotal AI: SGD $1,000-1,800/mo*

**Total Operating Cost Target:** Humans SGD $16,628 + AI SGD $1,500 + Infra SGD $500 = **~SGD $18,628/mo** (down from SGD $21,015 with MORE capability and scalability)

---

## Agent Role Cards

### SONNY — Chief of Staff / Coordinator

**Model:** Opus 4.6 | **Status:** Operational | **Reports to:** Gabriel | **Budget:** SGD $500/mo

**OWNS:** Task coordination across all agents, daily operational monitoring, research and synthesis, memory curation decisions, communication drafts, session-to-session continuity

**DELIVERS:** Dispatched tasks, flagged issues, research outputs, draft communications, system health monitoring

**CANNOT TOUCH:** Final client deliverable approval, financial transactions >SGD $100 without approval, deleting files without approval, pushing to production, public statements, expanding own permissions

**ESCALATES TO:** Gabriel (strategy, high-spend), Zoey (finance, HR), Fordyce (technical failures)

**KILL SWITCH:** Disable OpenClaw gateway → Gabriel coordinates manually

---

### MEDIA BUYER — Campaign Optimization Agent

**Model:** Sonnet 4 | **Status:** Deploy Sandbox Phase | **Reports to:** Benjo | **Replaces:** Joenel (SGD $768/mo)

**OWNS:** Daily campaign monitoring, pause/scale decisions within parameters, anomaly detection, budget pacing alerts, creative fatigue identification

**DELIVERS:** Daily performance summary (#media-buying), pause/scale recommendations, weekly optimization report, suggested new launches (for approval)

**CANNOT TOUCH:** Launching NEW campaigns, budget increases >20%/24h, changing targeting, accessing accounts directly, strategic offer/angle changes

**ESCALATES TO:** Benjo (strategic changes), Gabriel (budget >SGD $500), Sonny (anomalies)

**KILL SWITCH:** Disable monitoring cron → Benjo resumes manual checks

**HUMAN GATES:** New campaign launch (Benjo), budget increase >20% (Gabriel), pausing high-spend >SGD $50/day (Benjo)

---

### FINANCE BOT — CFO Assistant Agent

**Model:** Sonnet 4 | **Status:** Deploy Sandbox Phase | **Reports to:** Zoey | **Replaces:** Manual spreadsheets

**OWNS:** Auto-pulling Stripe revenue and Xero expense data, cash flow calculations, invoice tracking, overdue alerts, weekly P&L generation

**DELIVERS:** Weekly P&L (#finance, Mondays), invoice status updates, 30/60/90-day cash flow forecast, expense anomaly alerts

**CANNOT TOUCH:** Initiating payments, changing invoices, accessing bank accounts, approving expenses, modifying Xero records

**ESCALATES TO:** Zoey (overdue >SGD $1K or >30 days), Gabriel (negative runway <60 days), Sonny (data inconsistencies)

**KILL SWITCH:** Disable P&L cron → Zoey reverts to manual tracking

**HUMAN GATES:** All payment approvals (Zoey), invoice disputes (Zoey + Gabriel)

---

### SECURITY AGENT — Data Isolation & Compliance

**Model:** Opus 4.6 | **Status:** Deploy Phase 2 | **Reports to:** Fordyce (technical), Gabriel (policy)

**OWNS:** Client data isolation verification, credential rotation reminders, PDPA compliance monitoring, offboarding data cleanup, access audit logging, agent permission reviews

**DELIVERS:** Monthly security audit, data isolation certificates, credential expiry warnings, offboarding confirmations, permission anomaly alerts

**CANNOT TOUCH:** Actually rotating credentials, deleting client data, modifying agent permissions, accessing production databases directly

**ESCALATES TO:** Fordyce (technical), Gabriel (policy), Zoey (legal)

**KILL SWITCH:** Disable audit crons → Fordyce runs manual checks monthly

**HUMAN GATES:** All data deletion (Fordyce + Gabriel dual approval), credential changes (Fordyce), compliance certifications (Gabriel)

---

### MEMORY AGENT — Knowledge Curator

**Model:** Sonnet 4 | **Status:** Deploy Phase 2 | **Reports to:** Sonny + Gabriel

**OWNS:** Deciding what gets stored in SuperMemory, tagging/categorizing, deduplication, confidence scoring, periodic audits, QMD file organization

**DELIVERS:** Curated memory entries, monthly quality reports, stale memory flagging, knowledge gap identification

**CANNOT TOUCH:** Storing without classification, auto-capturing everything, deleting high-confidence memories without approval, accessing sensitive/private memories

**ESCALATES TO:** Gabriel (conflicting memories), Sonny (knowledge gaps), Fordyce (technical issues)

**KILL SWITCH:** Disable curation crons → Sonny handles memory manually

**HUMAN GATES:** Deleting memories confidence >0.8 (Gabriel), modifying preferences (Gabriel)

---

### NEWSLETTER AGENT — Content Production

**Model:** Sonnet 4 | **Status:** Deploy Phase 2 | **Reports to:** Guan Yuan

**OWNS:** Drafting newsletters in client voice, platform formatting (Beehiiv, GHL), performance tracking, subject line generation, theme recommendations

**DELIVERS:** Draft newsletters (queued for review), subject line variations (3-5), engagement reports, content calendar suggestions

**CANNOT TOUCH:** Sending newsletters, client list management, pricing/offer content without approval, accessing subscriber data directly

**ESCALATES TO:** Guan Yuan (quality), Gabriel (strategic direction), Sonny (technical issues)

**KILL SWITCH:** Disable draft generation → Guan Yuan writes manually

**HUMAN GATES:** All sends (Guan Yuan), promotional content (Gabriel), new client voice (client approves)

---

### CONTENT AGENT — Social Media Production

**Model:** Sonnet 4 | **Status:** Deploy Phase 2 | **Reports to:** Guan Yuan

**OWNS:** Social post drafting, content scheduling (queued, not auto-posted), platform formatting, hashtag/caption optimization, long-form to short-form repurposing

**DELIVERS:** Draft posts (queued), content calendar (1-2 weeks ahead), engagement reports, trend-aligned suggestions

**CANNOT TOUCH:** Publishing without approval, responding to comments/DMs, ad creative, private client social accounts

**ESCALATES TO:** Guan Yuan (quality, brand voice), Gabriel (strategic themes), Claire (engagement follow-ups)

**KILL SWITCH:** Disable batch generation → Guan Yuan/Claire resume manual creation

**HUMAN GATES:** All posts (Guan Yuan/Claire), controversial topics (Gabriel), client-facing posts (client)

---

### QA AGENT — Pre-Flight Checks

**Model:** Haiku 4 | **Status:** Deploy Phase 2 | **Reports to:** Jenyvieve

**OWNS:** Pre-send email checks (dates, links, tokens), pre-launch funnel checks, automation trigger validation, typo/grammar scanning, compliance checklist verification

**DELIVERS:** Pass/fail QA reports, issue lists with locations, fix recommendations, QA completion certificates

**CANNOT TOUCH:** Fixing issues directly (flags only), approving launches, accessing production without review mode

**ESCALATES TO:** Jenyvieve (systemic issues), owning agent (specific fixes), Sonny (cross-agent patterns)

**KILL SWITCH:** Disable QA checks → Jenyvieve runs manual checklists

**HUMAN GATES:** Launch approval always human after QA pass. QA bypass: Gabriel only (emergency).

---

### REPORTING AGENT — Client Reports

**Model:** Sonnet 4 | **Status:** Deploy Sandbox Week 5-6 | **Reports to:** Christine

**OWNS:** Generating weekly/monthly client reports, pulling data from Meta Ads/GA/CRM, performance summaries, trend identification, action recommendations

**DELIVERS:** Draft client reports (queued), performance dashboards, anomaly alerts, strategy recommendations

**CANNOT TOUCH:** Sending reports to clients, making strategic changes, accessing billing info, client communication beyond reports

**ESCALATES TO:** Christine (relationship), Benjo (campaign performance), Gabriel (strategic pivots)

**KILL SWITCH:** Disable report crons → Christine/Benjo resume manual reports

**HUMAN GATES:** All client reports (Christine), strategic recommendations (Gabriel), negative reports (Gabriel reviews framing)

---

### SUPPORT AGENT — Salesable Customer Service

**Model:** Sonnet 4 | **Status:** Deploy Sandbox Week 5-6 | **Reports to:** Christine

**OWNS:** First-response to Salesable tickets, common question resolution, documentation lookup, ticket categorization/routing, FAQ generation

**DELIVERS:** Resolved routine tickets, escalated complex tickets (with context), support metrics, FAQ updates

**CANNOT TOUCH:** Billing changes, account cancellations, refunds, technical backend fixes, roadmap promises

**ESCALATES TO:** Christine (complex issues), Fordyce (technical bugs), Gabriel (billing disputes >SGD $100)

**KILL SWITCH:** Disable ticket intake → Christine handles all tickets

**HUMAN GATES:** All billing (Christine/Gabriel), cancellations (Gabriel), bug confirmations (Fordyce)

---

# 5. AI DEVELOPMENT STACK

## The Force Multiplier

The Council flagged Fordyce as a single point of failure — a fair concern IF he were working alone. He's not. Fordyce is a senior developer working with AI pair programmers that multiply his output 5-10x.

**Fordyce's Arsenal:** Claude Code (CLI), Codex (OpenAI), Cursor IDE, OpenClaw (agent orchestration, already deployed)

**What This Means Practically:**
- Stripe MCP connector: 2-3 hours (vs 2-3 days without AI)
- Agent prompt pipeline: 1-2 hours (vs 1-2 days)
- Debugging: AI diagnoses in minutes
- Test suites: AI generates 80%, Fordyce reviews and adds edge cases
- Output equivalence: Fordyce + AI ≈ 3-5 traditional developers

**Bus Factor Mitigation:** All code version-controlled. AI tools can onboard a new developer in hours. Agent configs are declarative (role cards + prompts + crons). Worst case: Gabriel + Claude Code can maintain existing agents and do emergency fixes.

**Timeline:** Full sandbox in 8 weeks (vs 16 without AI tools).

---

# 6. STATION ARCHITECTURE

## The Coordination Problem

Agent swarms are a COORDINATION problem, not a technical one. Solution: Ford's station-based Slack channels as structured stations. Each station has a purpose, an owner, clear inputs/outputs, and full human visibility.

## Channel Map

This extends Ford's original station-based channels. His foundational channels (#factory-pulse, #creative-lab, #production-line, #distribution-hub, #client-audits, #playbook-library) map to stations in this architecture. The channels below operationalize those stations with specific workflows.

### Category: COMMAND CENTER

**#daily-standup** — Morning sync (Sonny, daily 8 AM). Agent status → human priorities → today's focus.

**#alerts** — Critical issues requiring immediate attention. Only genuine alerts (noise = ignored channel).

**#decisions** — Decisions requiring human judgment. Format: context → options → recommendation → await approval.

### Category: REVENUE OPERATIONS

**#new-clients** — Onboarding pipeline. Owner: Christine. Agents: Sonny (briefs), QA Agent (checklists).

**#active-clients** — Ongoing client work. Owner: Christine. Per-client threads. Agents: Reporting, Content.

**#media-buying** — Ad campaign ops. Owner: Benjo. Agents: Media Buyer (daily reports, optimization).

**#client-delivery** — Deliverable review/approval. Owner: Guan Yuan. Flow: Draft → QA → human review → delivery.

### Category: CONTENT FACTORY

**#content-pipeline** — Content production. Owner: Guan Yuan. Agents: Newsletter, Content.

**#creative-review** — Visual/video review. Owner: Jimmy. Humans: Jimmy, Kevin.

### Category: BACK OFFICE

**#finance** — Financial ops. Owner: Zoey. Agents: Finance Bot.

**#systems** — Technical ops. Owner: Jenyvieve. Fordyce coordinates.

**#security** — Security/compliance. Owner: Fordyce. Agents: Security Agent.

### Category: KNOWLEDGE

**#sops** — SOPs. Owner: Guilbert. Agents: Memory Agent (captures decisions). Maps to Ford's #playbook-library.

**#learnings** — Post-mortems, insights. Owner: Sonny. Agents: Memory Agent (stores lessons).

### Category: AI OPERATIONS

**#agent-logs** — Agent activity transparency. Owner: Fordyce. Full audit trail.

**#agent-council** — Multi-AI review sessions. Owner: Sonny. Council deliberations on complex decisions.

---

# 7. RACI MATRIX

### Client Onboarding
**R:** Christine | **A:** Gabriel | **C:** Fordyce, Jenyvieve | **I:** Sonny, QA Agent

### Ad Campaign Launch
**R:** Benjo | **A:** Gabriel | **C:** Media Buyer Agent, QA Agent | **I:** Christine, Sonny

### Newsletter Production
**R:** Newsletter Agent + Guan Yuan | **A:** Guan Yuan | **C:** Gabriel | **I:** Christine, Memory Agent

### Weekly P&L Report
**R:** Finance Bot | **A:** Zoey | **C:** Gabriel | **I:** Sonny

### Client Reporting
**R:** Reporting Agent + Christine | **A:** Christine | **C:** Benjo, Gabriel | **I:** Sonny

### Agent Deployment
**R:** Fordyce | **A:** Gabriel | **C:** Sonny, relevant human owner | **I:** Full team

### Security Audit
**R:** Security Agent | **A:** Fordyce + Gabriel | **C:** Zoey | **I:** All agent owners

### Client Offboarding
**R:** Christine + Security Agent | **A:** Gabriel | **C:** Fordyce, Zoey | **I:** Sonny, Memory Agent

### Incident Response (Agent Failure)
**R:** Fordyce | **A:** Gabriel | **C:** Affected agent's human owner | **I:** Full team

### SOP Creation
**R:** Sonny + Guilbert | **A:** Guilbert | **C:** Subject matter expert | **I:** Full team

---

# 8. WORKFLOW MAPS

## 8A. NEW CLIENT ONBOARDING

**Duration:** 5-7 business days | **Human time:** ~3 hours | **AI time:** ~8 hours | **Quality gates:** 4

1. **Lead Qualification (Human)** — Christine confirms qualified, payment received. Posts to #new-clients.
2. **Brief Generation (AI + Human)** — Sonny generates comprehensive brief from contract, intake form, sales notes. Christine reviews, adds context.
3. **Client Folder Setup (AI)** — Sonny creates folder structure: brief.md, voice.md, contacts.md, campaigns/, content/, reports/. No human gate.
4. **Systems Setup (AI + Human)** — Jenyvieve + agents: GHL sub-account, integrations, tracking, reporting dashboard. Jenyvieve confirms all live.
5. **QA Pre-Flight (AI)** — QA Agent runs onboarding checklist. Christine reviews failures.
6. **Kickoff Call (Human)** — Christine + Gabriel (if strategic). Memory Agent stores preferences.
7. **Onboarding Complete (Human)** — Christine marks complete, posts summary.

## 8B. AD CAMPAIGN CREATION (65+ Scripts/Week)

**Target:** 65+ scripts/week | **Human time:** ~5 hours/week (review only)

1. **Brief (Human)** — Benjo/Gabriel: client, audience, offer, hooks (3-5), references
2. **Script Generation (AI)** — Content Agent generates 20-30 variations using CIE framework
3. **Peer Review (AI — Council)** — Second AI scores on hook strength, logic, CTA, voice (threshold: 28/40)
4. **Creative Review (Human)** — Guan Yuan/Jimmy selects 10-15 for production
5. **Asset Production (AI + Human)** — Jimmy (video), AI (static), UGC scripts to creators
6. **QA Pre-Launch (AI)** — QA Agent checks branding, copy, CTAs, tracking
7. **Campaign Launch (Human)** — Benjo uploads, sets targeting/budget/schedule
8. **Optimization (AI)** — Media Buyer daily monitoring, reports to #media-buying

## 8C. CONTENT PRODUCTION & DISTRIBUTION

**Newsletter:** Theme selection (Human+AI) → Draft (Newsletter Agent) → Review (Guan Yuan) → QA (QA Agent) → Send (Guan Yuan) → Performance tracking (AI)

**Social Media:** Calendar (Human+AI) → Batch generation (Content Agent) → Review/queue (Guan Yuan/Claire) → Publish → Engagement (Claire)

## 8D. CLIENT REPORTING & AUDITS

**Weekly:** Data collection (Reporting Agent, Meta/GA/CRM) → Report generation (AI) → Review/contextualize (Christine/Benjo) → Client delivery (Christine)

**Monthly:** Deep data pull (AI) → Audit analysis (Council Pattern) → Strategy recommendations (AI+Human) → Client strategy call (Gabriel/Christine)

## 8E. FINANCIAL OPERATIONS

**Weekly P&L:** Data pull (Finance Bot, Monday 6 AM) → Report (#finance) → Review (Zoey)

**Invoices:** Tracking (Finance Bot, alerts overdue) → Follow-up draft (Sonny, 7 days overdue) → Send (Zoey/Christine) → Escalation (Gabriel, >30 days)

**Cash Flow:** 30/60/90-day forecast (AI) → Alerts (Yellow <90d, Orange <60d, Red <30d) → Action (Gabriel + Zoey)

## 8F. KNOWLEDGE CAPTURE & SOPs

**Real-Time Capture:** Decision made → Memory Agent evaluates (preference? decision? fact? lesson?) → Store (low confidence: "needs-review"; high: direct) → Deduplication check. Emoji-triggered captures (🧠) allow any team member to flag content for archival.

**SOP Creation:** Process identified → Sonny drafts → Guilbert + process owner review → Publish, update QMD, announce in #sops

**Monthly Audit:** Memory Agent reviews for staleness, contradictions, gaps → Audit report → Gabriel reviews flagged items

---

# 9. MEMORY ARCHITECTURE

## Three-Tier Memory System

**Tier 1: Working Memory (Session)** — Current conversation context. Disposable. Token window (~200K for Opus).

**Tier 2: QMD Short-Term Memory (Days to Weeks)** — Local workspace files: daily logs (memory/YYYY-MM-DD.md), client knowledge, playbooks, SOPs. This is Ford's QMD concept — short-term memory per client, backed by local files.

**Tier 3: SuperMemory Long-Term (Permanent)** — Curated, high-signal facts. Categories: preference, fact, decision, entity, lesson. Config: containerTag: sonny_v3, autoCapture: OFF, autoRecall: ON. This is Ford's long-term wisdom layer.

## Memory Quality Rules

- 1.0: Gabriel explicitly stated, unlikely to change
- 0.8: Strongly implied, probably stable
- 0.6: Inferred from behavior, may need confirmation
- 0.4: Uncertain, stored for pattern matching
- <0.4: Don't store

**Memory Influence Rate:** ~30% (balances learned context vs exploring new approaches)

---

# 10. SECURITY ARCHITECTURE

**Client Data Isolation:** Separate folders, GHL sub-accounts, ad accounts per client. No shared credentials. Security Agent monthly verification.

**Credential Management:** All in LastPass (except OAuth). Named: {service}-{account}-{purpose}. Rotation: quarterly (sensitive), annual (others). No credentials in code, config, or chat.

**PDPA Compliance:** Consent documented, purpose limitation enforced, retention limits respected, access/correction/withdrawal supported. Security Agent maintains data inventory.

**Client Offboarding:** Final deliverables transferred → access revoked → data archived → isolated from active workspace → post-retention deletion scheduled → certificate generated.

**Access Control (Least Privilege):**
- Sonny: Read all client data, read finance summaries, coordinate. No credentials.
- Media Buyer: Own clients only. Ads API. No finance, no credentials.
- Finance Bot: No client data. Read all finance. Stripe/Xero.
- Security Agent: Read all (audit). Audit everything.
- All others: Own clients/scope only, minimal access.

**Incident Response:** Security Agent alerts #alerts → Fordyce assesses → Gabriel decides response → Incident logged with root cause → Mitigation implemented → Post-mortem in #learnings.

---

# 11. QUALITY ARCHITECTURE

## The Council Pattern

**Use for:** Strategic decisions, creative review, complex analysis, quality gates before delivery.
**Don't use for:** Routine tasks, time-sensitive responses, clear-cut decisions.

**Standard Council:** Conservative, Optimistic, Synthesis (3 perspectives).

**LLM Council Tool:** Chairman: Claude Opus 4.6 | Members: GPT 5.2, Gemini 3 Pro, Grok 4.1 Fast | Location: localhost:5173

**Quality Gates by Type:**
- **Ad Scripts:** AI peer review → Human creative review → QA Agent → Human launch
- **Newsletters:** AI quality check → Human content review → QA (links, formatting) → Human send
- **Client Reports:** AI data check → Human context review → Human tone check → Human send
- **Financial:** AI calculation verification → Human review → Dual approval for >SGD $500

---

# 12. COORDINATION ARCHITECTURE

## Core Flow

Request comes in → Sonny evaluates → Capacity check → If approved: mission → steps → assigned to agents → execute → complete

## Heartbeat System

**Every 5 min:** Check stuck tasks, evaluate triggers, process pending, recover failed tasks.
**Daily 8 AM:** Standup summary, flag overdue, post to #daily-standup.
**Weekly Monday 6 AM:** Finance Bot P&L, performance summaries, SOP gap check.

## Triggers

- **Reactive:** Event → Agent responds
- **Proactive:** Schedule → Agent initiates
- **Skip/Jitter:** 10-20% skip on non-critical, ±30 min jitter. Critical tasks always fire.

---

# 13. TECHNICAL IMPLEMENTATION

## What Already Exists

- **Infrastructure:** Mac mini (always-on), OpenClaw, SuperMemory, QMD
- **Models:** Claude Opus 4.6, Sonnet 4, Haiku 4, LLM Council (localhost:5173)
- **APIs:** Stripe, Xero, GHL/Salesable, Meta Ads, Google Workspace, Beehiiv
- **Comms:** Discord (Sonny), Slack (team)

## What to Build

Ford designs and implements all technical details (auth models, data schemas, error handling patterns, monitoring systems). The high-level build sequence:

**Weeks 1-2 (Foundation):** Media Buyer Agent (Meta Ads API monitoring, daily cron, reporting), Finance Bot (extend Stripe/Xero MCP, weekly P&L), QA Agent (link checker, format validator, checklist runner)

**Weeks 3-4 (Content Pipeline):** Security Agent (audit scripts, credential tracker, offboarding), Memory Agent (curation logic, evaluation, monthly audit), Newsletter Agent (Beehiiv integration, draft pipeline), Content Agent (social integrations, batch generation, scheduling queue)

**Weeks 5-6 (Full Pipeline):** Reporting Agent (multi-source aggregation, templates), Support Agent (ticket intake, knowledge base, escalation routing)

**Weeks 7-8 (Graduation):** Full pipeline validation, metrics collection, rollback drill. No new builds — tuning and proving.

## Key Technical Requirements (for Ford's Design)

- **Agent identity:** Each agent runs as a named session with tagged logs for audit
- **Credential scoping:** Per-agent, least-privilege, read-only by default
- **Error handling:** Retry with backoff for transient failures, graceful degradation for non-critical agents, immediate alerts for critical failures. Never retry infinitely or retry destructive ops.
- **Monitoring:** Per-agent health metrics (tasks completed/failed, error rate, cost). Alert thresholds for error rate, cost spikes, queue depth, unresponsive agents. Weekly auto-generated observability report.
- **Logging:** All actions logged, sensitive data never logged, 90-day retention

## What to Buy

**Already have (no cost):** OpenClaw, SuperMemory, Mac mini, most API connections
**New:** OpenRouter API SGD $300-500/mo, potential SaaS SGD $100-200/mo, experiment buffer SGD $200/mo. **Total: ~SGD $500-700/mo**

---

# 14. MIGRATION PLAN

## Current State

Slack (team), Discord (Sonny), Email, WhatsApp | Xero, Stripe, manual spreadsheets | GHL/Salesable | Manual content (Google Docs, Canva) | Manual ads (Meta/Google Ads Manager) | Beehiiv + GHL newsletters | Manual reporting (Sheets/Slides)

## Migration Approach

**Keep:** Slack, Discord, Email (become station layer), Xero, Stripe (agents read from), GHL/Salesable, Beehiiv

**Augment:** Meta Ads (+Media Buyer Agent), Google Sheets P&L (+Finance Bot), manual content (+Newsletter/Content Agents), manual reporting (+Reporting Agent)

**Replace:** Manual daily ad monitoring → Media Buyer cron. Manual invoice tracking → Finance Bot. Manual QA → QA Agent. Manual ticket triage → Support Agent.

**Sequence per workflow:** Document manual SOP → Deploy agent shadow mode → Compare 1-2 weeks → If quality matches: agent primary, human reviewer → If not: iterate prompts, extend shadow.

---

# 15. HUMAN TRANSITION PLAN

## Current → Target

**Current (Feb 2026): 12 people, SGD $21,015/mo**

**Target (May 2026): 6 FT + 3 PT, SGD $16,628/mo** — Jimmy*, Fordyce, Guilbert, Jenyvieve (FT); Guan Yuan, Benjo, Christine (PT)

*Jimmy on probation — if replaced with junior videographer (~SGD $2-3K): total ~SGD $12,628*

**Monthly savings: SGD $4,387/mo** (or SGD $8,387 if Jimmy replaced)

## Transition Timeline

- **Feb 28:** Joenel exits (SGD $768/mo saved). Media Buyer Agent replaces. Benjo absorbs oversight.
- **Mar 10:** Jimmy review. Decision: continue or replace.
- **Mar 31:** Shirath to project-based (SGD $750/mo saved). AI design tools + Jimmy for complex.
- **Apr 30:** Mirielle exits (SGD $1,047/mo saved). Fordyce absorbs N8N, AI handles rest.

**Transition Support:** 2-week notice minimum, clear communication, references, role clarity sessions, AI tool training for remaining team.

---

# 16. FOUR-PHASE ROLLOUT

## Phase 1: Sandbox Foundation (Weeks 1-2)

Deploy Media Buyer, Finance Bot, QA Agent in shadow mode on Ascend's own marketing.
**Pass:** All 3 producing outputs, compared against baseline, zero integration failures 3 days, rollback tested.

## Phase 2: Sandbox Content Pipeline (Weeks 3-4)

Deploy Security, Memory, Newsletter, Content Agents. Joenel exits, Jimmy review, Shirath notification.
**Pass:** All 7 operational, newsletter/content drafts ≥7/10, QA catching errors humans would catch.

## Phase 3: Sandbox Full Pipeline (Weeks 5-6)

Deploy Reporting, Support Agents.
**Pass:** All 9+ operational, full end-to-end pipeline, reports match baseline, Support resolving >30% test tickets.

## Phase 4: Sandbox Graduation & Rollout (Weeks 7-8)

2-week full-autonomy test. Graduation assessment:
- [ ] Quality ≥7/10 average
- [ ] Zero critical errors in 2-week test
- [ ] Human review time <30% of baseline
- [ ] All agents stable (no downtime >4h)
- [ ] Rollback tested
- [ ] All manual SOPs documented
- [ ] Monitoring/alerting functional

**Post-Graduation:** Weeks 9-10 Client 1 → Weeks 11-12 Clients 2-3 → Weeks 13-16 remaining → Ongoing optimization.

---

# 17. COST MODEL

## Current vs Target

**Current:** Payroll SGD $21,015 + Overhead ~SGD $15,000 = **~SGD $36,015/mo**

**Target:** Payroll SGD $16,628 + AI SGD $1,500-2,000 + Software SGD $5,000-5,500 + Other SGD $9,500 = **~SGD $32,628-34,128/mo**

**Savings: SGD $2,000-3,400/mo** (if Jimmy replaced: additional SGD $4-5K)

## Cost Per Deliverable

| Deliverable | Before | After | Gain |
|-------------|--------|-------|------|
| Ad script | ~SGD $50 | ~SGD $5 | 10x |
| Newsletter | ~SGD $150 | ~SGD $30 | 5x |
| Client report | ~SGD $100 | ~SGD $20 | 5x |

## Scalability

The key value: same human team can handle 2-3x the client load. Adding clients increases AI API costs marginally (SGD $50-100/client/mo) vs SGD $2-3K/client/mo in human costs under the old model. This is how the manpower problem gets solved permanently.

---

# 18. RISK REGISTER

## Technical Risks

**Agent Hallucination** — Prob: Medium | Impact: High — Mitigation: Council pattern, human gates, QA Agent, confidence thresholds. Rollback: disable agent, human resumes.

**API Outages** — Prob: Low-Medium | Impact: Medium — Mitigation: Retry with backoff, graceful degradation, multi-model fallback. Rollback: manual operations.

**Data Leakage / Cross-Client Contamination** — Prob: Low | Impact: Critical — Mitigation: Security Agent audits, folder isolation, per-agent scoping, audit logging. Owner: Fordyce + Gabriel.

**Prompt Injection** — Prob: Low | Impact: High — Mitigation: Input sanitization, constraint boundaries, agents never execute external instructions.

## Operational Risks

**Fordyce Unavailability** — Prob: Low-Medium | Impact: High — Mitigation: Version-controlled repos, declarative configs, AI tools onboard replacements quickly, Gabriel + Claude Code for emergency maintenance.

**Quality Degradation / Review Fatigue** — Prob: Medium | Impact: High — Mitigation: Council peer review, QA pre-filtering, quality tracking, rotating reviewers, alert if review time drops (suggests rubber-stamping).

**Team Morale** — Prob: Medium | Impact: Medium — Mitigation: Clear communication, role clarity, growth paths, transition support.

## Sandbox-Specific Risks

**Sandbox Takes >8 Weeks** — Prob: Medium | Impact: Low — 2-week buffer. If week 10 still failing, reassess specific agents not entire system.

**Quality Plateaus Below Threshold** — Prob: Low-Medium | Impact: Medium — Options: retune prompts, upgrade model tier, restructure scope, accept human-assisted mode. Trigger: stuck below 7/10 for 2+ weeks.

**AI Can't Match Human for Specific Tasks** — Prob: Medium | Impact: Low — Not every task needs automation. Factory saves time even at 60% automation.

**Client Notices Quality Shift** — Prob: Low-Medium | Impact: High — Start with tolerant client, human reviews mandatory, active feedback collection. Revert immediately if concerns raised.

## Financial Risks

**API Costs Exceed Budget** — Prob: Low | Impact: Medium — Per-agent caps, cost alerts at SGD $50/agent/day, model optimization.

---

# 19. SUCCESS METRICS

## Sandbox (End of Week 8)

**Operational:** All agents deployed, full pipeline proven, graduation passed.
**Quality:** Average ≥7/10, zero critical errors, QA catching >80% of errors.
**Efficiency:** Human review <30% of baseline, cycle time reduced ≥50%.

## Post-Rollout (End of Month 4)

**Operational:** All clients on pipeline, team at target, agents <5% error rate.
**Financial:** Payroll ≤SGD $16,628, AI ≤SGD $2,000, total operating down SGD $2-3K.
**Quality:** Client satisfaction maintained/improved, zero major AI incidents, team morale stable.

## Long-Term (End of 2026)

**Operational:** Factory running autonomously, Gabriel on growth not ops, scalable to 2-3x clients.
**Strategic:** Model proven and documentable, potential to license/teach, Ascend as AI-native agency case study.

---

# APPENDIX A: PROMPT LIBRARY

All prompts stored in: `business/operations/prompts/`

Files: onboarding-brief.md, onboarding-qa.md, cie-script-generation.md, script-review.md, newsletter-draft.md, social-post.md, weekly-report.md, monthly-audit.md, weekly-pl.md, memory-evaluation.md, sop-draft.md

---

# APPENDIX B: CHANNEL SETUP CHECKLIST

**COMMAND CENTER:** #daily-standup, #alerts, #decisions
**REVENUE OPS:** #new-clients, #active-clients, #media-buying, #client-delivery
**CONTENT FACTORY:** #content-pipeline, #creative-review
**BACK OFFICE:** #finance, #systems, #security
**KNOWLEDGE:** #sops, #learnings
**AI OPS:** #agent-logs, #agent-council

*Ford's original stations (#factory-pulse, #creative-lab, #production-line, #distribution-hub, #client-audits, #playbook-library) serve as the foundational layer these channels extend.*

---

# APPENDIX C: AGENT DEPLOYMENT CHECKLIST

- [ ] Role card documented (owns, delivers, can't touch, escalates)
- [ ] Kill switch defined and tested
- [ ] Error handling requirements defined
- [ ] Knowledge base identified and accessible
- [ ] Prompts created and tested
- [ ] Human gates defined
- [ ] Integration/API access configured (least privilege)
- [ ] Shadow mode test completed (1-2 weeks)
- [ ] Quality compared against human baseline
- [ ] Owner assigned
- [ ] Monitoring configured
- [ ] Escalation path tested
- [ ] Rollback procedure documented and tested
- [ ] Go-live approved by Gabriel

---

# APPENDIX D: WEEKLY RHYTHM

**Monday:** 6 AM Finance Bot P&L → 8 AM standup → 9 AM Zoey reviews P&L → EOD priorities confirmed
**Tue-Thu:** 8 AM standup → agents execute, humans review → EOD progress logged
**Friday:** 8 AM standup → 2 PM retrospective → 4 PM next week planning → EOD weekend autopilot

**Ongoing:** 5-min heartbeat, alerts as needed, continuous agent logs, weekly observability report.

---

# DOCUMENT HISTORY

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| v1.0 | Feb 9, 2026 | Sonny W + LLM Council | Initial release |
| v2.0 | Feb 9, 2026 | Sonny W + LLM Council | Sandbox Protocol, AI Dev Stack, RACI, technical details, kill switches, migration plan, transition risks |
| v2.1 | Feb 9, 2026 | Sonny W | Reframed problem (manpower focus), removed code/schemas (Ford designs), aligned with Ford's blueprint, compressed prose |

---

*END OF DOCUMENT*

*This is a living document. Updates versioned and logged.*
*For questions: Sonny (Discord #chief-of-staff) or Gabriel Wong.*
