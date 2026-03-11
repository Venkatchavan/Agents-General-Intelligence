# The Agency — 20 Startup Project Ideas
> 15-Day Sprint Plan · MLOps · AIOps · Mobile · SaaS  
> Version: v1.0.0 — 2026-03-11 — AGI Goal Decomposer

---

## How to Use This File

Each project follows the full **SDLC → STLC → Agile** lifecycle:
- GitHub Issues: Epics → Stories → Tasks → Bugs
- 3 sprints × ~3 days each (within 15-day window)
- CI/CD via GitHub Actions on every PR and merge
- Security gate (OWASP), Ethical Reviewer gate, and Reality Checker sign-off before launch

---

## Domain 1 — MLOps Startups

### `01` DriftSentinel — Model Drift Detection for Indie ML Devs
**The Niche:** MLflow, Evidently, Arize — all built for enterprise data teams. Solo ML developers and 2-person startups have zero affordable tooling to know when their production model goes stale.

**What it does:** Drop in a Python SDK (`pip install driftsentinel`). Logs predictions + actuals. Dashboard alerts when PSI/KL-divergence crosses thresholds. One-click rollback to previous model version.

**Stack:** FastAPI · React · PostgreSQL · Redis · Celery · Docker/K8s

**Differentiator:** $0 free tier. No YAML config files. < 5 lines of SDK code. Model-agnostic.

**Agency Agents Activated:**
- `AGI Goal Decomposer` → activation plan
- `Backend Architect` → FastAPI SDK design + metrics pipeline
- `Data Engineer` → feature/prediction logging schema
- `AI Engineer` → statistical drift algorithms (PSI, KS test, CUSUM)
- `DevOps Automator` → Docker + GitHub Actions CI/CD
- `Sprint Prioritizer` → 3 sprints × 3 days
- `Security Engineer` → SDK auth tokens, API key rotation
- `Frontend Developer` → dashboard charts

---

### `02` SilentDeploy — Blue/Green for ML Models, Not Web Services
**The Niche:** Blue/green and canary deployments exist for APIs. Nobody has productized this specifically for ML models — where "bad" means accuracy drops 3% in production, not HTTP 500s.

**What it does:** Git-style version control for trained models. Route X% of traffic to new model. Compare live accuracy vs. challenger. Auto-rollback if challenger loses.

**Stack:** FastAPI · MinIO (model artifact store) · Prometheus · Grafana · Kubernetes

**Differentiator:** Works with any ML framework. Integrates with existing MLflow/W&B experiment tracking. Accuracy-gated rollout (not just latency-gated).

**Agency Agents Activated:**
- `AI Engineer` → inference routing logic
- `Backend Architect` → model registry + traffic splitting API
- `DevOps Automator` → Helm chart, GitHub Actions pipeline
- `Database Architect` → artifact metadata + lineage schema
- `Security Engineer` → model signing & integrity verification

---

### `03` AnnotatePro — Active Learning Data Labeler
**The Niche:** Scale AI costs $15–50/hour. In-house annotation = bottomless time sink. Active learning (label only the uncertain samples) can cut annotation effort by 60–70% — but no tool makes this accessible to solo CV/NLP practitioners.

**What it does:** Upload unlabeled dataset. Train a base model. System surfaces only the 20% of samples the model is most uncertain about. You label those. Repeat. Export annotated dataset + fine-tuned model.

**Stack:** Python · FastAPI · React · PyTorch · PostgreSQL · S3 · Celery

**Differentiator:** Works with images AND text. Exports to COCO, YOLO, HuggingFace formats. Annotation effort tracker (hours saved counter).

**Agency Agents Activated:**
- `AI Engineer` → uncertainty sampling, active learning loop
- `Frontend Developer` → annotation canvas (image bbox + text span)
- `Backend Architect` → batch job orchestration
- `DevOps Automator` → GPU-based GitHub Actions runner
- `Rapid Prototyper` → first working demo in 2 days

