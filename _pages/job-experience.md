---
layout: archive
title: "Job Experience"
permalink: /job-experience/
author_profile: true
---

I build backend systems, AI infrastructure, and enterprise applications with a focus on correctness, operational reliability, and maintainable architecture. My work spans government-scale Jakarta EE systems, distributed data pipelines, and production ML workflows.


---


## DYNAMIC SOLUTION INNOVATORS
**Software Engineer** | *April 2023 – Present* | Dhaka, Bangladesh

Core member of the engineering team building large-scale enterprise systems for government and public-sector clients, with a focus on backend architecture, security, and operational reliability.

<div class="highlight-box" markdown="1">

**Key Impact:** Built and open-sourced <a href="https://github.com/riyadomf/glassfish-hotswap-cli" target="_blank" rel="noopener noreferrer">`gf`</a>, a GlassFish development CLI that hot-swaps bytecode into running JVMs via JDI/JDWP and bypasses JasperReports classloader caching, reducing local edit-deploy cycles from **~2 minutes to ~5 seconds**.

</div>

### Core Contributions

*   Isolated auditing and notification dispatch from business logic using **AspectJ-based cross-cutting interceptors**, establishing a reusable pattern across multiple Jakarta EE systems.
*   Performed application security reviews and **static/dynamic testing against OWASP Top 10** risks as part of the internal Cybersecurity Team, identifying access-control, injection, and validation flaws before production release.


<div class="experience-card" markdown="1">

#### **E-Appeal: Digital Appeals System for NBR & USAID**
*A digital platform for managing tax-related appeals.*

*   Built the **foundational architecture** for DSI's first large-scale Jakarta EE system, defining the security model, package structure, and CDI/EJB conventions later reused across subsequent JEE projects at the firm.
*   Centralized **RBAC enforcement** by replacing authorization checks scattered across JSF views and services with a unified permission-evaluation layer.

</div>

<div class="experience-card" markdown="1">

#### **SHMS: Smart Hotel Management System** *(built on Project Scratch platform)*
*A nationwide licensing and registration system for hotels and restaurants, developed on DSI's internal core-services platform.*

*   Designed a reusable **approval-workflow engine** backed by configurable state transitions, replacing hardcoded per-module approval logic. Engineered a **dynamic field-level correction system** enabling reviewers to reopen only selected form fields with inline feedback while preserving audit history.
*   Introduced centralized **observability** for GlassFish applications using **Prometheus, Loki, and Grafana**, exposing JVM memory, thread pools, and request latency for production debugging and capacity monitoring.

</div>

<div class="experience-card" markdown="1">

#### **BCIC-ERP: End-to-End Enterprise Resource Planning**
*A comprehensive ERP system for process automation across 12 integrated modules.*

*   Re-architected file storage and delivery behind a pluggable **`StorageClient`** abstraction supporting MinIO and filesystem backends, replacing base64-inlined file rendering with URL-based streaming to eliminate large HTML payloads and reduce server-side memory pressure. Added scoped file authorization and **nginx `X-Accel-Redirect`** offloading for efficient file serving.
*   Designed a **JMS-based notification pipeline** with DLQ-backed retries, isolating SMS/email failures from the synchronous request path.
*   Led development of the **Procurement, Inventory, Asset, and Budget** modules of BCIC-ERP, including process modeling, schema design, backend implementation, and production rollout.

</div>

---


## ALTRI.AI
**Full-Stack AI Engineer**, RevestAI (<a href="https://revestai.com" target="_blank" rel="noopener noreferrer">revestai.com</a>) | Part-time, Remote (US)

Building AI-assisted real estate analysis systems that combine LLM-based enrichment, traditional ML valuation, and large-scale property ingestion pipelines.

<div class="highlight-box" markdown="1">

**Key Impact:** Achieved **~10× throughput** on LLM data enrichment by rebuilding the pipeline around bounded-concurrency **`asyncio.gather`** with atomic per-batch commits.

</div>

### Core Contributions

*   Designed the **three-stage property scoring pipeline** separating LLM feature extraction, valuation models, and deterministic financial heuristics, enabling each layer to be independently retrained and tested.
*   Rebuilt the LLM enrichment pipeline around **`asyncio.gather`** with bounded concurrency and atomic batch commits, allowing failed batches to resume without reprocessing completed LLM calls and improving throughput by **~10×** over the prior sequential pipeline.
*   Built the property ingestion pipeline on **HomeHarvest** and **PostgreSQL** using content-hash deduplication and incremental delta-syncing, preventing duplicate enrichment runs while preserving historical listing state across repeated scrapes.
*   Implemented **distributed job coordination on PostgreSQL** using **`SELECT FOR UPDATE`** locks with automatic stale-lock recovery, allowing multiple scheduler replicas to safely process long-running enrichment and training jobs.
*   Built the ML training pipeline with **Champion/Challenger validation** on a curated holdout datasets and a manual promotion gate, preventing unverified models from triggering production-wide rescoring.

<!-- 
###
**FUTURE COMPANY NAME**
**Your Title** | *Start Date – End Date* | Location

*   Responsibility 1
*   Responsibility 2

#### **Key Project Name**
*A brief, italicized description of the project.*

*   Accomplishment 1: Describe the problem, the action you took, and the positive result.
*   Accomplishment 2: Use strong verbs and quantify your impact where possible.
-->
