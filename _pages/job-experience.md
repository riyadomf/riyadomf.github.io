---
layout: archive
title: "Job Experience"
permalink: /job-experience/
author_profile: true
---

I build backend systems, AI infrastructure, and enterprise applications. My work spans government-scale Enterprise systems, distributed data pipelines, and production ML workflows.


---


## DYNAMIC SOLUTION INNOVATORS
**Software Engineer** | *April 2023 – Present* | Dhaka, Bangladesh

Core member of the engineering team building large-scale enterprise systems for government and public-sector clients, with a focus on backend architecture, security, and operational reliability.

<div class="highlight-box" markdown="1">

**Key Impact:** Built and open-sourced <a href="https://github.com/riyadomf/glassfish-hotswap-cli" target="_blank" rel="noopener noreferrer">`gf`</a>, a GlassFish development CLI that hot-swaps bytecode into running JVMs via JDI/JDWP and bypasses JasperReports classloader caching, reducing local edit-deploy cycles from **~2 minutes to ~5 seconds**.

</div>


<!-- <div class="experience-card" markdown="1">

#### **EC-BVRS: Bangladesh Voter Registration System**
*Bangladesh's national voter registration (NID) platform, built on Spring Boot, Kafka, Apache Kudu, and Redis.*

*   Contributed to the **data pipeline** behind the voter registration flow, which processes records for nearly **150 million voters**.
*   Resolved a **production incident** blocking payment processing after the Kafka pipeline fell **500,000 events behind**; traced recurring **consumer group rebalances** to slow Kudu writes and reduced batch size to restore consumer liveness and clear the backlog.
*   The symptoms and the cause sat in different components: Kafka kept evicting a consumer that was healthy, because each batch was waiting on Kudu writes. Tuning Kafka alone would never have reached it.

</div> -->

<div class="experience-card" markdown="1">

#### **E-Appeal: Digital Appeals System for NBR & USAID**
*A digital platform for managing tax-related appeals.*

*   Defined the security model, package structure, and CDI/EJB conventions for DSI's first large-scale Jakarta EE system; later JEE projects at the firm adopted these conventions.
*   Centralized **RBAC enforcement** by replacing authorization checks scattered across JSF views and services with a unified permission-evaluation layer.

</div>

<div class="experience-card" markdown="1">

#### **SHMS: Smart Hotel Management System** *(built on Project Scratch platform)*
*A nationwide licensing and registration system for hotels and restaurants, developed on DSI's internal core-services platform.*

*   Designed a reusable **approval-workflow engine** backed by configurable state transitions, replacing hardcoded per-module approval logic. Engineered a **dynamic field-level correction system** enabling reviewers to reopen only selected form fields with inline feedback while preserving audit history.
*   Introduced centralized **observability** for GlassFish applications using **Prometheus, Loki, and Grafana**, exposing JVM memory, thread pools, and request latency for production debugging and capacity monitoring.
*   Isolated auditing and notification dispatch from business logic using **AspectJ-based cross-cutting interceptors**, establishing a reusable pattern across multiple Jakarta EE systems.

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

*   Designed the **three-stage property scoring pipeline** that separates LLM feature extraction, valuation models, and deterministic financial heuristics, so each layer can be retrained and tested on its own.
*   Built the property ingestion pipeline on **HomeHarvest** and **PostgreSQL** with content-hash deduplication and incremental delta-syncing. Repeated scrapes no longer trigger duplicate enrichment runs, and historical listing state is preserved.
*   Implemented **distributed job coordination on PostgreSQL** using **`SELECT FOR UPDATE`** row-level locks with automatic stale-lock recovery, so multiple scheduler replicas safely process long-running enrichment and training jobs.
*   Built the ML training and promotion pipeline with **Champion/Challenger validation**. A challenger must beat the champion on a gold-standard holdout slice, and a human signs off before production-wide rescoring, since aggregate metrics can hide slice regressions and valuation errors cost money.

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