---

## Domain 2 — AIOps Startups

### `04` RunbookAI — Incident → Runbook in < 60 Seconds
**The Niche:** 90% of engineering teams have zero runbooks. When incidents fire at 2 AM, people improvise. PagerDuty and OpsGenie give you alerts — not knowledge.

**What it does:** Connect your Slack + PagerDuty/GitHub Issues. Every time an incident is resolved, RunbookAI interviews the responder via Slack bot and auto-generates a structured runbook. Over time, builds a searchable incident knowledge base.

**Stack:** FastAPI · Next.js · PostgreSQL · OpenAI/Claude API · Slack SDK · Vector DB (Qdrant)

**Differentiator:** Zero-friction — comes to you in Slack, not a separate tool. Runbooks are versioned and queryable. "What do I do when Redis OOM?" → exact playbook.

**Agency Agents Activated:**
- `AI Engineer` → Slack NLP bot, RAG knowledge base
- `Backend Architect` → incident ingestion pipeline
- `Prompt Engineer` → few-shot runbook generation prompts
- `Frontend Developer` → runbook editor + search UI
- `Security Engineer` → Slack token scoping + webhook validation

---

### `05` AlertMesh — Multi-Cloud Alert Correlation Engine
**The Niche:** A startup using AWS + Cloudflare + Vercel + Datadog gets 400 alerts about the same database blip. Alert fatigue kills on-call rotations. Existing correlation tools (Moogsoft, Splunk ITSI) cost $50k+/year.

**What it does:** Ingests webhooks from any alerting source. Uses temporal + semantic clustering to group related alerts into single "incidents." Assigns blast radius score. Routes to right team. Sends exactly one Slack message.

**Stack:** FastAPI · Redis Streams · PostgreSQL · React · Grafana embedding · Docker

**Differentiator:** Under $99/month for teams up to 20 engineers. 5-minute setup with webhook URLs. No agents to install.

**Agency Agents Activated:**
- `AI Engineer` → alert clustering ML model
- `Backend Architect` → streaming ingestion architecture
- `DevOps Automator` → multi-source webhook handling
- `Database Architect` → time-series alert schema + indexing strategy
- `Frontend Developer` → incident grouping dashboard

---

### `06` CostSheriff — Cloud Cost Anomaly Detection
**The Niche:** AWS Cost Explorer shows you history. It does NOT proactively alert when a data pipeline misbehaves at 3 AM and accrues $4,000 in S3 PUT costs before you notice Monday morning.

**What it does:** Connects to AWS/GCP/Azure billing APIs. Trains a per-service baseline (seasonality-aware). Fires real-time alerts when costs deviate. Links anomaly → probable root culprit service/lambda/job.

**Stack:** FastAPI · Next.js · PostgreSQL · Facebook Prophet (time-series) · AWS Cost Explorer API

**Differentiator:** Causality tracing — not just "your bill spiked" but "this Lambda ran 10,000x more than usual because of this event." Pays for itself in the first incident.

**Agency Agents Activated:**
- `AI Engineer` → Prophet-based anomaly detection
- `Data Engineer` → multi-cloud billing data normalization
- `Backend Architect` → billing API polling + event pipeline
- `Sprint Prioritizer` → RICE-scored feature backlog
- `Monetization Strategist` → pricing tiers

---

### `07` ObserveML — Production Observability for LLM Apps
**The Niche:** Everyone is building RAG apps and LLM pipelines, but nobody knows if they're actually working. LangSmith is LangChain-only. Helicone is basic. No tool gives full-stack observability — latency, token costs, hallucination detection, prompt drift — in one place.

**What it does:** Drop-in Python/JS middleware. Captures every LLM call with full trace context. Dashboard shows: cost per user session, p95 latency, semantic drift between prompt versions, retrieval relevance scores.

