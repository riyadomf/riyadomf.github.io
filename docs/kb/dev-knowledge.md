# Dev Knowledge, Md Omar Faruqe (Riyad)

*Last updated: 2026-07-18. For jobs, dev CV, and the job-experience / projects / skills pages. Shared facts and writing rules live in [README.md](README.md).*

## Contents

1. [Positioning and pitches](#1-positioning-and-pitches)
2. [DSI experience deep-dives](#2-dsi-experience-deep-dives)
3. [Altri.ai / RevestAI deep-dives](#3-altriai--revestai-deep-dives)
4. [Side projects and open source](#4-side-projects-and-open-source)
5. [Skills matrix](#5-skills-matrix)
6. [Quantified achievements](#6-quantified-achievements)
7. [STAR stories](#7-star-stories)
8. [Technical deep-dives](#8-technical-deep-dives)
9. [Question-to-material map](#9-question-to-material-map)
10. [CV bullet pool](#10-cv-bullet-pool)
11. [CV-editing lessons from the 2026-07 review](#11-cv-editing-lessons-from-the-2026-07-review)

---

## 1. Positioning and pitches

### Headline (LinkedIn / one-liner)

"Software Engineer | Backend Systems & AI Infrastructure" (this is also the dev CV title line)

### 30-second version

> "I'm a backend systems engineer with a parallel track in production AI. At DSI I build government-scale Jakarta EE applications and operational tooling; I open-sourced `gf`, a GlassFish hot-swap CLI that cut my team's edit-deploy cycles from about two minutes to five seconds. At Altri.ai I build production AI pipelines for real-estate investment scoring, combining LLM feature extraction with XGBoost valuation and deterministic financial heuristics."

### 60-second version

> "I'm a software engineer with strong backend systems experience and a parallel track in production AI.
>
> Full-time at Dynamic Solution Innovators since April 2023, I build mission-critical Jakarta EE systems for government clients. I defined the security model and CDI/EJB conventions for E-Appeal, DSI's first enterprise-scale Jakarta EE application, and those conventions were adopted by the firm's later JEE projects. I recently joined EC-BVRS, Bangladesh's national voter registration platform serving records of 150+ million people.
>
> Part-time at Altri.ai (product: RevestAI), I lead full-stack and AI infrastructure work: three-stage property scoring, distributed job coordination on Postgres without adding Redis, and ML training with Champion/Challenger validation. I'm an SUST CSE grad with three NLP workshop papers and a research internship on SREGym, an AI-for-SRE benchmark from UIUC."

### 3-minute walk (interview opener)

1. DSI scope: government clients, Jakarta EE depth, now EC-BVRS at national scale
2. The `gf` CLI hero story: problem, investigation, JDWP/JDI solution, 2 min to 5 s, team-wide adoption, open-sourced, Claude Code integration
3. E-Appeal as multiplier: conventions became the firm's JEE template
4. BCIC modules ownership: Procurement, Inventory, Asset, Budget, including the StorageClient/nginx delivery rework
5. Altri three-stage architecture (Facts, Opinions, Math) and what each layer does
6. Distributed Postgres locking pragmatism (did not bolt on Redis)
7. Research track in one line: SREGym benchmark work plus three NLP papers (shows range, then move on for dev audiences)
8. Teaching: Enterprise JEE course at Dynamic Learning

---

## 2. DSI experience deep-dives

**Software Engineer | April 2023 to present | Dhaka, Bangladesh.** Core member of the engineering team building large-scale enterprise systems for government and public-sector clients (EC, NBR, MoCAT, BCIC). Cross-cutting roles: open-source tooling, Cybersecurity Team, course authoring.

### 2.1 EC-BVRS (Election Commission, Bangladesh Voter Registration System)

> **Status**: current project, joined July 2026
> **Scale**: national voter registration (NID) platform; the voter registration flow processes records for nearly 150 million voters
> **Tech**: Spring Boot, Kafka, Redis
> **Detail level**: keep descriptions at the level already published on the portfolio (project name, scale, stack)

**Where it stands**: contributing to the data pipeline behind the voter registration flow. This project is what backs Spring Boot, Kafka, and Redis in the skills lists.

**Canonical CV bullet** (both variants, 2026-07-29): "Contributed to the data pipeline behind the voter registration flow of Bangladesh's national voter registration (NID) platform, which processes records for nearly **150 million voters** (Spring Boot, Kafka, Redis)."

**Framing rule**: no "recently joined" or "currently ramping up" wording anywhere. It goes stale on its own and reads weaker than the contribution itself. State what was built.

**To fill in as contributions grow**: which pipeline stages were owned, throughput numbers, specific Kafka topic/consumer patterns, Redis caching strategy, any migration or reliability work.

### 2.2 `gf`, GlassFish hot-swap CLI

> **Status**: open-sourced, in daily team use; integrated as a Claude Code skill
> **Years**: 2024–2026 (active)
> **Tech**: Java, Bash, JDI/JDWP, GlassFish, Maven, rsync
> **Repo**: github.com/riyadomf/glassfish-hotswap-cli

**What it is**: a CLI dev tool that hot-swaps modified bytecode into a running GlassFish JVM via JDI/JDWP, with JasperReports classloader-cache bypass and automatic full-redeploy fallback for structural class changes.

**Contributions**
- Built the JDI client (`HotSwap.java`) that attaches to the running JVM's debug port and atomically swaps changed classes in memory
- Reverse-engineered Mojarra 4.1.6's `FaceletCacheFactoryImpl` to diagnose XHTML staleness; found `ProjectStage`-aware `FACELETS_REFRESH_PERIOD` defaults; solved via Maven profile filtering
- Built JasperReports hot-reload by detecting `file://` vs `jar://` resource URLs and reading directly from the exploded-deployment filesystem
- Shipped the fallback path: full redeploy when JDI rejects the swap (added/removed methods, signature changes)
- Integrated as a Claude Code skill (`/gf`) for natural-language server lifecycle management

**Impact**: edit-deploy cycle from ~2 minutes to ~5 seconds (~96% reduction, but lead with the raw numbers; they are stronger than the percentage). Adopted team-wide.

**Why it was hard**: the JDI API is documented but underused, with almost no production-grade examples; Mojarra cache behavior required tracing source, not flipping a config; JasperReports caches at the classloader level, so bytecode hot-swap alone leaves report templates stale.

**Tradeoffs**: JDI/JDWP over JRebel (commercial license) and HotswapAgent (more invasive); CLI over an IDE plugin (terminal-first, AI-integratable, editor-agnostic).

**Likely follow-ups**
- *Why not JRebel?* Cost and licensing for a team-wide tool; JDWP gives what we needed for free.
- *Failure mode?* Structural changes fall back to full redeploy, automatically.
- *How did the team adopt it?* Demo session, paired with two early adopters, then word-of-mouth.

### 2.3 E-Appeal (NBR / USAID)

> **Status**: in production at NBR
> **Years**: 2023–2024
> **Tech**: Jakarta EE, JSF, PrimeFaces, CDI, EJB, JPA/Hibernate, JMS, Jakarta Security, PostgreSQL
> **Detail level**: client-specific business logic stays vague

**What it is**: a digital platform for managing tax-related appeals between taxpayers and the National Board of Revenue, funded in part by USAID.

**Contributions**
- Defined the security model (Jakarta Security with custom form-based auth), package layout, and CDI/EJB conventions for DSI's first large-scale Jakarta EE system; the conventions were adopted by SHMS, BCIC-ERP, and Project Scratch
- Centralized RBAC enforcement: replaced authorization checks scattered across JSF views and services with a unified permission-evaluation layer (a CDI-managed `PermissionEvaluator` resolved once per request)
- Designed the asynchronous notification subsystem on JMS with idempotent consumers and DLQ-backed retries, so transient gateway failures never blocked appeal submissions

(Framing note: the earlier "built the foundational architecture" phrasing was retired in the 2026-07 review; use the concrete "defined the security model and CDI/EJB conventions" version.)

**Tradeoffs**: centralized RBAC layer over annotation-only `@RolesAllowed` because permissions needed to be data-driven (per-record permissions on appeal documents); JMS+DLQ over synchronous SMS dispatch because gateway flakiness was a regular operational hit.

**Likely follow-ups**
- *Why not Spring Boot?* Jakarta EE was the firm's existing standard; reinventing on Spring would not have served the team.
- *How did the conventions spread?* Written package-conventions doc, internal walkthroughs, and a working reference implementation.

### 2.4 SHMS (Smart Hotel Management System)

> **Status**: in production (nationwide licensing/registration for hotels and restaurants)
> **Year**: 2024 | **Built on**: Project Scratch platform
> **Tech**: Jakarta EE, JSF, PrimeFaces, CDI interceptors, PostgreSQL

**Contributions**
- Designed the state-driven approval workflow engine: a configuration-driven state machine (states, transitions, and per-state actions stored as data, not code) that replaced per-application-type hardcoded approval logic; reused across other DSI projects
- Engineered the dynamic field-level correction system: reviewers reopen only selected form fields with inline feedback, fields unlock atomically with per-field reviewer notes, audit history preserved
- Kept auditing and notification dispatch out of business code via CDI interceptors (AspectJ-style cross-cutting)

**Impact**: cross-project reuse of the engine is the strongest signal of good design here.

**Tradeoffs**: state machine + config over a workflow product (Camunda etc.), since that overhead was not justified at this scale; CDI interceptors over an explicit auditing wrapper layer (one less indirection).

### 2.5 Project Scratch (internal core-services platform)

> **Status**: internal infrastructure used across DSI projects (notably SHMS)
> **Year**: 2024
> **Tech**: GlassFish, PostgreSQL, MinIO, Docker, Prometheus, Loki, Grafana

**Contributions**
- Engineered the observability stack: Prometheus scraping JMX from GlassFish, Loki for log aggregation, Grafana dashboards for JVM heap, thread pools, and request latency, replacing ad-hoc SSH-and-tail debugging
- Dockerized the full application stack (GlassFish, PostgreSQL, MinIO) for consistent local and staging environments
- Contributed PrimeFaces PR #12865 from this work (see §4.2)

### 2.6 BCIC-ERP

> **Status**: in production at BCIC (Bangladesh Chemical Industries Corporation)
> **Years**: 2024–2026
> **Tech**: Jakarta EE, JSF, PrimeFaces, MinIO, nginx, PostgreSQL, JMS

**What it is**: an ERP for process automation across 12 integrated modules.

**Contributions**
- Led the Procurement, Inventory, Asset, and Budget modules end-to-end (4 of 12): process modeling (As-Is/To-Be), schema design, backend implementation, UAT, production rollout
- Re-architected file storage and delivery behind a pluggable `StorageClient` abstraction (MinIO or filesystem); replaced base64-inlined file rendering with URL-based streaming, which cut page payload size and server memory pressure
- Added scoped file authorization and nginx `X-Accel-Redirect` offloading: the app validates auth and returns a header pointing to an internal-only nginx location; nginx serves the bytes, the JVM never touches the file stream
- Designed the JMS notification pipeline with DLQ-backed retries, isolating SMS/email failures from the request path

**Impact**: the file-delivery rework eliminated multi-MB HTML pages and the OOM patterns they caused; nginx offload moved heavy file traffic off the JVM thread pool.

**Tradeoffs**: `X-Accel-Redirect` over signed-URL-to-S3 (nginx integration was simpler and did not change the deployment shape); pluggable backends so dev/staging can run without MinIO.

### 2.7 Cybersecurity Team

> **Status**: cross-project role, 2023 to present
> **Tech**: OWASP Top 10, Burp Suite / OWASP ZAP, SAST, manual code review
> **Detail level**: findings are client-confidential; discuss only category-level patterns

**Contributions**: authenticated vulnerability assessments on Jakarta EE applications pre-deployment; threat modeling; static and dynamic testing; access-control, injection, and input-validation flaws caught before government releases.

**Category-level talking points**: missing authorization on data endpoints (IDOR), insufficient input validation, file-upload trust issues. Process: code review, DAST against staging, threat-model walkthrough with the project team. Outcome: every project gets a clean security report before production sign-off.

**Placement**: off the dev CV since 2026-07; stays on the research CV and the site. The ISC2 CC certification carries the security signal on the dev CV.

### 2.8 Course Instructor (Dynamic Learning)

> **Years**: 2024 to present, active

Authored and teaches *Enterprise Web Development with JEE, JSF, and PrimeFaces* (use this exact course name everywhere): component-driven design, CDI/EJB integration, JSF lifecycle management. YouTube playlist linked from the CV. CV value: mentorship signal, "can teach what I do".

---

## 3. Altri.ai / RevestAI deep-dives

**Full-Stack AI Engineer | part-time, remote (US).** Product: RevestAI (revestai.com), AI-assisted real-estate investment analysis. Scrapes listings, enriches with LLM analysis, estimates ARV/rent via ML, scores investment potential, delivers email alerts. Stack: FastAPI + React + scheduler pipeline + ML training, on Supabase (Postgres) and Render. Built the backend, scheduler pipeline, ML training/promotion flow, frontend integration, and AI infrastructure. **CVs keep this entry undated by choice.**

### 3.1 Three-stage property scoring pipeline

**Architecture: Facts, then Opinions, then Math.**
- **Facts** (LLM enrichment): `gpt-4.1-nano` extracts a UAD condition rating (C1–C6) and 20 investor tags from listing descriptions. Smart fallbacks for missing/empty text (age-based defaults; conservative C4 for empty).
- **Opinions** (valuation): Strategy pattern. Either XGBoost regression predicting ARV in "ideal renovated state", or LLM web-search valuation using the OpenAI Responses API with live comps. Active strategy is a `SystemSetting` DB row, so switching algorithms is one INSERT, not a code change.
- **Math** (deterministic financial scoring): 70%-rule for flips, 1%-rule for rentals, risk synthesis (physical-condition risk plus financial-deal risk), ROI computation.

**Why three layers**: isolation. Retrain the ML model without re-running LLM enrichment; the financial layer is pure math, testable independently; each layer's failure mode is contained.

### 3.2 LLM enrichment with asyncio (the 10x story)

Rewrote the enrichment job from sequential to `asyncio.gather` with a semaphore-bounded concurrency limit (default 5) and atomic per-batch commits.

- Bounded concurrency: naive gather over N tasks dispatches all N, which hammers rate-limited LLM APIs into 429 spirals; the semaphore keeps in-flight count inside OpenAI limits, and connection reuse amortizes TCP/TLS overhead
- Atomic per-batch commits: failed batches do not roll back successfully enriched listings, so completed LLM calls are never re-charged, and a restarted worker resumes at the last successful batch

**Impact**: ~10x throughput vs sequential; proportional drop in per-property OpenAI cost.

### 3.3 Ingestion pipeline (content-hash dedup + delta-sync)

- Scrape via HomeHarvest into PostgreSQL `current_listings`
- Content-hash dedup: MD5 over a canonical JSON of 15 key fields (property_id, MLS ID, status, price, sqft, photos, description...); identical listings map to the same enrichment
- Delta-sync since `location.last_scraped_at`: incremental, not full re-scrape
- Window functions (`ROW_NUMBER() OVER (PARTITION BY location_id)`) cap listings per location so one city with 10x inventory cannot skew workloads

**Why it matters**: re-running scrapes never duplicates LLM enrichment (real dollar cost) or pollutes historical lifecycle data; idempotent upserts on `property_id` preserve the latest entity hash.

### 3.4 Distributed job coordination on Postgres

`SELECT ... FOR UPDATE` with automatic stale-lock recovery (default 120 minutes), tracked in a `PipelineMetadata` table via a `JobContext` Python context manager (RUNNING / SUCCESS / FAILURE).

**Two-layer locking** (the key insight):
1. Postgres row lock via `FOR UPDATE`: short-lived, held only during the acquisition transaction; serializes the check-then-act so two replicas cannot both pass "am I running?"
2. Application lease: the row's `last_status = 'RUNNING'` IS the lock for the job's duration; persists across connections.

**Stale-lock recovery**: a crashed holder would leave the lease stuck at RUNNING forever; the timeout lets a fresh worker break it and take over.

**Why not Redis/Zookeeper**: Postgres was already in the stack. Another stateful service means another thing to operate, two consistency models, extra failure modes. The row-based approach also makes `PipelineMetadata` double as a run-history audit log, which advisory locks cannot.

**Impact**: the scheduler runs as multiple Render replicas without double-enriching; a crashed worker does not halt the pipeline.
Whiteboard version: [§8.1](#81-postgres-select-for-update).

### 3.5 ML training and Champion/Challenger promotion

1. Training data: SOLD listings (ground-truth sale prices) with denormalized LLM features joined in
2. Train/holdout split including a gold-standard holdout slice (C2-condition, low-risk properties: clean signal, minimal noise)
3. XGBoost regression for ARV prediction
4. Model version stamped into the artifact bundle automatically
5. Upload to Supabase Storage staging with atomic `upsert=true`
6. Manual promotion gate: a human inspects Challenger vs Champion on the gold-standard slice before running `rescore-all`; no auto-trigger

**Why manual**: valuation is monetary; silent regressions cost real money. Frame the gate as deliberate, not as missing automation.

### 3.6 Unified notifications queue

One `notifications` table with a `source` discriminator (`buy_box` | `portfolio_alert` | `portfolio_digest`). Three matcher jobs enqueue PENDING rows; one sender job dispatches, branching on `source` for the template. Adding a notification type = one matcher + one template; no parallel send pipeline. Per-source dedup via type-specific unique constraints.

### 3.7 LLM JSON repair pipeline

Malformed LLM JSON (missing brace, markdown fences, token-limit truncation) crashes naive `json.loads`. Solution: a four-strategy fallback parser: direct parse; code-block extraction; boundary-finding (first `{`, scan backward for matching `}`); truncated-JSON repair (close unclosed quotes/braces). Plus exponential-backoff retry on the API call (max 2). Structured error dicts on permanent failure instead of silent `None`.

---

## 4. Side projects and open source

### 4.1 KnowledgeRelay (2025)
Knowledge-transfer agent built in a 24-hour onsite hackathon; 6th of 30 teams, DSI AI Agent Hackathon 2025. Repo: github.com/riyadomf/knowledgeRelay

**What it actually does** (corrected 2026-07-29 against the repo README; earlier CV copy described only the document half and missed the point of the project): the problem is that critical unwritten knowledge leaves with departing team members. Two ingestion flows: **Project QA** interactively prompts outgoing members with adaptive, context-aware questions generated from chat history, and **Document QA** extracts knowledge from uploaded files (PDFs, Word docs, code) with chunking strategies that differ for code versus prose. Retrieval is RAG over ChromaDB with metadata filtering; follow-up questions are rewritten into self-contained queries using prior conversation context; answers carry source attribution back to the originating file. Hybrid OpenAI/Ollama support.

Tech: Python, FastAPI, LangChain, ChromaDB, OpenAI, Ollama, React.

**Canonical CV bullet**: "Built a knowledge-transfer agent that interviews outgoing team members with adaptive questions, ingests their documents and code, and answers new joiners' questions with source attribution. Retrieval rewrites follow-ups into self-contained queries; chunking differs for code and prose."

### 4.2 PrimeFaces PR #12865 (2024, merged)
Added the ability to inject custom `FilterMeta` into `JPALazyDataModel`, enabling advanced filtering beyond the stock component. PrimeFaces has 12k+ GitHub stars and is used by thousands of enterprise apps. A merged PR in a major library is worth more than self-graded bullets; keep it prominent.

### 4.3 SREGym fault-scenario PR #886 (2026, merged)
Dev-relevant angle: Kubernetes failure-mode depth (admission webhooks, NetworkPolicy, RBAC, kind). Full details live in [research-knowledge.md](research-knowledge.md) §2; on the dev CV it lives under Projects with the research entry kept bird's-eye.

### 4.4 Token-Efficient LLM Query Router (2026)

> **Context**: AMD Hackathon Act II, Track 1. Repo: github.com/riyadomf/llm-query-router
> **Goal**: answer 8 task categories (factual QA, math, sentiment, summarization, NER, code debugging, logic, code generation) while minimizing paid API token spend under a hard accuracy gate.

**Architecture, a precision-gated cascade** (each tier only answers what it can prove it handles; everything uncertain escalates):
1. **Regex router**, zero tokens, classifies the task category and falls through to a safe default when uncertain. Measured 64/64 on dev, practice, and adversarial paraphrase sets.
2. **ONNX sentiment specialist** (DistilBERT-SST2), non-generative, zero tokens. Shipped only after measuring 100% precision at 38% coverage; uncertain cases escalate to cloud.
3. **Fine-tuned Qwen2.5-1.5B** (LoRA via Unsloth on a free Colab T4, ~2,800 programmatically validated synthetic examples) handles factual QA and NER locally. A wall-clock speed calibration detects the grading VM's real throughput at runtime and enables a category only when it can finish safely.
4. **Cloud model** (Fireworks API) as accuracy backstop, with minimized system prompts, thinking mode disabled (199 to 55 tokens on the first call), and per-category token caps.

**The two ideas worth telling in an interview**:
- **Program-aided math**: instead of having the model compute, it emits a short symbolic expression evaluated by a sandboxed AST interpreter. Removes arithmetic error as a category and cuts output tokens ~90%.
- **Deterministic verification guards instead of model self-assessment**: self-reported confidence was tested and found unreliable at this scale, so local answers pass programmatic checks (for example, an entity-completeness check requiring every named entity in the source to appear in the output: 99% detection of dropped entities at 62% acceptance over 597 ground-truth rows).

**Engineering process** (the part that reads as senior):
- LLM-as-judge evaluation harness mirroring the official rubric, so every change was tested offline before a submission was spent.
- Offline precision experiments killed unpromising ideas on measured evidence (a batching optimization, a naive NER specialist, a "neutral" sentiment heuristic) before they cost a submission.
- 17 measured build iterations logged version by version in SCORES.md with root-cause analysis, including a production timeout bug, an accuracy-gate failure, and a token regression from an over-broad regex.
- Immutable Docker image tags per submission for reproducibility, adopted after an early mutable-tag mistake made it unclear which code had actually been graded.
- Capability promotion loop: LLM-generated synthetic data, programmatic validation (execution-checked math, fact-coverage-checked summaries), fine-tune, A/B evaluate, promote only on a measured win.

**No final leaderboard rank is published**; do not claim one.

### 4.5 Shopaholic (2022)
Full-stack e-commerce platform. Node.js, Express, MongoDB, React, Redux. REST API, schemas, frontend.

### 4.6 Brevity (2021)
Knowledge-sharing blog platform. Python, Flask, MySQL, vanilla JS. Auth, CRUD, comments, profiles.

---

## 5. Skills matrix

Rule: every skills-line entry is a claim volunteered for interrogation. Anything without evidence gets probed and discounts the real entries.

| Category | Skill | Last used | Evidence |
|---|---|---|---|
| **Languages** | Java | 2026 | DSI (daily), gf CLI |
|  | Python | 2026 | Altri (daily), scrapers, training |
|  | SQL | 2026 | Altri (heavy), DSI (heavy) |
|  | Bash | 2026 | gf CLI, scheduler scripts |
|  | JavaScript | 2026 | Altri React frontend |
|  | C/C++ | 2022 | Competitive programming, undergrad |
| **Backend** | Jakarta EE (CDI, EJB, JPA, JMS) | 2026 | DSI JEE projects |
|  | Spring Boot | 2026 | EC-BVRS (current), earlier side projects and course content |
|  | Kafka | 2026 | EC-BVRS (current; ramping up) |
|  | FastAPI | 2026 | Altri backend |
|  | Flask | 2021 | Brevity |
|  | GlassFish | 2026 | DSI JEE projects |
|  | AspectJ / CDI interceptors | 2026 | SHMS, cross-cutting |
|  | Python asyncio | 2026 | Altri enrichment pipeline |
| **AI / ML** | PyTorch | 2025 | BLP papers, fine-tuning |
|  | LLMs (OpenAI, Llama, Qwen) | 2026 | Altri, BLP-2025 |
|  | RAG / LangChain / ChromaDB | 2025 | KnowledgeRelay |
|  | XGBoost | 2026 | Altri valuation |
|  | LoRA fine-tuning | 2025 | BLP-2025 |
| **Databases** | PostgreSQL | 2026 | Altri, DSI |
|  | Redis | 2026 | EC-BVRS (current; ramping up) |
|  | MySQL | 2021 | Brevity |
|  | Supabase | 2026 | Altri |
|  | MinIO | 2026 | BCIC-ERP StorageClient |
|  | Hibernate / JPA | 2026 | DSI |
|  | Flyway, Alembic | 2026 | DSI / Altri respectively |
|  | Neo4j | 2024 | Coursework only. REMOVED from CVs and skills page (2026-07); do not re-add without real use |
| **Security** | OWASP Top 10, SAST/DAST | 2026 | DSI Cybersecurity Team |
|  | Jakarta Security | 2026 | E-Appeal and others |
|  | JWT, RBAC | 2026 | DSI, Altri |
|  | ISC2 CC certified | 2024 | Credential |
| **Infra** | Docker | 2026 | All projects |
|  | Kubernetes | 2026 | SREGym scenarios (admission webhooks, NetworkPolicy, kind). Frame as "K8s failure-mode knowledge", not "ran production K8s" |
|  | Git, GitHub Actions | 2026 | All projects |
|  | Prometheus, Grafana, Loki | 2024 | Project Scratch / SHMS observability |
|  | Nginx | 2026 | BCIC-ERP file delivery |
|  | Linux | 2026 | Daily |
|  | Ansible | 2024 | DSI infra |
| **Frontend** | React | 2026 | Altri |
|  | JSF, PrimeFaces | 2026 | DSI |

---

## 6. Quantified achievements

- **~2 min to ~5 s** edit-deploy cycle (`gf` CLI); "~96% reduction" as the secondary framing
- **~10x** throughput on LLM enrichment (Altri asyncio refactor)
- **~150 million** voters' records processed by the EC-BVRS voter registration flow (contributed to its data pipeline)
- **64/64** regex-router accuracy and **100% measured precision** on the gated ONNX sentiment tier; **~90%** output-token cut from program-aided math; **17** measured releases (LLM query router)
- **4 of 12** BCIC-ERP modules owned end-to-end (Procurement, Inventory, Asset, Budget)
- **PrimeFaces PR #12865** merged (12k+ star library)
- **SREGym PR #886** merged (UIUC AI-for-SRE benchmark)
- **4th of 32** teams, Code Generation in Bangla, IJCNLP-AACL 2025 (Pass@1 0.85)
- **6th of 30** teams, DSI AI Agent Hackathon 2025
- **Ranked 12th** in post-evaluation (19th official), VITD, BLP 2023
- **11th place**, BUET CSE Fest 2022 AI Contest
- **500+** algorithmic problems solved (Codeforces, LeetCode, LightOJ). Off the CVs since 2026-07 (filler at this career stage); stays on the skills page with profile links
- E-Appeal conventions adopted by 4+ subsequent DSI JEE projects
- CGPA 3.53/4.00 (last two years 3.83); 3 NLP workshop papers; ISC2 CC

---

## 7. STAR stories

### Story-to-question lookup

| If asked... | Use |
|---|---|
| Critical problem you solved | 7.1 gf CLI |
| Improved something proactively | 7.1 gf CLI |
| Deep debugging in unfamiliar code | 7.1 (Mojarra reverse-engineering) |
| Owned architecture / set the pattern | 7.2 E-Appeal |
| Pragmatic tradeoff / chose simplicity | 7.3 Postgres locking, no Redis |
| Performance optimization | 7.4 asyncio 10x |
| Designed for reuse | 7.5 SHMS approval engine |
| ML rigor / silent regressions | 7.6 Champion/Challenger |
| Mentorship / teaching | 7.7 JEE course |
| Ramping up on a large unfamiliar system | 7.8 EC-BVRS (fill in as it develops) |

### 7.1 Critical problem solved: `gf` CLI (verbatim-ready)

> **Situation/Problem**: One problem I worked on was improving the development workflow for our GlassFish-based enterprise applications at DSI. The edit-deploy-test cycle was extremely slow. Even small backend or JSF changes often required full redeployment, around two minutes each time, and since these are large monolithic Jakarta EE systems, it dragged the whole team's iteration speed.
>
> **Approach**: I investigated where the bottlenecks actually were instead of accepting the workflow. I found several separate issues: JVM class reloading limitations, Mojarra Facelets caching behavior, JasperReports classloader caching, and GlassFish deployment overhead.
>
> **Action**: I built an internal CLI tool called `gf` that connects to the JVM through JDI/JDWP and hot-swaps modified bytecode directly into the running server, with automatic fallback to full redeployment for structural class changes. Along the way I reverse-engineered parts of Mojarra's Facelets cache implementation and found refresh behavior depended on ProjectStage configuration, and I bypassed JasperReports cache issues by loading report templates directly from exploded deployment paths.
>
> **Result**: Edit-deploy went from about two minutes to roughly five seconds for most changes. The whole team adopted it daily. I open-sourced it and later integrated it into Claude Code workflows for AI-assisted server management.
>
> **What I learned**: understanding systems below the framework layer. The real fix was not more automation scripts; it required tracing JVM behavior, framework caching, and deployment internals end to end.

Tags: critical-problem, proactive, deep-debugging, multiplier, tooling

### 7.2 Owned architecture: E-Appeal

**Situation**: DSI's first large-scale Jakarta EE engagement; no internal template existed for a system of this scope (multi-tenant, audit-trailed, formal approval workflows, government-grade security expectations).
**Task**: technical lead on the architecture; the deliverable was a reusable foundation, not just the app.
**Action**: security model on Jakarta Security with custom form-based auth; package-layout conventions (entities, services, JSF beans, REST resources cleanly separated); CDI/EJB patterns for transactional boundaries (`@Stateless` services, view-scoped CDI beans for UI state); centralized RBAC via a per-request `PermissionEvaluator`; internal architecture doc plus walkthrough sessions.
**Result**: shipped to production at NBR; the conventions were adopted by SHMS, BCIC-ERP, and Project Scratch, so each new project bootstrapped faster.
**Would do differently**: write the patterns down while building, not backfill docs after.
(Public framing: "defined the security model and CDI/EJB conventions"; avoid "foundational architecture".)

### 7.3 Pragmatic tradeoff: distributed locking without Redis

**Situation**: Altri's scheduler runs as multiple Render replicas; uncoordinated, both would race the same enrichment job (double LLM cost, duplicate notifications, corrupted state).
**Action**: built coordination on Postgres instead of adding Redis/Zookeeper: `SELECT FOR UPDATE` to serialize check-then-act, a `RUNNING` lease on the same row, a `JobContext` context manager so locks always release on exception, and 120-minute stale-lock recovery.
**Result**: horizontal scaling with zero new infrastructure, plus a free run-history audit log.
**Considered and rejected**: Redis SETNX+TTL (a stateful service for one feature), Zookeeper (more ops), `pg_advisory_lock` (dies with the connection; no audit trail).
**Lesson**: use what is already there; adding infrastructure is easy, operating it is expensive.

### 7.4 Performance: 10x asyncio refactor

**Situation**: LLM enrichment was sequential (call, await, write, next) and the slowest pipeline stage with thousands of new listings a day.
**Action**: `asyncio.gather` with a semaphore bound (default 5), one reusable async HTTP client per batch, atomic per-batch commits, retry budget with exponential backoff (max 2).
**Result**: ~10x throughput, no increase in 429s, lower per-property cost, crash-safe resume at the last committed batch.
**Rejected**: unbounded gather (rate-limit spiral); Celery/RQ (overkill for one pipeline the scheduler already orchestrates).

### 7.5 Design for reuse: SHMS approval engine

**Situation**: multi-stage approvals needed across hotel licensing, restaurant registration, and more; first instinct was a hardcoded state machine per module.
**Action**: configuration-driven state-machine engine (states, transitions, per-state actions as data); auditing and notifications via CDI interceptors; field-level correction system on top.
**Result**: adopted by multiple DSI projects beyond SHMS; audit history comes free from the interceptor.
**Lesson**: generic engines look like extra work up front and pay off the moment a second project needs the feature.

### 7.6 ML rigor: Champion/Challenger with gold-standard holdout

**Situation**: the valuation model influences real money; silent regressions are unacceptable.
**Action**: train on SOLD listings; hold out a gold-standard slice (C2-condition, low-risk: clean signal); stamp model versions; stage uploads atomically; manual promotion gate with explicit human review before `rescore-all`.
**Result**: caught at least one Challenger that looked fine overall but regressed on the high-confidence slice.
**Framing**: the manual gate is deliberate design for a monetary-impact model, not missing automation.

### 7.7 Mentorship: JEE course at Dynamic Learning

**Situation**: the DSI JEE patterns were valuable but not teachable beyond the firm.
**Action**: authored and teach *Enterprise Web Development with JEE, JSF, and PrimeFaces* (component-driven design, CDI/EJB, JSF lifecycle, RBAC patterns), with a YouTube presence.
**Result**: active since 2024; demonstrates teaching and communication.

### 7.8 EC-BVRS (in progress)

First contribution landed: the data pipeline behind the voter registration flow. Still too thin for a full STAR story. Capture as it develops: how you built a mental model of a system holding ~150 million voter records, what the pipeline actually does, the first incident or review you handled. This becomes the "ramping up on a large unfamiliar system" story.

### 7.9 Evidence over intuition: LLM query router (verbatim-ready)

**Situation**: a hackathon agent had to answer 8 task categories while minimizing paid API tokens under a hard accuracy gate, with a limited number of graded submissions.
**Task**: cut token cost without dropping below the accuracy floor, where a single bad submission is expensive.
**Action**: built a precision-gated cascade (regex router, ONNX classifier, fine-tuned local model, cloud backstop) where each tier only answers what it can prove it handles. Replaced model self-assessment with deterministic guards after measuring that self-reported confidence was unreliable. Built an LLM-as-judge harness mirroring the official rubric so every idea was tested offline first, which killed three plausible-sounding optimizations on measured evidence before they cost a submission.
**Result**: 17 measured releases with root-cause analysis for each regression (a production timeout, an accuracy-gate failure, a token regression from an over-broad regex); immutable Docker tags made every graded build reproducible.
**Why it lands**: it is a story about not trusting your own intuition, or the model's, without measurement.

---

## 8. Technical deep-dives

Whiteboard-ready. Open the day of a technical interview when the topic matches the JD.

### 8.1 Postgres SELECT FOR UPDATE

**Two-sentence summary**: `SELECT ... FOR UPDATE` takes a row-level exclusive lock that serializes the check-then-act on a job's status row, so two replicas cannot both pass the "am I running?" check. The lock is held only during acquisition; the long-lived lease is a status column on the same row, with a wall-clock timeout for crash recovery.

```sql
BEGIN;
SELECT id, job_name, last_status, job_started_at
  FROM pipeline_metadata
  WHERE job_name = 'enrich-new'
  FOR UPDATE;
```

Postgres acquires the exclusive row lock, returns the row, and holds the lock until COMMIT/ROLLBACK. Conflicts with other `FOR UPDATE`/`FOR SHARE`/`UPDATE`/`DELETE` on the row; plain `SELECT` continues via MVCC snapshots.

**Two-replica timeline**: A locks and reads `status='SUCCESS'`; B blocks in the wait queue; A sets `RUNNING`, commits, lock releases; B is granted the lock and reads the post-commit `RUNNING` (READ COMMITTED re-reads locked rows), sees a fresh non-stale lease, and skips cleanly.

**Why MVCC alone fails**: at READ COMMITTED, two plain SELECTs both read the old `SUCCESS`, both UPDATE to `RUNNING`, both run. The bill doubles silently. `FOR UPDATE` forces serialization at the read step. (SERIALIZABLE would catch it as write-skew but needs opt-in plus retry logic; `FOR UPDATE` is the lower-overhead idiom.)

**Stale-lock recovery**: if the holder crashes, the row lock releases (transaction aborts) but the committed `RUNNING` lease survives; a timeout check (`now - job_started_at > 120 min`) lets a fresh worker break it. The breaking path is itself race-free because the second contender waits in the queue and re-reads the fresh `started_at`.

**Follow-ups**: *Why not Redis SETNX?* A stateful service for one feature; Postgres already gives transactional guarantees in use. *Why not advisory locks?* They die with the session; the row approach doubles as run history. *Unhandled failure mode?* Clock skew between replicas; in practice hosts are NTP-synced. *NOWAIT / SKIP LOCKED?* NOWAIT fails fast instead of blocking (not needed); SKIP LOCKED fits work-queue dispatch (e.g. the notifications sender), not a singleton job lock.

### 8.2 JDWP bytecode hot-swap

Primitives: JDI (high-level client API) over JDWP (wire protocol exposed by any JVM started with `-agentlib:jdwp=...`); the swap call is `VirtualMachine.redefineClasses(Map<ReferenceType, byte[]>)`.

`gf` flow: save file, incremental `mvn compile`, attach to the debug port via JDI, build the class-to-bytes map, `redefineClasses`. If JDI rejects (added/removed methods, signature changes, field-structure changes), fall back to `asadmin deploy --force`.

JasperReports bypass: templates load via classloader (`classpath:/reports/...`) and the resource URL is cached; detect `file://` (exploded deployment) vs `jar://` and read directly from the filesystem when exploded.

Mojarra bypass: `FaceletCacheFactoryImpl` honors `FACELETS_REFRESH_PERIOD`, but the default depends on `ProjectStage` (disabled in Production); fix via Maven profile filtering to set `ProjectStage=Development` locally.

### 8.3 Asyncio bounded concurrency

```python
sem = asyncio.Semaphore(5)

async def bounded_task(item):
    async with sem:
        return await process(item)

results = await asyncio.gather(*[bounded_task(i) for i in items])
```

All N coroutines are scheduled cheaply; at most 5 run concurrently. Unbounded gather over 1000 LLM calls hits rate limits and spirals retries. Atomic per-batch commits give a resume point:

```python
for batch in chunks(items, batch_size):
    results = await asyncio.gather(*[task(i) for i in batch])
    db.bulk_update(results)
    db.commit()  # atomic boundary; crash resumes at next batch
```

### 8.4 Content-hash deduplication

MD5 over canonical JSON (sorted keys, fixed separators) of 15 listing fields. Same listing twice = same hash = idempotent upsert, no re-enrichment cost; any field change = new hash = re-enrichment. History is an immutable event log keyed by `property_id`, not hash. MD5 over SHA-256 because it is not a security context; speed and entity-level collision resistance suffice.

### 8.5 CDI interceptors (cross-cutting)

```java
@Auditable
@Stateless
public class ApprovalService { ... }

@Interceptor @Auditable
public class AuditInterceptor {
    @AroundInvoke
    public Object audit(InvocationContext ctx) throws Exception {
        // who/what/when
        Object result = ctx.proceed();
        // outcome
        return result;
    }
}
```

Business code declares `@Auditable` and knows nothing about logging; the interceptor owns the concern. Same pattern for notifications (`@NotifyOnComplete`). Used in SHMS and adopted across DSI JEE projects.

### 8.6 Champion/Challenger validation

Champion serves; Challenger trains on fresh data; evaluate both on a gold-standard holdout (a deeply trusted slice: C2-condition, low-risk) plus the full holdout; a human inspects and explicitly promotes. Manual because valuation is monetary and aggregate metrics can hide slice regressions. Prevents: input distribution shift (LLM feature drift), overfit challengers, silent label corruption.

---

## 9. Question-to-material map

**Behavioral**
- "Tell me about yourself" → 60-second pitch (§1)
- "Critical problem you solved" / "improved something proactively" → 7.1
- "Owned the architecture" → 7.2
- "Pragmatic tradeoff" → 7.3
- "Performance win" → 7.4
- "Prevent regressions in production ML" → 7.6
- "Taught or mentored" → 7.7

**Technical**
- SELECT FOR UPDATE / distributed coordination without Redis → 8.1
- JDWP hot-swap mechanics → 8.2
- Bounded concurrency in asyncio → 8.3
- Three-stage scoring walk-through → 3.1 (Facts, Opinions, Math)
- Malformed LLM output in production → 3.7
- Model versioning and promotion → 3.5

**Systems-design anchors** (when asked to "design X", anchor on something built): notification queue with source discriminator; Postgres job coordination; ingestion with content-hash + delta-sync; hybrid LLM + ML + deterministic scoring.

Per-company prep, negotiation notes, and answers still being drafted live in the private layer (see README).

---

## 10. CV bullet pool

Post-2026-07 rewrite. These follow the writing rules in README.md (one bold max, varied shape, no filler). Pick per JD; the dev CV groups DSI bullets by project prefix.

**EC-BVRS (current; expand as contributions grow, but never with "recently joined" wording)**
- **EC-BVRS:** Contributed to the data pipeline behind the voter registration flow of Bangladesh's national voter registration (NID) platform, which processes records for nearly **150 million voters** (Spring Boot, Kafka, Redis).

**Tooling / gf**
- **Tooling:** Built and open-sourced `gf`, a GlassFish CLI that hot-swaps modified bytecode into running JVMs over JDI/JDWP and bypasses JasperReports classloader caching. Cut local edit-deploy cycles from **~2 minutes to ~5 seconds**.

**E-Appeal**
- **E-Appeal (NBR):** Consolidated authorization checks scattered across JSF views and service code into a single permission-evaluation layer for role-based access control.
- (Site-only, softened version of the retired architecture bullet): Defined the security model, package structure, and CDI/EJB conventions for DSI's first large-scale Jakarta EE system; later JEE projects at the firm adopted these conventions.

**SHMS**
- **SHMS:** Built a configurable approval-workflow engine that replaced hardcoded per-module approval logic. Added a field-level correction flow so reviewers can reopen individual form fields with inline feedback instead of rejecting whole submissions.
- **SHMS:** Introduced Prometheus, Loki, and Grafana observability for GlassFish applications, exposing JVM memory, thread pools, and request latency for production debugging and capacity planning.

**BCIC-ERP**
- **BCIC-ERP:** Replaced base64-inlined file rendering with URL-based streaming behind a pluggable `StorageClient` interface (MinIO or filesystem), cutting page payload size and server memory use. Files are served through nginx X-Accel-Redirect after per-request authorization checks.
- **BCIC-ERP:** Moved SMS and email notifications onto a JMS queue with dead-letter retries, so provider outages no longer block user-facing requests. Led development of the Procurement, Inventory, Asset, and Budget modules (4 of 12), from process modeling and schema design through production rollout.

**Cross-cutting**
- **Cross-project:** Isolated auditing and notification dispatch from business logic with AspectJ cross-cutting interceptors, a pattern reused in multiple Jakarta EE systems.

**Security (research CV and site only; off the dev CV by decision)**
- On the internal Cybersecurity Team, ran static and dynamic security testing against OWASP Top 10 risks and found access-control, injection, and validation flaws before production releases.

**Altri**
- Rewrote the sequential LLM enrichment pipeline as bounded-concurrency async batches with atomic per-batch commits. Throughput rose about **10x**, and failed runs resume without repeating completed LLM calls.
- Designed the three-stage property scoring pipeline that separates LLM feature extraction, ML valuation, and deterministic financial heuristics, so each layer can be retrained and tested on its own.
- Built the property ingestion pipeline on HomeHarvest and PostgreSQL with content-hash deduplication and incremental delta-syncing. Repeated scrapes no longer trigger duplicate enrichment runs, and historical listing state is preserved.
- Implemented distributed job coordination on PostgreSQL with `SELECT FOR UPDATE` row locks and stale-lock recovery, so multiple scheduler replicas safely share long-running enrichment and training jobs.
- Built the training and promotion pipeline for XGBoost property valuation. A challenger must beat the champion on a gold-standard holdout slice, and a human signs off before production-wide rescoring, since aggregate metrics can hide slice regressions and valuation errors cost money.
- (Research-CV variant, folded onto the ingestion bullet) Built the property ingestion pipeline on PostgreSQL with content-hash deduplication and incremental delta-syncing, so repeated scrapes skip already-enriched listings while preserving historical state. Model promotion is gated the same way: a challenger must beat the champion on a gold-standard holdout slice, and a human signs off before production-wide rescoring.

**Projects**
**Token-Efficient LLM Query Router** (AMD Hackathon Act II, Track 1). Canonical three-bullet form, identical on both CVs as of 2026-07-30; the earlier two-bullet version was too dense to read at a glance:
- Designed a four-tier inference cascade (regex router → ONNX classifier → LoRA fine-tuned Qwen2.5-1.5B → cloud LLM fallback) that resolves 8 task categories with minimal paid API usage, admitting each tier only at measured precision (router 64/64 on adversarial cases; sentiment classifier 100%).
- Replaced model confidence checks with deterministic verification guards: sandboxed AST evaluation of model-emitted math expressions, which removes arithmetic errors and cuts output tokens ~90%, and an entity-completeness check that catches 99% of dropped entities in NER.
- Fine-tuned the local tier on 2,800 programmatically validated synthetic examples and iterated 17 times against an LLM-as-judge harness mirroring the competition rubric, root-causing each regression before redeploy.

Attribution rule for this project: the **~90% token cut belongs to program-aided math specifically**, not to the guards collectively; the **self-assessment contrast appears once**, in the guards bullet. Details that came off the CVs but stay interview-ready in §4.4: runtime speed calibration, immutable Docker tags per submission, the three named regressions, and the offline experiments that killed ideas before they cost a submission.
- **KnowledgeRelay**: Built a knowledge-transfer agent that interviews outgoing team members with adaptive questions, ingests their documents and code, and answers new joiners' questions with source attribution. Retrieval rewrites follow-ups into self-contained queries; chunking differs for code and prose.

**Retired bullets (do not resurrect)**
- "Built the foundational architecture for DSI's first large-scale Jakarta EE system..." (retired 2026-07; use the concrete E-Appeal version above)
- "Recently joined... currently deep-diving the system architecture" for EC-BVRS (retired 2026-07-29; goes stale, and understates the contribution)
- "Built a RAG-based knowledge transfer system: multi-stage ingestion generates structured QA pairs from documents..." for KnowledgeRelay (retired 2026-07-29; described only the document flow and missed the outgoing-member interview, which is the point of the project)
- Bold-heavy variants of any bullet above (pre-review style: 16 bolded terms per section, uniform "-ing" tails)

---

## 11. CV-editing lessons from the 2026-07 review

- **Strongest material**: the gf bullet (concrete, quantified, verifiable, below-the-framework depth), the 10x async rewrite, `SELECT FOR UPDATE` coordination (honest scope: "on Postgres"), and the merged PrimeFaces/SREGym PRs. Lead with these.
- **Weakest material**: walls of uniform bolded bullets; long publication listings on a dev resume; student-era honors.
- **Identity framing**: systems engineer who works in JEE, with gf as the proof of JVM-level depth.
- **Structure that works**: group bullets by project with one-line scope; each fact once per document; skills lists only claim what a bullet or project backs; Google Scholar link last in the dev CV header.
