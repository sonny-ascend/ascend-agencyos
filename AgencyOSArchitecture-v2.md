# AGENCY OS ARCHITECTURE v2.0
## Ascend Group Digital Factory — The Build Document

*Version: 2.0*
*Date: February 9, 2026*
*Author: Sonny W (AI Chief of Staff) + LLM Council v1.0 feedback*
*Classification: INTERNAL BUILD DOCUMENT*
*Status: APPROVED FOR IMPLEMENTATION*
*Changelog: v2.0 incorporates LLM Council critique (session #003) and Gabriel's directives*

---

# 1. EXECUTIVE SUMMARY

## What This Document Is

This is the **master architecture document** for transforming Ascend Group from a traditional 15-person agency into a hybrid Digital Factory: 6 full-time humans + 3 part-time specialists + 10 AI agents.

This is NOT a strategy deck. This is a **BUILD document** — specific enough that an engineer can implement it, detailed enough that operations can run from it, comprehensive enough that it survives personnel changes.

**Scope Boundary:** This document covers the Digital Factory's operational architecture — how work gets done, who does what, and how agents are built and coordinated. Revenue growth strategy, sales pipelines, and client acquisition are OUT OF SCOPE and belong in a separate Revenue Playbook. The factory's value proposition is operational efficiency and scalability, not revenue forecasting.

## Why This Architecture Exists

**The Problem:**
- Revenue: SGD $40,532/mo (profitable on P&L)
- Cash flow: -SGD $1,038/mo before founder pay (DBS loan squeeze)
- Team payroll: SGD $21,015/mo for 12 people
- Gabriel + Zoey need: SGD $9,000/mo minimum combined pay
- The math requires cost reduction to create breathing room

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
- Gabriel + Zoey pay: SGD $9,000-12,000/mo combined
- Digital Factory proven end-to-end on sandbox client
- Rolling out to remaining clients

**By December 2026:**
- DBS loan paid off (SGD $5,593/mo permanent savings)
- Digital Factory running at full capacity across all clients
- Gabriel focused on growth, not operations
- Scalable to 2-3x client load without headcount increase

---

# 2. CORE PRINCIPLES

These principles drive every architectural decision. When in doubt, return to these.

## Principle 1: AI Proposes, Humans Dispose

**Rule:** No AI output reaches a client without human approval.

AI can draft, analyze, optimize, recommend. Humans make final calls on anything that:
- Goes to a paying client
- Involves money (spend, invoices, payments)
- Is public-facing (social media, ads, emails)
- Could create legal/compliance risk

This is non-negotiable. The Digital Factory is not about removing humans — it's about making human time 10x more valuable.

## Principle 2: All Men Are Corruptible (And So Are AI Agents)

**Rule:** Build structural safeguards. Never rely on a single point of trust.

Gabriel's decision-making philosophy applied to AI:
- Multiple AI agents check each other's work (Council Pattern)
- No single agent has write access to critical systems AND approval authority
- Audit logs for all consequential actions
- Regular review of AI outputs for drift

If one agent gets compromised or starts hallucinating, others catch it.

## Principle 3: Constraints Do More Work Than Capabilities

**Rule:** Define what agents CAN'T touch before what they can do.

From @Voxyz_ai: "The 'can't touch' boundaries do more work than the role descriptions. Constraints are the whole product. Defining what agents should NOT do is 80% of making them reliable."

Every agent role card specifies:
- What they own
- What they deliver
- What they CANNOT touch
- When they escalate

## Principle 4: Coordination > Capability

**Rule:** A swarm of coordinated "dumb" agents beats one brilliant unmanaged agent.

From @jumperz: "Agent swarms are a COORDINATION problem, not a technical one. Who decides which agent gets which task? How do they avoid duplicate work? How do they hand off tasks?"

Solution: Slack/Discord channels as coordination layer. Structured stations. A coordinator (Sonny) as right-hand brain dispatching work.

## Principle 5: Memory Is Sacred

**Rule:** Auto-capture is dangerous. Selective capture is essential.

From Gabriel's requirements: Memory Agent curates what gets stored. Not everything is worth remembering. Bad data in memory = compounding errors.

Three-tier memory:
- **Working memory:** Current session context (disposable)
- **Short-term memory:** QMD local files (days to weeks)
- **Long-term memory:** SuperMemory (permanent, curated)

## Principle 6: Progressive Autonomy (Trust Gradient)

**Rule:** Trust is earned through demonstrated competence, then explicitly granted.

This is Gabriel's Trust Gradient pattern — the same as paper trading before real money. New agents start with training wheels:
- Human approval on all outputs
- Narrow scope
- Verbose logging

As confidence builds:
- Approval thresholds raise
- Scope expands
- Logging becomes exception-based

From @Voxyz_ai's Initiative System: Agents propose their own work only after accumulating ≥5 high-confidence memories.

## Principle 7: Optimize for Gabriel's Time

**Rule:** Every design decision should answer: "Does this reduce Gabriel's operational load?"

Gabriel's highest-value activities:
- Live teaching (webinars, bootcamps)
- Closing sales
- Creative direction
- Strategic partnerships

Everything else should flow to the Digital Factory. Gabriel reviews outputs, doesn't create them.

## Principle 8: Sandbox First, Scale Second

**Rule:** Prove the full factory pipeline on ONE client before rolling out to others.

Never deploy untested systems across all clients simultaneously. Pick one sandbox client (or internal project), build the entire pipeline end-to-end, validate it works, measure quality against human baseline, THEN roll out progressively.

This principle applies at every level:
- New agent? Sandbox one workflow first.
- New integration? Test on one client first.
- New process? Prove it internally first.

---

# 3. SANDBOX PROTOCOL

## Purpose

Before the Digital Factory touches any paying client at scale, it must be proven end-to-end on a single sandbox project. This is Gabriel's Trust Gradient applied to the entire system — paper trading before real money.

## Sandbox Selection Criteria

Pick ONE client or project that has:
- Low-to-medium complexity (not the biggest or most demanding client)
- Full service scope (ads + content + reporting — tests the whole pipeline)
- Tolerant relationship (client who trusts us and can handle a brief learning curve)
- Representative workload (similar to what most clients need)
- OR: Use an internal project (Ascend's own marketing) as the sandbox — zero client risk

**Recommended sandbox:** Ascend Group's own marketing (internal). This lets us test every station with zero client risk.

## Sandbox Build Plan

**Week 1-2: Foundation**
- Deploy Media Buyer Agent monitoring Ascend's own ad campaigns
- Deploy Finance Bot pulling Ascend's Stripe/Xero data
- Deploy QA Agent checking Ascend's own content
- All agents in shadow mode (produce outputs but humans still do the real work)
- Compare AI outputs vs human outputs — measure quality gap

**Week 3-4: Content Pipeline**
- Deploy Newsletter Agent drafting Ascend's newsletters
- Deploy Content Agent producing Ascend's social posts
- Human reviews every output, scores quality 1-10
- Iterate prompts until quality consistently ≥7/10

**Week 5-6: Full Pipeline**
- Deploy Reporting Agent generating Ascend's internal performance reports
- Deploy Memory Agent curating Ascend's knowledge
- All 7+ agents running on the sandbox
- End-to-end flow: brief → AI draft → QA → human review → delivery
- Measure: cycle time, error rate, human review time

**Week 7-8: Graduation**
- Run full pipeline without shadow mode (AI as primary, human as reviewer)
- Track metrics for 2 weeks under real conditions
- Graduation criteria (ALL must pass):
  - Quality score ≥7/10 average across all deliverable types
  - Zero critical errors reaching "client" (internal stakeholders)
  - Human review time <30% of pre-factory baseline
  - All agents stable (no crashes, no stuck tasks for >4 hours)
  - Rollback tested and confirmed working

## Rollback Procedures

**Per-Agent Rollback:**
- Every agent has a kill switch: disable the cron/trigger in OpenClaw
- Human who previously did the work resumes immediately
- Agent outputs archived for post-mortem analysis
- Rollback decision authority: Fordyce (technical) or Gabriel (strategic)

**System-Wide Rollback ("Break Glass"):**
- Trigger: 2+ agents failing simultaneously, or 1 critical agent (Finance Bot, Media Buyer) failing for >24 hours
- Action: Disable all agent crons. Team reverts to pre-factory manual operations.
- Duration: Until root cause identified and fixed
- Owner: Fordyce executes, Gabriel approves
- Pre-requirement: Document current manual procedures BEFORE deploying agents (this is the rollback target)

**Rollback Readiness Checklist:**
- [ ] All current manual procedures documented as SOPs
- [ ] Each human team member knows their rollback responsibilities
- [ ] Agent kill switches tested (can disable in <5 minutes)
- [ ] Communication template ready ("We're temporarily reverting to manual for X")
- [ ] Rollback drill completed at least once before first client deployment

## Sandbox → Production Rollout

After sandbox graduation:
- **Client 1:** Lowest-risk paying client. Run for 2 weeks. Measure.
- **Clients 2-3:** Next tier. Run for 2 weeks. Measure.
- **All remaining clients:** Full rollout with monitoring.
- At each stage: same graduation criteria must pass before expanding

---

# 4. AGENT ROSTER

## Overview

**Human Team (Target: 6 FT + 3 PT)**

- **Gabriel Wong** — CEO / Strategy — FT — Variable — Active
- **Zoey Sin** — COO / Finance — FT — Variable — Active
- **Jimmy Ng** — Creative Director — FT — SGD $7,000 — PROBATION (Mar 10 review)
- **Fordyce Gozali** — Senior AI Engineer — FT — SGD $2,083 — Critical — builds agents (see AI Development Stack)
- **Guilbert Codog** — People & Systems Lead — FT — SGD $1,303 — Most reliable person
- **Jenyvieve Sarmiento** — Head of Systems — FT — SGD $1,234 — Systems backbone
- **Guan Yuan Pok** — AI Content Specialist — PT — SGD $1,912 — Solid — curates AI output
- **Benjo Magcalen** — Production Lead — PT — SGD $1,862 — "100% AI" — best executor
- **Christine Ybanez** — Client Success — PT — SGD $1,234 — Best client-facing

*Subtotal humans: SGD $16,628/mo (after restructure complete, excluding G+Z)*
*If Jimmy replaced with junior videographer: SGD $12,628/mo*

**AI Agent Team (Target: 10 Agents)**

- **Sonny** — Chief of Staff / Coordinator — Opus 4.6 — SGD $300-500/mo
- **Media Buyer** — Campaign optimization — Sonnet 4 — SGD $100-200/mo
- **Finance Bot** — P&L, invoices, forecasts — Sonnet 4 — SGD $50-100/mo
- **Security Agent** — Data isolation, compliance — Opus 4.6 — SGD $50-100/mo
- **Memory Agent** — Curates knowledge capture — Sonnet 4 — SGD $50-100/mo
- **Newsletter Agent** — Drafts newsletters — Sonnet 4 — SGD $100-200/mo
- **Content Agent** — Social media content — Sonnet 4 — SGD $100-200/mo
- **QA Agent** — Pre-flight checks — Haiku 4 — SGD $20-50/mo
- **Reporting Agent** — Client reports — Sonnet 4 — SGD $100-150/mo
- **Support Agent** — Salesable CS tickets — Sonnet 4 — SGD $100-200/mo

*Subtotal AI agents: SGD $1,000-1,800/mo*

**Total Operating Cost Target:**
- Humans: SGD $16,628/mo (excluding G+Z)
- AI Agents: SGD $1,500/mo
- Infrastructure: SGD $500/mo
- **Total: ~SGD $18,628/mo** (down from SGD $21,015 with MORE capability)

---

## Agent Role Cards

### SONNY — Chief of Staff / Coordinator

**Classification:** AI Agent (Opus 4.6)
**Status:** Operational since Feb 2026
**Reports to:** Gabriel Wong
**Budget:** SGD $500/mo API

**OWNS:**
- Task coordination across all agents
- Daily operational monitoring
- Research and synthesis requests
- Memory curation decisions (what to store/forget)
- Communication drafts (internal and external)
- Session-to-session context continuity

**DELIVERS:**
- Dispatched tasks to appropriate agents
- Flagged issues requiring human attention
- Research outputs and recommendations
- Draft communications for Gabriel's review
- System health monitoring

**CANNOT TOUCH:**
- Final approval on client deliverables (human only)
- Financial transactions over SGD $100 without explicit approval
- Deleting files without explicit approval
- Pushing to production/main branches
- Public statements on Gabriel's behalf
- Expanding own permissions or access

**ESCALATES TO:**
- Gabriel: Strategic decisions, high-spend approvals, partnership terms
- Zoey: Financial discrepancies, HR issues
- Fordyce: Technical failures, agent deployment issues

**KILL SWITCH:** Disable OpenClaw gateway → Gabriel takes over coordination manually

**KNOWLEDGE BASE:**
- SOUL.md, TOOLS.md, AGENTS.md (auto-injected)
- SuperMemory (auto-recall enabled)
- QMD workspace files
- ascend.md (company context)
- All playbooks and SOPs in workspace

---

### MEDIA BUYER — Campaign Optimization Agent

**Classification:** AI Agent (Sonnet 4)
**Status:** Deploy during Sandbox Phase
**Reports to:** Benjo (Production Lead)
**Replaces:** Joenel Masculino (PT, SGD $768/mo)

**OWNS:**
- Daily monitoring of all active ad campaigns
- Pause/scale decisions within approved parameters
- Performance anomaly detection
- Budget pacing alerts
- Creative fatigue identification

**DELIVERS:**
- Daily campaign performance summary (posted to #media-buying)
- Pause recommendations for losing ads
- Scale recommendations for winning ads
- Weekly optimization report
- Suggested new campaign launches (for human approval)

**CANNOT TOUCH:**
- Launching NEW campaigns (human approval required)
- Budget increases over 20% in 24 hours
- Changing targeting on existing campaigns
- Accessing client ad accounts directly (works through API)
- Making strategic decisions about offer/angle changes

**ESCALATES TO:**
- Benjo: Campaigns needing strategic changes
- Gabriel: Budget reallocation over SGD $500
- Sonny: Reporting anomalies or technical issues

**KILL SWITCH:** Disable monitoring cron → Benjo resumes manual daily checks

**ERROR HANDLING:**
- Meta API timeout: Retry 3x with exponential backoff (5s, 15s, 45s). If all fail, post alert to #alerts and skip that cycle.
- Data inconsistency: Flag in #alerts, do NOT act on suspicious data. Wait for human verification.
- Stale data (>6h old): Mark report as "STALE DATA" and alert Fordyce.

**KNOWLEDGE BASE:**
- Client campaign briefs (per client folder)
- Performance benchmarks (business/ads/playbooks/)
- Historical campaign data (Meta Ads API)
- Winning ad swipe files

**HUMAN GATES:**
- New campaign launch: Benjo approves
- Budget increase >20%: Gabriel approves
- Pausing high-spend campaigns (>SGD $50/day): Benjo approves

---

### FINANCE BOT — CFO Assistant Agent

**Classification:** AI Agent (Sonnet 4)
**Status:** Deploy during Sandbox Phase
**Reports to:** Zoey Sin
**Replaces:** Manual spreadsheet tracking

**OWNS:**
- Auto-pulling Stripe revenue data
- Auto-pulling Xero expense data
- Cash flow calculations
- Invoice tracking and overdue alerts
- Weekly P&L summary generation

**DELIVERS:**
- Weekly P&L report (every Monday, posted to #finance)
- Invoice status updates (overdue flagged)
- Cash flow forecast (30/60/90 day rolling)
- Expense anomaly alerts

**CANNOT TOUCH:**
- Initiating payments or transfers
- Changing invoice amounts
- Accessing bank accounts directly
- Approving expenses
- Modifying Xero records

**ESCALATES TO:**
- Zoey: Any overdue invoice >SGD $1,000 or >30 days
- Gabriel: Cash flow projections showing negative runway <60 days
- Sonny: Data inconsistencies between Stripe and Xero

**KILL SWITCH:** Disable P&L cron → Zoey reverts to manual spreadsheet tracking

**ERROR HANDLING:**
- Stripe API failure: Retry 3x with backoff. If fails, generate partial report with "[STRIPE DATA UNAVAILABLE]" flag.
- Xero API failure: Same pattern. Never generate a P&L with silently missing data.
- Data mismatch (Stripe vs Xero >5% variance): Flag as anomaly, do NOT auto-reconcile. Post to #finance for Zoey.

**KNOWLEDGE BASE:**
- Stripe MCP connection (read-only)
- Xero MCP connection (read-only)
- business/operations/finance-data-report.md
- Client contract terms (for invoice amounts)

**HUMAN GATES:**
- All payment approvals: Zoey
- Invoice disputes: Zoey + Gabriel

---

### SECURITY AGENT — Data Isolation & Compliance

**Classification:** AI Agent (Opus 4.6 — higher tier for sensitive work)
**Status:** Deploy Phase 2 (Sandbox Week 3-4)
**Reports to:** Fordyce (technical), Gabriel (policy)

**OWNS:**
- Client data isolation verification
- Credential rotation reminders
- PDPA compliance monitoring
- Client offboarding data cleanup
- Access audit logging
- Agent permission reviews

**DELIVERS:**
- Monthly security audit report
- Client data isolation certificates
- Credential expiry warnings
- Offboarding completion confirmations
- Permission anomaly alerts

**CANNOT TOUCH:**
- Actually rotating credentials (requests human action)
- Deleting client data (requests human confirmation)
- Modifying agent permissions (proposes changes only)
- Accessing production databases directly

**ESCALATES TO:**
- Fordyce: Technical security issues
- Gabriel: Policy decisions, compliance concerns
- Zoey: Client data requests (legal)

**KILL SWITCH:** Disable audit crons → Fordyce runs manual security checks monthly

**KNOWLEDGE BASE:**
- Client list and data locations
- PDPA requirements summary
- Credential storage locations (LastPass structure)
- Agent permission matrix

**HUMAN GATES:**
- All data deletion: Fordyce + Gabriel dual approval
- Credential changes: Fordyce executes
- Compliance certifications: Gabriel signs

---

### MEMORY AGENT — Knowledge Curator

**Classification:** AI Agent (Sonnet 4)
**Status:** Deploy Phase 2 (Sandbox Week 3-4)
**Reports to:** Sonny (coordination), Gabriel (policy)

**OWNS:**
- Deciding what gets stored in SuperMemory
- Tagging and categorizing memories
- Deduplication of similar memories
- Confidence scoring on stored facts
- Periodic memory audits (stale/wrong detection)
- QMD file organization

**DELIVERS:**
- Curated memory entries (preference, fact, decision, entity, lesson)
- Memory quality reports (monthly)
- Stale memory flagging
- Knowledge base gap identification

**CANNOT TOUCH:**
- Storing without classification
- Auto-capturing everything (explicit anti-pattern)
- Deleting high-confidence memories without human approval
- Accessing memories marked as sensitive/private

**ESCALATES TO:**
- Gabriel: Conflicting memories about preferences/decisions
- Sonny: Knowledge gaps affecting operations
- Fordyce: Memory system technical issues

**KILL SWITCH:** Disable curation crons → Sonny handles memory decisions manually (current state)

**HUMAN GATES:**
- Deleting memories with confidence >0.8: Gabriel approves
- Modifying preferences category: Gabriel confirms

---

### NEWSLETTER AGENT — Content Production

**Classification:** AI Agent (Sonnet 4)
**Status:** Deploy Phase 2 (Sandbox Week 3-4)
**Reports to:** Guan Yuan (Content Specialist)

**OWNS:**
- Drafting newsletters in client voice
- Formatting for platform (Beehiiv, GHL)
- Performance metric tracking
- Subject line generation
- Content theme recommendations

**DELIVERS:**
- Draft newsletters (queued for human review)
- Subject line variations (3-5 options)
- Engagement reports (post-send)
- Content calendar suggestions

**CANNOT TOUCH:**
- Sending newsletters (human triggers send)
- Client list management
- Pricing or offer content without approval
- Accessing client subscriber data directly

**ESCALATES TO:**
- Guan Yuan: Content quality concerns
- Gabriel: Strategic content direction
- Sonny: Technical delivery issues

**KILL SWITCH:** Disable draft generation → Guan Yuan writes newsletters manually (pre-factory baseline)

**ERROR HANDLING:**
- Voice mismatch detected (quality score <6/10): Auto-reject draft, log issue, alert Guan Yuan
- Beehiiv API failure: Save draft locally, alert for manual upload
- Missing source material: Generate partial draft with "[NEEDS INPUT]" flags, don't fabricate content

**KNOWLEDGE BASE:**
- business/newsletters/playbooks/ (frameworks)
- business/newsletters/swipe-files/ (examples)
- Client voice documents (per client)
- Beehiiv API (scheduled sends)
- GHL (Salesable) integration

**HUMAN GATES:**
- All sends: Guan Yuan approves content
- Promotional content: Gabriel approves offer
- New client voice: Client approves tone

---

### CONTENT AGENT — Social Media Production

**Classification:** AI Agent (Sonnet 4)
**Status:** Deploy Phase 2 (Sandbox Week 3-4)
**Reports to:** Guan Yuan (Content Specialist)

**OWNS:**
- Social media post drafting
- Content scheduling (queued, not auto-posted)
- Platform-specific formatting
- Hashtag and caption optimization
- Repurposing long-form to short-form

**DELIVERS:**
- Draft social posts (queued for review)
- Content calendar (1-2 weeks ahead)
- Engagement reports
- Trend-aligned content suggestions

**CANNOT TOUCH:**
- Publishing without human approval
- Responding to comments/DMs
- Managing ad creative (separate agent)
- Accessing private client social accounts

**ESCALATES TO:**
- Guan Yuan: Content quality, brand voice
- Gabriel: Strategic content themes
- Claire: Community engagement follow-ups

**KILL SWITCH:** Disable batch generation → Guan Yuan/Claire resume manual content creation

**KNOWLEDGE BASE:**
- business/content/playbooks/ (frameworks)
- business/content/swipe-files/ (examples)
- Client brand guidelines
- Platform best practices

**HUMAN GATES:**
- All posts: Guan Yuan or Claire approves before publish
- Controversial topics: Gabriel approves
- Client-facing posts: Client approves

---

### QA AGENT — Pre-Flight Checks

**Classification:** AI Agent (Haiku 4 — fast, cheap)
**Status:** Deploy Phase 2 (Sandbox Week 1-2)
**Reports to:** Jenyvieve (Head of Systems)

**OWNS:**
- Pre-send email checks (dates, times, links, tokens)
- Pre-launch funnel checks (broken links, form validation)
- Automation trigger validation
- Typo and grammar scanning
- Compliance checklist verification

**DELIVERS:**
- Pass/fail QA reports
- Issue lists with specific locations
- Fix recommendations
- QA completion certificates

**CANNOT TOUCH:**
- Fixing issues directly (flags only)
- Approving launches
- Accessing production without review mode

**ESCALATES TO:**
- Jenyvieve: Systemic QA issues
- Owning agent: Specific fixes needed
- Sonny: Cross-agent QA patterns

**KILL SWITCH:** Disable QA checks → Jenyvieve runs manual checklists

**ERROR HANDLING:**
- Link checker timeout: Mark link as "UNVERIFIED" (not "pass"), flag for manual check
- False positive rate tracking: If >20% of flagged issues are false positives, alert Fordyce to retune prompts

**KNOWLEDGE BASE:**
- QA checklists (per deliverable type)
- Common error patterns
- Client-specific requirements

**HUMAN GATES:**
- Launch approval: Always human after QA pass
- QA bypass: Gabriel only (emergency)

---

### REPORTING AGENT — Client Reports

**Classification:** AI Agent (Sonnet 4)
**Status:** Deploy Sandbox Week 5-6
**Reports to:** Christine (Client Success)

**OWNS:**
- Generating weekly/monthly client reports
- Pulling data from Meta Ads, Google Analytics, CRM
- Creating performance summaries
- Trend identification and insights
- Action recommendations

**DELIVERS:**
- Draft client reports (queued for review)
- Performance dashboards
- Anomaly alerts
- Strategy recommendations

**CANNOT TOUCH:**
- Sending reports to clients (human sends)
- Making strategic changes based on data
- Accessing client billing information
- Client communication beyond reports

**ESCALATES TO:**
- Christine: Client relationship concerns
- Benjo: Campaign performance issues
- Gabriel: Strategic pivots needed

**KILL SWITCH:** Disable report generation crons → Christine/Benjo resume manual report creation

**ERROR HANDLING:**
- Partial data (API failure): Generate report with clear "[DATA UNAVAILABLE: source]" flags. Never fill gaps with estimates without labeling them.
- Anomalous data (>3 std dev from norm): Flag as anomaly, include in report with warning, don't auto-interpret.

**KNOWLEDGE BASE:**
- Client reporting templates
- Meta Ads API
- Google Analytics access
- Historical performance data

**HUMAN GATES:**
- All client-facing reports: Christine reviews
- Strategic recommendations: Gabriel approves
- Negative performance reports: Gabriel reviews framing

---

### SUPPORT AGENT — Salesable Customer Service

**Classification:** AI Agent (Sonnet 4)
**Status:** Deploy Sandbox Week 5-6
**Reports to:** Christine (Client Success)

**OWNS:**
- First-response to Salesable support tickets
- Common question resolution
- Documentation lookup
- Ticket categorization and routing
- FAQ generation from patterns

**DELIVERS:**
- Resolved tickets (routine questions)
- Escalated tickets (complex issues, with context)
- Support metrics (response time, resolution rate)
- FAQ updates

**CANNOT TOUCH:**
- Billing changes
- Account cancellations
- Refunds
- Technical backend fixes
- Promises about roadmap/features

**ESCALATES TO:**
- Christine: Complex customer issues
- Fordyce: Technical bugs
- Gabriel: Billing disputes over SGD $100

**KILL SWITCH:** Disable ticket intake → Christine handles all tickets manually

**ERROR HANDLING:**
- Confidence <0.7 on response: Auto-escalate to Christine instead of responding
- Repeat ticket from same customer (3+ in 7 days): Flag for human intervention, likely systemic issue

**KNOWLEDGE BASE:**
- Salesable documentation
- FAQ database
- Common issue resolutions
- Ticket history patterns

**HUMAN GATES:**
- All billing: Christine or Gabriel
- Cancellations: Gabriel
- Bug confirmations: Fordyce

---

# 5. AI DEVELOPMENT STACK

## The Force Multiplier

The Council flagged Fordyce as a "catastrophic single point of failure" — a fair concern IF he were working alone. He's not. Fordyce is a **senior developer** working with AI pair programmers that multiply his output 5-10x.

**Fordyce's Development Arsenal:**
- **Claude Code (CLI):** AI pair programmer for complex architecture, debugging, and code generation. Handles ~60% of boilerplate and integration code.
- **Codex (OpenAI):** Alternative AI coder for second opinions and different approaches. Used when Claude Code hits edge cases.
- **Cursor IDE:** AI-native IDE with inline code generation, refactoring, and test writing.
- **OpenClaw:** Agent orchestration platform (already deployed, runs Sonny)

**What This Means Practically:**
- Writing a Stripe MCP connector: 2-3 hours (vs 2-3 days without AI tools)
- Building an agent's prompt pipeline: 1-2 hours (vs 1-2 days)
- Debugging integration failures: AI tools can diagnose and suggest fixes in minutes
- Writing test suites: AI generates 80% of test cases, Fordyce reviews and adds edge cases
- Documentation: AI auto-generates from code, Fordyce reviews for accuracy

**Output Equivalence:**
- Fordyce + AI tools ≈ 3-5 traditional developers for building agents
- Fordyce + AI tools ≈ 5-10x faster iteration on prompt engineering
- This is not theoretical — this is how Sonny was built, how the Council was set up, how the current infrastructure was deployed

**Knowledge Transfer & Bus Factor Mitigation:**
- All code lives in version-controlled repos (not in Fordyce's head)
- AI coding tools can onboard a new developer to the codebase in hours (feed it the repo, it explains everything)
- Agent configurations are declarative (role cards + prompts + cron schedules) — not complex custom code
- OpenClaw's architecture means most agents are prompt configurations, not software engineering
- Worst case (Fordyce unavailable): Gabriel + Claude Code can maintain existing agents and do emergency fixes. Building NEW agents would slow down but the factory wouldn't stop.

**Timeline Implications:**
- Phase 1 (Foundation): 2 weeks, not 3 — AI tools compress build time
- Phase 2 (Content Pipeline): 2 weeks, not 4 — prompt iteration is fast with AI
- Full sandbox: 8 weeks total (vs 16 weeks estimated without AI tools)

---

# 6. STATION ARCHITECTURE

## The Coordination Problem

From @jumperz: "Agent swarms are a COORDINATION problem, not a technical one. Who decides which agent gets which task? How do they avoid duplicate work? How do they hand off tasks? How does the human monitor and review?"

Solution: **Structured channels as stations.** Each station has:
- A purpose (what work happens here)
- An owner (who's accountable)
- Clear inputs (what comes in)
- Clear outputs (what goes out)
- Visibility (humans can see everything)

## Channel Map (Slack/Discord)

### Category: COMMAND CENTER

**#daily-standup**
- Purpose: Morning sync, priorities, blockers
- Owner: Sonny
- Frequency: Daily 8 AM
- Format: Agent status → human priorities → today's focus

**#alerts**
- Purpose: Critical issues requiring immediate attention
- Owner: Sonny (monitors), humans (respond)
- Trigger: Anomalies, failures, urgent client issues
- Rule: Only genuine alerts. Noise = ignored channel.

**#decisions**
- Purpose: Decisions requiring human judgment
- Owner: Gabriel/Zoey
- Format: Context → options → recommendation → await approval
- Rule: No decisions made without logging here

### Category: REVENUE OPERATIONS

**#new-clients**
- Purpose: Onboarding pipeline
- Owner: Christine
- Flow: Lead qualified → brief created → setup initiated
- Agents: Sonny (brief generation), QA Agent (onboarding checklist)

**#active-clients**
- Purpose: Ongoing client work coordination
- Owner: Christine
- Sub-threads: Per-client threads for specific work
- Agents: Reporting Agent, Content Agent (client-specific)

**#media-buying**
- Purpose: Ad campaign operations
- Owner: Benjo
- Flow: Brief → creative → launch → optimize
- Agents: Media Buyer (daily reports, optimization)

**#client-delivery**
- Purpose: Deliverable review and approval
- Owner: Guan Yuan
- Flow: Draft → QA → human review → client delivery
- Agents: QA Agent (pre-flight), relevant production agents

### Category: CONTENT FACTORY

**#content-pipeline**
- Purpose: Content production workflow
- Owner: Guan Yuan
- Flow: Brief → draft → review → schedule → publish
- Agents: Newsletter Agent, Content Agent

**#creative-review**
- Purpose: Visual/video content review
- Owner: Jimmy
- Flow: Brief → concept → draft → review → final
- Humans: Jimmy, Kevin (editing)

### Category: BACK OFFICE

**#finance**
- Purpose: Financial operations
- Owner: Zoey
- Content: P&L reports, invoice tracking, cash flow
- Agents: Finance Bot (weekly reports)

**#systems**
- Purpose: Technical operations
- Owner: Jenyvieve
- Content: Integrations, automations, technical issues
- Agents: Fordyce coordinates

**#security**
- Purpose: Security and compliance
- Owner: Fordyce
- Content: Audits, access reviews, offboarding
- Agents: Security Agent (reports)

### Category: KNOWLEDGE

**#sops**
- Purpose: Standard operating procedures
- Owner: Guilbert
- Content: Process documentation, updates
- Agents: Memory Agent (captures decisions)

**#learnings**
- Purpose: Post-mortems, insights, improvements
- Owner: Sonny
- Content: What worked, what didn't, what to change
- Agents: Memory Agent (stores lessons)

### Category: AI OPERATIONS

**#agent-logs**
- Purpose: Agent activity transparency
- Owner: Fordyce
- Content: What agents are doing, decisions made
- Visibility: Full audit trail

**#agent-council**
- Purpose: Multi-AI review sessions
- Owner: Sonny
- Content: Council deliberations on complex decisions
- Format: Question → individual responses → synthesis

---

# 7. RACI MATRIX

## Key Processes

### Client Onboarding
- **R (Responsible):** Christine (drives the process)
- **A (Accountable):** Gabriel (client relationships)
- **C (Consulted):** Fordyce (technical setup), Jenyvieve (systems)
- **I (Informed):** Sonny (coordinates), QA Agent (validates)

### Ad Campaign Launch
- **R:** Benjo (executes launch)
- **A:** Gabriel (approves spend)
- **C:** Media Buyer Agent (recommends), QA Agent (pre-flight)
- **I:** Christine (client comms), Sonny (logs)

### Newsletter Production
- **R:** Newsletter Agent (drafts), Guan Yuan (reviews)
- **A:** Guan Yuan (quality gate)
- **C:** Gabriel (strategic direction)
- **I:** Christine (client awareness), Memory Agent (captures learnings)

### Weekly P&L Report
- **R:** Finance Bot (generates)
- **A:** Zoey (reviews and acts)
- **C:** Gabriel (strategic decisions from data)
- **I:** Sonny (flags anomalies)

### Client Reporting
- **R:** Reporting Agent (generates), Christine (reviews)
- **A:** Christine (client relationship)
- **C:** Benjo (campaign context), Gabriel (strategic framing)
- **I:** Sonny (logs)

### Agent Deployment (New Agent)
- **R:** Fordyce (builds and deploys)
- **A:** Gabriel (approves go-live)
- **C:** Sonny (coordination design), relevant human owner
- **I:** Full team (via #agent-logs)

### Security Audit
- **R:** Security Agent (runs audit)
- **A:** Fordyce (technical), Gabriel (policy)
- **C:** Zoey (legal/compliance)
- **I:** All agent owners (findings)

### Client Offboarding
- **R:** Christine (relationship), Security Agent (data cleanup)
- **A:** Gabriel (final sign-off)
- **C:** Fordyce (technical cleanup), Zoey (financial close-out)
- **I:** Sonny (logs), Memory Agent (archives knowledge)

### Incident Response (Agent Failure)
- **R:** Fordyce (diagnoses and fixes)
- **A:** Gabriel (decides rollback vs fix-forward)
- **C:** Affected agent's human owner
- **I:** Full team (via #alerts)

### SOP Creation
- **R:** Sonny (drafts), Guilbert (reviews)
- **A:** Guilbert (process owner)
- **C:** Process subject matter expert
- **I:** Full team (via #sops)

---

# 8. WORKFLOW MAPS

## 8A. NEW CLIENT ONBOARDING

### Overview
- **Duration:** 5-7 business days
- **Human time:** ~3 hours total
- **AI time:** ~8 hours equivalent
- **Quality gates:** 4 human checkpoints

### Step-by-Step Flow

**STEP 1: Lead Qualification (Human)**
- Actor: Christine
- Action: Confirms lead is qualified, payment received
- Output: Lead record marked "Ready for Onboarding"
- Posts to: #new-clients

**STEP 2: Brief Generation (AI + Human)**
- Actor: Sonny
- Inputs: Client contract/proposal, intake form responses, sales call notes
- Action: Generates Client Onboarding Brief
- Output: Comprehensive brief (business context, services, contacts, goals, timeline, requirements)
- Human gate: Christine reviews, adds context

**STEP 3: Client Folder Setup (AI)**
- Actor: Sonny
- Action: Creates client folder structure:
  - business/clients/{client-name}/brief.md
  - business/clients/{client-name}/voice.md
  - business/clients/{client-name}/contacts.md
  - business/clients/{client-name}/campaigns/
  - business/clients/{client-name}/content/
  - business/clients/{client-name}/reports/
- No human gate (routine)

**STEP 4: Systems Setup (AI + Human)**
- Actor: Jenyvieve + relevant agents
- Actions: Create GHL sub-account (human), configure integrations (human), set up tracking pixels (human), create reporting dashboard template (AI), add to monitoring systems (AI)
- Human gate: Jenyvieve confirms all systems live

**STEP 5: QA Pre-Flight (AI)**
- Actor: QA Agent
- Action: Runs onboarding checklist (folder exists, brief complete, GHL created, tracking installed, reporting access, contacts documented, communication preferences)
- Human gate: Christine reviews any failures

**STEP 6: Kickoff Call (Human)**
- Actor: Christine + Gabriel (if strategic client)
- Output: Call notes posted to client thread
- Memory Agent: Stores client preferences from call

**STEP 7: Onboarding Complete (Human)**
- Actor: Christine marks complete, posts summary to #new-clients

---

## 8B. AD CAMPAIGN CREATION (65+ Scripts/Week)

### Overview
- **Target output:** 65+ ad scripts per week
- **Human time:** ~5 hours/week (review only)
- **AI time:** Bulk of production
- **Quality gates:** Creative review, final approval

### Step-by-Step Flow

**STEP 1: Campaign Brief (Human)** — Benjo or Gabriel creates brief with client/product, target audience, offer/angle, hooks (3-5), reference ads

**STEP 2: Script Generation (AI)** — Content Agent generates 20-30 script variations per brief using CIE framework

**STEP 3: Peer Review (AI — Council Pattern)** — Second AI instance scores scripts on hook strength, logic flow, CTA clarity, voice match (threshold: 28/40)

**STEP 4: Human Creative Review (Human)** — Guan Yuan or Jimmy selects 10-15 scripts for production

**STEP 5: Asset Production (AI + Human)** — Jimmy (video), AI (static), UGC scripts to creators

**STEP 6: QA Pre-Launch (AI)** — QA Agent checks branding, copy, CTAs, tracking parameters

**STEP 7: Campaign Launch (Human)** — Benjo uploads, sets targeting/budget/schedule

**STEP 8: Optimization (AI)** — Media Buyer Agent daily monitoring, reports to #media-buying

---

## 8C. CONTENT PRODUCTION & DISTRIBUTION

### Newsletter Flow
1. Theme Selection (Human + AI) → #content-pipeline
2. Draft Generation (AI — Newsletter Agent)
3. Review & Edit (Human — Guan Yuan)
4. QA Pre-Send (AI — QA Agent)
5. Schedule & Send (Human — Guan Yuan)
6. Performance Tracking (AI — Newsletter Agent)

### Social Media Flow
1. Content Calendar (Human + AI)
2. Batch Generation (AI — Content Agent)
3. Review & Queue (Human — Guan Yuan or Claire)
4. Publish (Scheduled/Manual)
5. Engagement (Human — Claire)

---

## 8D. CLIENT REPORTING & AUDITS

### Weekly Report Flow
1. Data Collection (AI — Reporting Agent pulls Meta, GA, CRM)
2. Report Generation (AI — structured report with insights)
3. Review & Contextualize (Human — Christine or Benjo)
4. Client Delivery (Human — Christine sends)

### Monthly Audit Flow
1. Deep Data Pull (AI — 30-day comprehensive)
2. Audit Analysis (AI — Council Pattern, multiple perspectives)
3. Strategy Recommendations (AI + Human — Sonny generates, Gabriel decides)
4. Client Strategy Call (Human — Gabriel or Christine)

---

## 8E. FINANCIAL OPERATIONS

### Weekly P&L Flow
1. Data Pull (AI — Finance Bot, Stripe + Xero, every Monday 6 AM)
2. Report Generation (AI — posted to #finance)
3. Review & Action (Human — Zoey)

### Invoice Management Flow
1. Invoice Tracking (AI — Finance Bot monitors, alerts overdue)
2. Follow-up Generation (AI — Sonny drafts after 7 days overdue)
3. Follow-up Send (Human — Zoey or Christine)
4. Escalation (Human — Gabriel for >30 days overdue)

### Cash Flow Forecasting
1. Projection (AI — 30/60/90 day forecast)
2. Alert Thresholds (AI — Yellow <90 days, Orange <60 days, Red <30 days)
3. Action Planning (Human — Gabriel + Zoey)

---

## 8F. KNOWLEDGE CAPTURE & SOPs

### Real-Time Knowledge Capture Flow
1. Decision Made (Human — in any channel)
2. Capture Evaluation (AI — Memory Agent evaluates: preference? decision? fact? lesson?)
3. Store Decision (AI or Human — low confidence: "needs-review" tag; high confidence: direct store)
4. Deduplication (AI — Memory Agent checks for existing)

### SOP Creation Flow
1. Process Identified (Human or AI)
2. Draft SOP (AI — Sonny)
3. Review & Refine (Human — Guilbert + process owner)
4. Publish & Index (AI — Sonny saves, updates QMD, announces in #sops)

### Knowledge Audit (Monthly)
1. Memory Agent reviews all memories for staleness, contradictions, gaps
2. Audit report generated
3. Gabriel reviews flagged items, approves cleanup

---

# 9. MEMORY ARCHITECTURE

## Three-Tier Memory System

### Tier 1: Working Memory (Session)
- **Scope:** Current conversation context
- **Persistence:** Session only (disposable)
- **Size:** Token window (~200K for Opus)

### Tier 2: QMD Short-Term Memory (Days to Weeks)
- **Scope:** Local workspace files
- **Persistence:** Files until deleted
- **Structure:**
  - memory/YYYY-MM-DD.md (daily logs)
  - business/clients/ (client-specific knowledge)
  - business/ads/playbooks/ (ad frameworks)
  - business/content/playbooks/ (content frameworks)
  - business/operations/ (SOPs)

### Tier 3: SuperMemory Long-Term (Permanent)
- **Scope:** Curated, high-signal facts
- **Categories:** preference, fact, decision, entity, lesson
- **Configuration:** containerTag: sonny_v3, autoCapture: OFF, autoRecall: ON

## Memory Quality Rules

- 1.0 confidence: Gabriel explicitly stated, unlikely to change
- 0.8: Gabriel implied strongly, probably stable
- 0.6: Inferred from behavior, may need confirmation
- 0.4: Uncertain, stored for pattern matching
- <0.4: Don't store

**Memory Influence Rate:** ~30% (from @Voxyz_ai — balances learned context vs exploring new approaches)

---

# 10. SECURITY ARCHITECTURE

## Client Data Isolation
- Separate folders per client: business/clients/{client}/
- Separate GHL sub-accounts per client
- Separate ad accounts per client
- No shared credentials between clients
- Security Agent monthly verification audit

## Credential Management
- All credentials in LastPass (except OAuth)
- Named: {service}-{account}-{purpose}
- Rotation: Quarterly for sensitive, annual for others
- No credentials in code, config files, or chat

## PDPA Compliance
- Consent documented for data collection
- Purpose limitation enforced
- Retention limits respected
- Access/correction/withdrawal requests supported
- Security Agent maintains data inventory

## Client Offboarding Checklist
- [ ] Final deliverables transferred
- [ ] Client access revoked
- [ ] Client data archived (retention period)
- [ ] Data isolated from active workspace
- [ ] Post-retention deletion scheduled
- [ ] Offboarding certificate generated

## Access Control Principles
- Least privilege: Agents get minimum access needed
- Sonny: Read all client data, read finance summaries, no credentials, coordinate
- Media Buyer: Own clients only, no finance, no credentials, Ads API
- Finance Bot: No client data, read all finance, no credentials, Stripe/Xero
- Security Agent: Read all (audit), audit finance, audit credentials, audit systems
- All other agents: Own clients/scope only, minimal access

## Incident Response
1. Security Agent alerts #alerts immediately
2. Fordyce assesses technical impact
3. Gabriel decides disclosure/response
4. Incident logged with root cause
5. Mitigation implemented
6. Post-mortem in #learnings

---

# 11. QUALITY ARCHITECTURE

## The Council Pattern

**When to Use:**
- Strategic decisions (significant impact)
- Creative review (taste is subjective)
- Complex analysis (multiple valid perspectives)
- Quality gates (before client delivery)

**When NOT to Use:**
- Routine tasks (over-engineering)
- Time-sensitive responses (latency)
- Clear-cut decisions (unnecessary cost)

### Council Structure

**Standard Council (3 perspectives):** Conservative, Optimistic, Synthesis

**LLM Council Tool (Strategic Decisions):**
- Chairman: Claude Opus 4.6 (synthesis)
- Member: GPT 5.2 (breadth)
- Member: Gemini 3 Pro (Google ecosystem)
- Member: Grok 4.1 Fast (contrarian)
- Location: localhost:5173

### Quality Gates by Deliverable Type

**Ad Scripts:** AI peer review → Human creative review → QA Agent → Human launch approval

**Newsletters:** AI draft quality check → Human content review → QA Agent (links, formatting) → Human send approval

**Client Reports:** AI data accuracy check → Human context review → Human tone check → Human send approval

**Financial Operations:** AI calculation verification → Human review → Dual approval for payments >SGD $500

---

# 12. COORDINATION ARCHITECTURE

## Core Concepts (adapted from @Voxyz_ai)

**Proposals → Missions → Steps → Events**
1. Request comes in (Slack, Discord, email, scheduled)
2. Sonny evaluates: valid proposal?
3. Cap Gate check: capacity/budget?
4. If approved: becomes a mission → decomposed into steps → assigned to agents → agents execute → mission complete

## Heartbeat System

**Every 5 Minutes:** Check stuck tasks, evaluate scheduled triggers, process pending reactions, recover failed tasks (retry with backoff)

**Daily (8 AM):** Generate standup summary, flag overdue items, post to #daily-standup

**Weekly (Monday 6 AM):** Trigger Finance Bot P&L, trigger performance summaries, check SOP gaps

## Trigger System
- **Reactive:** Event happens → Agent responds
- **Proactive:** Schedule reached → Agent initiates
- **Skip Probability + Jitter:** 10-20% skip on non-critical, ±30 min jitter (critical tasks always fire)

---

# 13. TECHNICAL IMPLEMENTATION

## What Already Exists

**Infrastructure:** Mac mini (always-on), OpenClaw (agent orchestration), SuperMemory (long-term memory), QMD (local file indexing)

**Model Access:** Claude Opus 4.6, Claude Sonnet 4, Claude Haiku 4, LLM Council tool (localhost:5173)

**API Integrations:** Stripe, Xero, GHL/Salesable, Meta Ads, Google Workspace, Beehiiv

**Communication:** Discord (Sonny), Slack (team)

## What to Build (AI-Augmented Timeline)

**Sandbox Weeks 1-2 (Foundation):**
- Media Buyer Agent (Meta Ads API read + limited write, daily monitoring cron, reporting)
- Finance Bot (extend Stripe/Xero MCP, weekly P&L cron)
- QA Agent (link checker, format validator, checklist runner)
- Estimated build time: 2 weeks (Fordyce + Claude Code)

**Sandbox Weeks 3-4 (Content Pipeline):**
- Security Agent (audit scripts, credential tracker, offboarding automation)
- Memory Agent (SuperMemory curation logic, evaluation prompts, monthly audit)
- Newsletter Agent (Beehiiv API integration, draft pipeline)
- Content Agent (social platform integrations, batch generation, scheduling queue)
- Estimated build time: 2 weeks (most work is prompt engineering, fast with AI tools)

**Sandbox Weeks 5-6 (Full Pipeline):**
- Reporting Agent (multi-source data aggregation, report templates)
- Support Agent (ticket intake, knowledge base search, escalation routing)
- Estimated build time: 2 weeks

**Sandbox Weeks 7-8 (Graduation):**
- Full pipeline validation
- Metrics collection and graduation assessment
- Rollback drill
- No new builds — focus on tuning and proving

## Technical Implementation Details

### Authentication & Authorization Model

**API Credentials:**
- All stored in LastPass, retrieved at runtime via lpass CLI
- Per-agent credential scoping: each agent only has credentials for its required APIs
- Read-only by default; write access explicitly granted per role card
- Credential format: environment variables injected at agent startup

**Agent Identity:**
- Each agent runs as a named OpenClaw session
- Session logs tagged with agent name for audit trail
- No agent can impersonate another agent's session

### Data Schemas

**Client Data Structure (per client):**
- brief.md: Onboarding brief (markdown, human-readable)
- voice.md: Brand voice document (markdown)
- contacts.md: Key contacts (structured markdown: name, role, email, phone, preferences)
- campaigns/: Ad campaign files (brief.md per campaign, performance snapshots)
- content/: Content deliverables (drafts, approved, published)
- reports/: Generated reports (weekly/, monthly/)

**Agent Output Schema (standard for all agents):**
- Header: agent_name, timestamp, task_id, confidence_score
- Body: The deliverable content
- Footer: human_gate_required (bool), escalation_needed (bool), next_action

**Memory Entry Schema:**
- category: preference | fact | decision | entity | lesson
- content: The memory text
- confidence: 0.0-1.0
- source: Who/what generated this
- timestamp: When captured
- tags: Searchable tags
- review_status: confirmed | needs-review | stale

### Error Handling Patterns

**Standard Retry Pattern (all agents):**
- Attempt 1: Immediate
- Attempt 2: Wait 5 seconds
- Attempt 3: Wait 15 seconds
- Attempt 4: Wait 45 seconds
- After 4 failures: Log error, post to #alerts, skip task, alert human owner
- Never retry infinitely. Never retry destructive operations.

**Graceful Degradation:**
- If non-critical agent fails: Other agents continue. Failed agent's work queued for human.
- If critical agent fails (Finance Bot, Media Buyer): Alert #alerts immediately. Human owner takes over within 1 hour.
- If multiple agents fail simultaneously: Trigger system-wide rollback assessment.

**Error Classification:**
- **Transient:** API timeout, rate limit → auto-retry with backoff
- **Recoverable:** Bad input data → flag for human, skip task
- **Critical:** Auth failure, data corruption → immediate alert, stop agent, human intervention

### Monitoring & Observability

**Agent Health Dashboard (posted to #agent-logs daily):**
- Per agent: tasks completed, tasks failed, average completion time, error rate
- System: total API cost (rolling 24h), total tasks processed, queue depth

**Alert Thresholds:**
- Agent error rate >20% in 1 hour → Yellow alert
- Agent error rate >50% in 1 hour → Red alert, auto-disable agent
- API cost >SGD $50 in 24h (any single agent) → Cost alert
- Task queue depth >20 unprocessed → Capacity alert
- Agent unresponsive for >30 minutes → Health alert

**Logging:**
- All agent actions logged to #agent-logs (structured: timestamp, agent, action, result)
- Error details logged with full context (input, error type, stack trace if applicable)
- Logs retained 90 days, then archived
- Sensitive data (client PII, credentials) NEVER logged

**Weekly Observability Report (auto-generated, posted to #systems):**
- Agent uptime percentages
- Error patterns and trends
- API cost breakdown by agent
- Performance bottlenecks identified
- Recommendations for tuning

## What to Buy

**Already Have (No New Cost):** OpenClaw, SuperMemory, Mac mini, most API connections

**New/Increased Costs:**
- OpenRouter API: SGD $300-500/mo (increased from current)
- Potential new SaaS: SGD $100-200/mo
- Buffer for experiments: SGD $200/mo
- **Total new infrastructure: ~SGD $500-700/mo**

---

# 14. MIGRATION PLAN (Current Tooling → Digital Factory)

## Current State Inventory

**Communication:** Slack (team), Discord (Sonny), Email, WhatsApp (some client comms)
**Project Management:** Ad hoc (Slack threads, Google Docs)
**Finance:** Xero (accounting), Stripe (payments), manual spreadsheets (P&L)
**CRM:** GHL/Salesable
**Content:** Manual creation in Google Docs, Canva
**Ads:** Manual management in Meta Ads Manager, Google Ads
**Newsletters:** Beehiiv (Uncrowded Strategies), GHL (Gab's Edge)
**Reporting:** Manual (Google Sheets/Slides)

## Migration Approach

**Keep As-Is (no change):**
- Slack, Discord, Email — these become the station layer
- Xero, Stripe — agents read from these, don't replace them
- GHL/Salesable — core CRM stays, agents integrate with it
- Beehiiv — newsletter platform stays, agents draft for it

**Augment (add AI layer on top):**
- Meta Ads → Media Buyer Agent monitors and recommends via API
- Google Sheets P&L → Finance Bot auto-generates from Stripe/Xero
- Manual content creation → Newsletter/Content Agents draft, humans review
- Manual reporting → Reporting Agent generates from data sources

**Replace (human process → AI process):**
- Manual daily ad monitoring → Media Buyer Agent daily cron
- Manual invoice tracking → Finance Bot auto-monitoring
- Manual QA checklists → QA Agent automated checks
- Manual support ticket triage → Support Agent first-response

**Migration Sequence:**
1. Document current manual process as SOP (rollback target)
2. Deploy agent in shadow mode (runs alongside human)
3. Compare outputs for 1-2 weeks
4. If quality matches: Agent becomes primary, human becomes reviewer
5. If quality doesn't match: Iterate prompts, extend shadow period

---

# 15. HUMAN TRANSITION PLAN

## Current State → Target State

**Current (Feb 2026): 12 People, SGD $21,015/mo**
- Jimmy Ng — Creative Director — SGD $7,000
- Fordyce Gozali — Senior AI Engineer — SGD $2,083
- Guan Yuan Pok — Content Specialist — SGD $1,912
- Benjo Magcalen — Production Lead — SGD $1,862
- Guilbert Codog — People & Systems — SGD $1,303
- Christine Ybanez — Client Success — SGD $1,234
- Jenyvieve Sarmiento — Head of Systems — SGD $1,234
- Mirielle Grabato — Automations — SGD $1,047
- Kevin Kaye Gaudier — Editor — SGD $937
- Claire Castillon — Content Coordinator — SGD $885
- Joenel Masculino — Media Buyer (PT) — SGD $768
- Shirath Muhammad — Design — SGD $750

**Target (May 2026): 6 FT + 3 PT, SGD $16,628/mo**
- Jimmy Ng* — Creative Director — FT — SGD $7,000
- Fordyce Gozali — Senior AI Engineer — FT — SGD $2,083
- Guilbert Codog — People & Systems Lead — FT — SGD $1,303
- Jenyvieve Sarmiento — Head of Systems — FT — SGD $1,234
- Guan Yuan Pok — AI Content Specialist — PT — SGD $1,912
- Benjo Magcalen — Production Lead — PT — SGD $1,862
- Christine Ybanez — Client Success — PT — SGD $1,234

*Jimmy on probation — if replaced with junior videographer (~SGD $2-3K): total drops to ~SGD $12,628*

**Monthly Savings: SGD $4,387/mo** (SGD $21,015 → SGD $16,628)
**If Jimmy replaced: SGD $8,387/mo** savings

## Transition Timeline

**Feb 28, 2026: Joenel Exits**
- Savings: SGD $768/mo
- Replacement: Media Buyer Agent
- Transition: Benjo absorbs oversight role

**Mar 10, 2026: Jimmy Review**
- Decision: Continue at SGD $7K or replace
- Criteria: Creative output with AI tools

**Mar 31, 2026: Shirath to Project-Based**
- Savings: SGD $750/mo → project fees only
- Replacement: AI design tools + Jimmy for complex

**Apr 30, 2026: Mirielle Exits**
- Savings: SGD $1,047/mo
- Replacement: Fordyce absorbs N8N work, AI handles rest

## Transition Support
- 2-week notice minimum
- Clear communication about AI transition
- References for future roles
- Role clarity sessions for remaining team
- AI tool training for everyone staying

---

# 16. FOUR-PHASE ROLLOUT (Sandbox-First)

## Phase 1: Sandbox Foundation (Weeks 1-2)

**Focus:** Build foundation agents, start sandbox on Ascend's own marketing

**Agents Deployed (shadow mode):**
- Media Buyer Agent
- Finance Bot
- QA Agent

**Success Criteria:**
- All 3 agents producing outputs in shadow mode
- Outputs compared against human baseline
- Zero integration failures for 3 consecutive days
- Rollback procedures tested

## Phase 2: Sandbox Content Pipeline (Weeks 3-4)

**Focus:** Content production agents, expand sandbox

**Agents Deployed (shadow mode):**
- Security Agent
- Memory Agent
- Newsletter Agent
- Content Agent

**Human Changes:**
- Joenel exit (Feb 28)
- Jimmy review (Mar 10)
- Shirath notification

**Success Criteria:**
- All 7 agents operational in sandbox
- Newsletter drafts scoring ≥7/10 quality
- Content drafts scoring ≥7/10 quality
- QA Agent catching errors humans would catch

## Phase 3: Sandbox Full Pipeline (Weeks 5-6)

**Focus:** Complete agent roster, full sandbox pipeline

**Agents Deployed:**
- Reporting Agent
- Support Agent

**Success Criteria:**
- All 9+ agents operational
- Full end-to-end pipeline running for sandbox project
- Client report quality matching human baseline
- Support Agent resolving >30% of test tickets

## Phase 4: Sandbox Graduation & Rollout (Weeks 7-8)

**Focus:** Prove the factory, begin client rollout

**Activities:**
- 2-week full-autonomy test (AI primary, human reviewer)
- Graduation assessment against all criteria
- If pass: Begin Client 1 rollout
- If fail: Identify gaps, iterate, extend sandbox 2 weeks

**Graduation Criteria:**
- [ ] Quality ≥7/10 average across all deliverable types
- [ ] Zero critical errors in 2-week autonomy test
- [ ] Human review time <30% of pre-factory baseline
- [ ] All agents stable (no unplanned downtime >4 hours)
- [ ] Rollback tested and confirmed
- [ ] All manual SOPs documented (rollback targets)
- [ ] Monitoring/alerting functional

**Post-Graduation Rollout:**
- Weeks 9-10: Client 1 (lowest risk)
- Weeks 11-12: Clients 2-3
- Weeks 13-16: Remaining clients
- Ongoing: Optimization and tuning

---

# 17. COST MODEL

## Current Monthly Costs
- Team Payroll: SGD $21,015 (12 people)
- Overhead (rent, software, other): ~SGD $15,000
- **Total Operating: ~SGD $36,015/mo**

## Target Monthly Costs (Post-Rollout)
- Team Payroll: SGD $16,628 (6 FT + 3 PT)
- AI Agents: SGD $1,500-2,000
- Software: SGD $5,000-5,500
- Other Overhead: SGD $9,500
- **Total Operating: ~SGD $32,628-34,128/mo**

**Monthly Savings: SGD $2,000-3,400/mo**
**If Jimmy replaced: Additional SGD $4-5K → Total SGD $6-8K/mo savings**

## Cost Per Unit of Work

**Before AI Factory:**
- Ad script: ~SGD $50 (human time)
- Newsletter: ~SGD $150 (human time)
- Client report: ~SGD $100 (human time)

**After AI Factory:**
- Ad script: ~SGD $5 (AI + review time)
- Newsletter: ~SGD $30 (AI + review time)
- Client report: ~SGD $20 (AI + review time)

**Efficiency Gain: 5-10x per deliverable**

## Break-Even Analysis

**Current break-even:**
- Operating: SGD $36,015 + Loan: SGD $5,593 + G+Z pay: SGD $9,000 = **SGD $50,608/mo needed**
- Current revenue: SGD $40,532 → Gap: -SGD $10,076/mo

**Target state break-even:**
- Operating: SGD $32,628 + Loan: SGD $5,593 + G+Z pay: SGD $9,000 = **SGD $47,221/mo needed**
- Gap shrinks to: -SGD $6,689/mo

**Post-loan break-even (mid-2027):**
- Operating: SGD $32,628 + G+Z pay: SGD $9,000 = **SGD $41,628/mo needed**
- Current revenue: SGD $40,532 → Gap: -SGD $1,096/mo (nearly break-even)

*Note: Revenue growth strategy is handled in a separate Revenue Playbook. This document's job is to minimize the operating cost denominator.*

---

# 18. RISK REGISTER

## Technical Risks

**RISK: Agent Hallucination**
- Probability: Medium | Impact: High (client-facing errors)
- Mitigation: Council pattern, human gates, QA Agent, confidence thresholds
- Rollback: Disable agent, human resumes task
- Owner: Fordyce

**RISK: API Outages (Stripe, Meta, Xero, LLM providers)**
- Probability: Low-Medium | Impact: Medium (temporary disruption)
- Mitigation: Retry with exponential backoff (4 attempts), graceful degradation (partial reports with flags), multi-model fallback for LLM calls
- Rollback: Manual operations for affected workflow
- Owner: Fordyce

**RISK: Data Leakage / Cross-Client Contamination**
- Probability: Low | Impact: Critical (client trust, legal)
- Mitigation: Security Agent audits, folder isolation, per-agent credential scoping, audit logging
- Rollback: Isolate affected agent, security review, client notification if confirmed
- Owner: Fordyce + Gabriel

**RISK: Prompt Injection / Adversarial Input**
- Probability: Low | Impact: High
- Mitigation: Input sanitization, constraint boundaries in role cards, agents never execute external instructions
- Rollback: Disable affected agent, review all recent outputs
- Owner: Fordyce

## Operational Risks

**RISK: Fordyce Unavailability (illness, departure)**
- Probability: Low-Medium | Impact: High
- Mitigation:
  - All code in version-controlled repos
  - Agent configs are declarative (prompts + crons), not complex code
  - AI coding tools (Claude Code) can onboard a replacement developer quickly
  - Gabriel + Claude Code can maintain existing agents for emergency fixes
  - Documentation maintained as part of build process
- Owner: Gabriel (contingency planning)

**RISK: Quality Degradation / Review Fatigue**
- Probability: Medium | Impact: High (client churn)
- Mitigation: Council pattern for peer review, QA Agent pre-filtering, quality score tracking, rotating reviewer schedules, alert if review time drops below threshold (suggests rubber-stamping)
- Owner: Guan Yuan + Christine

**RISK: Team Morale During Transition**
- Probability: Medium | Impact: Medium
- Mitigation: Clear communication, role clarity, growth paths for remaining team, transition support for exiting team
- Owner: Guilbert + Gabriel

## Sandbox-Specific Transition Risks

**RISK: Sandbox Takes Longer Than 8 Weeks**
- Probability: Medium | Impact: Low (delays rollout, not catastrophic)
- Mitigation: 2-week extension buffer built in. If still not graduating at week 10, reassess specific failing agents rather than entire system.
- Owner: Fordyce + Gabriel

**RISK: Agent Quality Plateaus Below Threshold**
- Probability: Low-Medium | Impact: Medium
- Mitigation: Identify specific failure modes. Options: retune prompts, change model tier (Haiku → Sonnet → Opus), restructure agent scope, accept human-assisted mode for that workflow.
- Trigger: Quality score stuck below 7/10 for 2+ weeks despite prompt iteration.
- Owner: Fordyce

**RISK: Shadow Mode Reveals AI Can't Match Human Quality for Specific Tasks**
- Probability: Medium | Impact: Low (just means that task stays human)
- Mitigation: Not every task needs to be AI-automated. Identify which tasks AI does well (80% rule) and keep humans on the rest. The factory still saves time even at 60% automation.
- Owner: Gabriel (strategic decision)

**RISK: Client Notices Quality Shift During Rollout**
- Probability: Low-Medium | Impact: High (trust)
- Mitigation: Start with most tolerant client, human reviews remain mandatory, collect client feedback actively during first 2 weeks of rollout. If client raises concerns, immediately revert that client to manual.
- Owner: Christine + Gabriel

## Financial Risks

**RISK: API Costs Exceed Budget**
- Probability: Low | Impact: Medium
- Mitigation: Per-agent cost caps, cost alerts at SGD $50/agent/day, model tier optimization (use Haiku where possible)
- Owner: Sonny (monitoring) + Fordyce (optimization)

**RISK: Loan Pressure**
- Probability: Fixed (known schedule) | Impact: Cash flow squeeze
- Mitigation: Apply SGD $29K excess payment, accelerate payoff
- Owner: Zoey

---

# 19. SUCCESS METRICS

## Sandbox Success (End of Week 8)

**Operational:**
- [ ] All agents deployed and running on sandbox
- [ ] Full pipeline end-to-end proven
- [ ] Graduation criteria passed

**Quality:**
- [ ] Average quality score ≥7/10 across all deliverable types
- [ ] Zero critical errors in 2-week autonomy test
- [ ] QA Agent catching >80% of errors

**Efficiency:**
- [ ] Human review time <30% of pre-factory baseline
- [ ] Cycle time (brief → deliverable) reduced by ≥50%

## Post-Rollout Success (End of Month 4)

**Operational:**
- [ ] All clients on Digital Factory pipeline
- [ ] Team at target state (6 FT + 3 PT)
- [ ] All agents stable with <5% error rate

**Financial:**
- [ ] Payroll at SGD $16,628/mo or lower
- [ ] AI costs within SGD $1,500-2,000/mo budget
- [ ] Total operating costs down SGD $2,000-3,400/mo

**Quality:**
- [ ] Client satisfaction maintained or improved
- [ ] Zero major AI-caused incidents
- [ ] Team morale stable

## Long-Term Success (End of 2026)

**Operational:**
- [ ] DBS loan paid off
- [ ] Digital Factory running autonomously
- [ ] Gabriel focused on growth, not operations
- [ ] Scalable to 2-3x client load without headcount increase

**Strategic:**
- [ ] Model proven and documentable
- [ ] Potential to license/teach the system
- [ ] Ascend Group as case study for AI-native agency

---

# APPENDIX A: PROMPT LIBRARY

All prompts referenced in this document are stored in:
`business/operations/prompts/`

**Files:**
- onboarding-brief.md — Client onboarding brief generation
- onboarding-qa.md — Onboarding QA checklist
- cie-script-generation.md — CIE-powered ad script generation
- script-review.md — Script quality review (Council pattern)
- newsletter-draft.md — Newsletter draft generation
- social-post.md — Social media post generation
- weekly-report.md — Client weekly report generation
- monthly-audit.md — Client monthly audit analysis
- weekly-pl.md — Finance Bot P&L report
- memory-evaluation.md — Memory Agent storage decision
- sop-draft.md — SOP document generation

---

# APPENDIX B: CHANNEL SETUP CHECKLIST

Category: COMMAND CENTER
- [ ] #daily-standup
- [ ] #alerts
- [ ] #decisions

Category: REVENUE OPERATIONS
- [ ] #new-clients
- [ ] #active-clients
- [ ] #media-buying
- [ ] #client-delivery

Category: CONTENT FACTORY
- [ ] #content-pipeline
- [ ] #creative-review

Category: BACK OFFICE
- [ ] #finance
- [ ] #systems
- [ ] #security

Category: KNOWLEDGE
- [ ] #sops
- [ ] #learnings

Category: AI OPERATIONS
- [ ] #agent-logs
- [ ] #agent-council

---

# APPENDIX C: AGENT DEPLOYMENT CHECKLIST

Per-Agent Deployment:
- [ ] Role card documented (owns, delivers, can't touch, escalates)
- [ ] Kill switch defined and tested
- [ ] Error handling patterns implemented
- [ ] Knowledge base identified and accessible
- [ ] Prompts created and tested
- [ ] Human gates defined
- [ ] Integration/API access configured (least privilege)
- [ ] Shadow mode test completed (1-2 weeks)
- [ ] Quality compared against human baseline
- [ ] Owner assigned (human accountability)
- [ ] Monitoring configured (logs to #agent-logs)
- [ ] Escalation path tested
- [ ] Rollback procedure documented and tested
- [ ] Go-live approved by Gabriel

---

# APPENDIX D: WEEKLY RHYTHM

**Monday:**
- 6 AM: Finance Bot P&L report generated
- 8 AM: Daily standup (Sonny posts summary)
- 9 AM: Zoey reviews P&L, flags issues
- EOD: Week's priorities confirmed

**Tuesday-Thursday:**
- 8 AM: Daily standup
- Ongoing: Agents execute, humans review
- EOD: Progress logged

**Friday:**
- 8 AM: Daily standup
- 2 PM: Week retrospective
- 4 PM: Next week planning
- EOD: Weekend autopilot mode

**Ongoing:**
- Heartbeat every 5 minutes (stuck task recovery)
- Alerts as needed (genuine issues only)
- Agent logs continuous
- Weekly observability report (auto-generated)

---

# DOCUMENT HISTORY

- v1.0 — Feb 9, 2026 — Sonny W + LLM Council — Initial release
- v2.0 — Feb 9, 2026 — Sonny W + LLM Council v1.0 feedback — Major upgrade incorporating Council critique and Gabriel's directives: Sandbox Protocol added, Fordyce upgraded to Senior Dev + AI tools, revenue projections removed (out of scope), RACI matrix added, technical implementation details (auth, schemas, error handling, monitoring), kill switches per agent, migration plan, AI Development Stack section, transition risks strengthened, payroll numbers reconciled

---

*END OF DOCUMENT*

*This is a living document. Updates will be versioned and logged.*

*For questions: Contact Sonny (Discord #chief-of-staff) or Gabriel Wong.*