**Stack:** FastAPI · ClickHouse (append-only logs) · React · OpenTelemetry SDK · Prometheus

**Differentiator:** Framework-agnostic (OpenAI, Anthropic, Ollama, custom). Prompt version diff viewer. "Which prompt version has the best task completion rate?"

**Agency Agents Activated:**
- `AI Engineer` → embedding-based drift detection, relevance scoring
- `Backend Architect` → OpenTelemetry ingestion pipeline
- `Database Architect` → ClickHouse schema for high-throughput trace data
- `Frontend Developer` → trace waterfall + cost analytics dashboard
- `Security Engineer` → PII scrubbing in traces before storage

---

## Domain 3 — Mobile App Startups

### `08` FieldSyncPro — Offline-First Field Service App
**The Niche:** HVAC/electrical/plumbing technicians still use paper job sheets, WhatsApp photos, and Excel. Enterprise FSM (FieldEdge, ServiceMax) costs $150+/user/month. SMB owners get nothing.

**What it does:** Flutter app. Technician gets jobs assigned, views customer history, logs parts used, captures signatures, takes photos, marks job complete. Everything syncs when they get signal. Boss sees real-time job status + auto-invoicing.

**Stack:** Flutter · Dart · SQLite (offline) · FastAPI backend · PostgreSQL · Firebase (push) · PDF generation

**Differentiator:** Works with zero internet. Sub-$15/user/month. WhatsApp-like UX simplicity.

**Agency Agents Activated:**
- `Mobile App Builder` → Flutter offline-sync architecture
- `Backend Architect` → conflict-resolution sync API
- `Database Architect` → offline schema + server reconciliation logic
- `UX Architect` → technician workflow UX (one-handed, gloves-compatible)
- `DevOps Automator` → GitHub Actions → App Store / Play Store pipeline

---

### `09` FarmVoice — Voice AI Advisory for Rural Farmers
**The Niche:** 500M+ smallholder farmers globally. They have basic Android phones, 2G connectivity, speak regional languages, and cannot read long text. Agricultural advisory exists on web portals they never visit.

**What it does:** Speak your problem (crop disease, weather, market prices). App transcribes via Whisper (on-device), sends to LLM, reads answer back in your language. Works on 2G. Stores last 10 questions offline.

**Stack:** Flutter · Whisper.cpp (on-device) · Ollama/small LLM · FastAPI · gTTS · PostgreSQL

**Differentiator:** Truly offline-capable TTS+STT. Regional language support (Hindi, Swahili, Tamil). Voice-first, not text-first. Community Q&A where answers are verified by local agronomists.

**Agency Agents Activated:**
- `Mobile App Builder` → Flutter + on-device ML integration
- `AI Engineer` → Whisper.cpp + LLM prompt chain for agronomic domain
- `Cultural Intelligence Strategist` → regional language + cultural appropriateness
- `UX Researcher` → rural farmer UX research brief
- `Backend Architect` → lightweight sync for low-bandwidth

---

### `10` MicroBreak Coach — Burnout Prevention via HRV + ML
**The Niche:** Burnout costs $125B/year in healthcare. Headspace and Calm are passive. No app actually detects cognitive fatigue in real-time and intervenes before burnout hits.

**What it does:** Reads HRV data from Apple Watch/Fitbit. ML model detects when stress-to-recovery ratio crosses threshold. Sends contextual nudge: "You've been in deep work 110 minutes. 4-7-8 breath, 3 min." Tracks whether you took the break. Weekly recovery score.

**Stack:** SwiftUI (iOS) · HealthKit · CoreML (on-device) · FastAPI · PostgreSQL · WidgetKit

**Differentiator:** Proactive, not reactive. On-device ML = no data leaves phone. Backed by HRV science (not just step count). Integrates with calendar to avoid nudging during meetings.

**Agency Agents Activated:**
- `Mobile App Builder` → SwiftUI + HealthKit integration
- `AI Engineer` → HRV-based fatigue ML model (CoreML)
- `UX Designer` + `UX Architect` → habit loop design
- `Security Engineer` → HealthKit data privacy, on-device inference
- `Ethical Reviewer` → health claim validation, no medical device claims

---

### `11` NativeScan — Edge ML Quality Control for Micro-Factories
**The Niche:** Large manufacturers use $500k Cognex vision systems. Small garment/electronics factories in Southeast Asia (20–200 workers) have zero automated QC and rely on manual inspection — 6–8% defect rate.

**What it does:** Flutter tablet app. Point camera at product on production line. On-device TensorFlow Lite model classifies defect type + severity in < 200ms. Logs defect rate by shift, operator, and product line. Weekly quality report.

**Stack:** Flutter · TensorFlow Lite · FastAPI · PostgreSQL · S3 (defect image archive)

**Differentiator:** Model pre-trained on common textile/PCB defect datasets, then fine-tuned with 50–100 client images. No cloud dependency. Runs on $150 Android tablet.

**Agency Agents Activated:**
- `AI Engineer` → TFLite model training + quantization
- `Mobile App Builder` → Flutter camera + inference integration
- `Data Engineer` → defect telemetry pipeline + report generation
- `UX Researcher` → factory floor UX (noisy, moving, operator literacy)
- `DevOps Automator` → OTA model update pipeline

---

## Domain 4 — SaaS Startups

### `12` LegalDiff — AI Contract Redlining for Freelancers
**The Niche:** 60M+ freelancers in the US sign contracts blind. Legal review costs $300–500/hour. Existing AI legal tools (Harvey, Ironclad) are enterprise-only with $20k+/year contracts.

**What it does:** Upload two contract versions (PDF/DOCX). AI diffs them, highlights changed clauses, gives each change a risk score (Low/Medium/High) with plain-English explanation. Flags missing clauses (IP assignment, termination, payment terms).

**Stack:** FastAPI · Next.js · PostgreSQL · Claude API (long context for contracts) · PDF.js · Diffing library

**Differentiator:** Compares versions, not just analyzes one. Risk-scored. Plain English. $10/month — less than 5% of one lawyer hour.

**Agency Agents Activated:**
- `AI Engineer` → contract diff + clause extraction pipeline
- `Prompt Engineer` → structured extraction + risk scoring prompts
- `Backend Architect` → document processing pipeline (PDF → structured JSON)
- `Frontend Developer` → side-by-side diff viewer
- `Security Engineer` → PII handling, document encryption at rest, no training on user docs

---

### `13` TechDebtLens — Technical Debt Scoreboard for CTOs
**The Niche:** CTOs at Series A companies need to sell engineering work to the board. "We have technical debt" is not fundable. A quantified, prioritized, business-risk-linked debt register is. No tool exists for this.

**What it does:** Connect GitHub repo. Analyzes: cyclomatic complexity trends, test coverage gaps, dependency age, hotspot files (high churn + low coverage). Generates a "Debt Portfolio" — each item has business risk score, estimated fix cost, and recommended action.

**Stack:** FastAPI · Next.js · PostgreSQL · GitHub API · SonarQube integration · OpenAI (natural language summaries)

**Differentiator:** Business language, not engineer language. Links debt to revenue risk. Generates slide-ready board report PDF. Tracks debt paydown over time.

**Agency Agents Activated:**
- `AI Engineer` → code complexity analysis + NL summary generation
- `Backend Architect` → GitHub API ingestion + static analysis pipeline
- `Sprint Prioritizer` → RICE-scored debt backlog generation
- `Frontend Developer` → debt heatmap + CTO dashboard
- `Technical Writer` → board-ready report generation

---

### `14` ChurnRadar — Churn Prediction SDK for Early-Stage SaaS
**The Niche:** Mixpanel and Amplitude give you dashboards. Gainsight costs $30k+/year and requires a CS team to operate. Pre-Series A SaaS teams have no early warning system for churn.

**What it does:** Drop in 5 lines of JS/Python. SDK pipes usage events to ChurnRadar. Trains a gradient boosting model per customer. Each account gets a daily churn probability score + top contributing factors. Triggers Slack alert when score spikes.

**Stack:** FastAPI · React · PostgreSQL · XGBoost · Celery · Redis · JavaScript SDK

**Differentiator:** Zero data science required. Works with < 500 customers (unlike enterprise tools that need "enough data"). Explains predictions in plain English. Integrates with HubSpot/Intercom for intervention workflows.

**Agency Agents Activated:**
- `AI Engineer` → XGBoost churn model + feature engineering
- `Backend Architect` → event ingestion pipeline + per-tenant isolation
- `Data Engineer` → multi-tenant feature store
- `Frontend Developer` → account health dashboard
- `Security Engineer` → multi-tenant data isolation, SOC2-readiness checklist

---

### `15` CodeCarbon Tracker — ML Training Sustainability Dashboard
**The Niche:** EU AI Act mandates sustainability disclosures. Green AI is becoming an investor + enterprise procurement criterion. No lightweight, developer-friendly tool exists that tracks CO2 per training run and generates compliance-ready reports.

**What it does:** GitHub Action + Python decorator. Measures GPU energy consumption using NVIDIA NVML / Intel RAPL. Maps to regional carbon intensity (CO2Signal API). Generates per-experiment carbon budget. Creates EU AI Act sustainability annex PDF.

**Stack:** Python package · FastAPI · Next.js · PostgreSQL · GitHub Actions · CO2Signal API

**Differentiator:** CI/CD native. Per-commit + per-experiment tracking. EU AI Act report template built-in. "Your model training emitted 2.3kg CO2 — equivalent to driving 14km."

**Agency Agents Activated:**
- `AI Engineer` → energy measurement instrumentation
- `DevOps Automator` → GitHub Actions + pip package release pipeline
- `Backend Architect` → carbon accounting API
- `Ethical Reviewer` → EU AI Act compliance checklist
- `Technical Writer` → SDK docs + compliance report templates

---

### `16` DocVector — Private RAG Platform for Regulated Industries
**The Niche:** Law firms, medical practices, financial advisors can't send documents to OpenAI. They have enormous internal knowledge bases and zero ability to query them. Enterprise solutions (MS Copilot for M365) cost $30+/user/month and require Azure.

**What it does:** Self-hosted Docker container. Upload PDFs/DOCX. Embeddings stored locally (ChromaDB). Query in natural language. Cites source + page. Multi-user with role-based access. Air-gapped mode available.

**Stack:** FastAPI · React · ChromaDB · Ollama (local LLM) · PostgreSQL · Docker Compose

**Differentiator:** 100% local — no data ever leaves the network. One `docker-compose up`. Runs on a $600 server. Ollama supports Llama, Qwen, Mistral — no API keys.

**Agency Agents Activated:**
- `AI Engineer` → RAG pipeline + embedding + retrieval tuning
- `Backend Architect` → multi-user document isolation
- `Security Engineer` → auth, RBAC, document encryption, audit logs
- `DevOps Automator` → Docker Compose + air-gapped deployment scripts
- `Frontend Developer` → document library + chat interface

---

### `17` TestGenAI — AI Test Case Generator from Git Diffs
**The Niche:** Solo developers and 2-person teams skip QA. Not laziness — they don't have time to write tests for every PR. Copilot suggests unit tests but doesn't generate integration/edge-case tests from what actually changed.

**What it does:** GitHub App. On every PR, diffs the changed files, analyzes the AST, generates: unit tests for new functions, edge case tests for modified logic, integration test stubs for changed API endpoints. Creates a draft PR comment with ready-to-commit test code.

**Stack:** FastAPI · TypeScript · GitHub App SDK · Tree-sitter (AST parsing) · OpenAI/Claude API

**Differentiator:** AST-aware — understands code structure, not just text diff. Generates test code in the project's existing test framework (detects Jest vs Pytest vs RSpec). Creates test PR you review and merge.

**Agency Agents Activated:**
- `AI Engineer` → AST analysis + test generation pipeline
- `Prompt Engineer` → few-shot test generation prompts per language/framework
- `Backend Architect` → GitHub App webhook architecture
- `DevOps Automator` → GitHub App deployment + marketplace listing
- `Senior Developer` → test quality validation logic

---

### `18` PricePulse — Dynamic Pricing Engine for Independent Shopify Merchants
**The Niche:** Amazon sellers have Repricer.com. Shopify merchants have nothing. Independent sellers lose 15–20% revenue daily by not adjusting prices when competitors run sales or demand spikes.

**What it does:** Connects to Shopify store. Scrapes competitor prices via Firecrawl/Playwright. Trains demand elasticity model per SKU. Recommends price changes with expected revenue delta. One-click "Apply All" or rules ("Never go below cost + 20%").

**Stack:** FastAPI · Next.js · Shopify API · PostgreSQL · Playwright (scraping) · XGBoost (elasticity) · Celery

**Differentiator:** Decision engine considers margin floor, not just competitor matching. Shows merchants expected $ impact before applying. Shopify App Store distribution channel.

**Agency Agents Activated:**
- `AI Engineer` → demand elasticity ML, price recommendation engine
- `Data Engineer` → competitor scraping pipeline + price history store
- `Backend Architect` → Shopify OAuth + Webhook integration
- `Frontend Developer` → pricing dashboard + rules builder
- `Growth Hacker` → Shopify App Store listing + launch strategy

---

### `19` AccessAudit — Physical Space Accessibility Scanner
**The Niche:** 15% of the global population has a disability. ADA/WCAG compliance for physical spaces is legally mandated but manually audited at $500–2000/site. Property managers don't audit until they get sued.

**What it does:** React Native app. Walk through a space, photograph potential barriers (narrow doorways, no ramps, inaccessible signage). On-device CV model classifies barrier type + ADA compliance status. Generates audit report with prioritized remediation checklist + estimated fix costs.

**Stack:** React Native · TensorFlow Lite · FastAPI · PostgreSQL · PDF report generation · S3

**Differentiator:** Evidence-based (photos attached to each finding). Remediation cost estimates. LEED/ADA/ISO 21542 compliance mapped. Reusable audit templates for different space types.

**Agency Agents Activated:**
- `Mobile App Builder` → React Native + TFLite camera pipeline
- `AI Engineer` → barrier classification model training
- `UX Researcher` → disability community co-design research
- `Ethical Reviewer` → false positive/negative impact on vulnerable users
- `Technical Writer` → ADA compliance report template generation

---

### `20` AgentBoard — Project Management Purpose-Built for AI Agent Workflows
**The Niche:** Running 70+ AI agents across 11 divisions has no native tooling. GitHub Issues + Notion were built for human teams only. No tool maps to Agile sprints, records inter-agent debates, and tracks agent performance over time.

**What it does:** A GitHub Issues + Notion hybrid, purpose-built for AI-native workflows. Each "task" is an agent activation. Sprint boards show which agent is working what. Debates (Śhāstrārtha) are stored as threaded comment chains. Memory written automatically after each session. Performance scores agents like a team lead.

**Stack:** Next.js · FastAPI · PostgreSQL · GitHub Issues API · OpenAI (summaries) · WebSockets

**Differentiator:** The first project management tool designed for human × AI teams, not just humans. Sells itself to everyone adopting The Agency framework — your own community is your first market.

**Agency Agents Activated:**
- Every division contributes requirements
- `Backend Architect` → multi-agent workflow data model
- `Frontend Developer` → sprint board + debate threads UI
- `Prompt Engineer` → agent activation template library
- `AGI Memory Manager` → writes project state after each sprint

---

## Recommended 10 to Build First

| # | Project | Domain | Why Pick It |
|---|---------|--------|-------------|
| 1 | **DriftSentinel** | MLOps | Python SDK + SaaS, fastest to get working demo |
| 2 | **RunbookAI** | AIOps | Slack bot = instant virality in engineering communities |
| 3 | **ObserveML** | AIOps/LLM | Every RAG builder in the world needs this right now |
| 4 | **FieldSyncPro** | Mobile | Real, paying SMB customers. Offline-first = unique moat |
| 5 | **LegalDiff** | SaaS | 60M freelancers. Claude's long context = unfair advantage |
| 6 | **DocVector** | SaaS | Regulated industries = high willingness to pay |
| 7 | **ChurnRadar** | SaaS/ML | Every SaaS founder feels this pain personally |
| 8 | **TestGenAI** | DevTools | GitHub Marketplace distribution built-in |
| 9 | **NativeScan** | Mobile/ML | Edge ML moat. Emerging market blue ocean |
| 10 | **AgentBoard** | SaaS | You already have the domain knowledge — you built The Agency |

---

## 15-Day Sprint Structure (Per Project)

```
Days 1–2   → AGI Goal Decomposer activation plan
             GitHub repo setup + branch protection rules
             Sprint Prioritizer creates 3 sprints + 30 GitHub Issues
             Milestones: Sprint 1 / Sprint 2 / Sprint 3 / Launch

Days 3–7   → Sprint 1 & 2: Core Build
             Backend Architect + AI Engineer + DB Architect
             DevOps Automator wires CI/CD (GitHub Actions → Railway/Fly.io)
             PR template enforced, coverage gate ≥ 80%

Days 8–10  → Sprint 3: Polish + QA
             Frontend Developer builds UI
             QA Engineer writes STLC test plan (unit, integration, e2e)
             Security Engineer audit pass (OWASP Top 10)

Days 11–12 → STLC Execution
             Integration tests, load tests, edge case coverage
             Playwright e2e against staging environment

Days 13–14 → Hardening Gates
             Ethical Reviewer sign-off
             Reality Checker milestone gate
             Technical Writer: README + API docs + CHANGELOG

Day 15     → Launch
             Growth Hacker: Product Hunt / Hacker News / Reddit
             Self Reflector writes retrospective
             Memory Manager writes to memory/project-state/
```

---

## CI/CD Pipeline Template (All Projects)

```yaml
# .github/workflows/main.yml
# Runs on every PR and merge to main

on: [push, pull_request]

jobs:
  test:
    # pytest / jest — coverage gate ≥ 80%

  lint:
    # ruff (Python), eslint (JS/TS), mypy (type checking)

  security:
    # bandit (Python), npm audit, trivy (Docker image scan)

  build:
    # Docker build + push to GitHub Container Registry (GHCR)

  deploy-staging:
    # Railway / Fly.io staging deploy on every PR
    # environment: staging

  e2e:
    # Playwright tests against staging URL

  deploy-production:
    # Manual approval gate required
    # environment: production (protected)
```

**GitHub Issues Hierarchy per Project:**
- `Epic` → Feature area (e.g., "Authentication", "ML Pipeline", "Dashboard")
- `Story` → User story with acceptance criteria
- `Task` → Implementation subtask (≤ 1 day of work)
- `Bug` → Defect found in testing
- `Debt` → Technical debt item

**Branch Strategy:**
- `main` → protected, no direct push, requires PR + passing CI
- `staging` → auto-deploys to staging environment
- `feat/*` → feature branches, open PR to main
- `fix/*` → bug fix branches
- `chore/*` → debt / infra / tooling

---

*The Agency AGI — Project Ideas v1.0.0 — 2026-03-11*
