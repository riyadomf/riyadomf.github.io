---
layout: archive
title: "Job Experience"
permalink: /job-experience/
author_profile: true
---

I am a Software Engineer and AI Engineer with experience shipping production ML systems, enterprise applications, and secure infrastructure. My work spans the full stack — from architecting hybrid AI pipelines to engineering mission-critical government systems.

---

## ALTRI.AI
**AI Engineer** | *October 2025 – Present* | Remote, US

Building production AI systems for real estate investment analysis, combining modern LLMs with traditional ML to deliver actionable insights at scale.

<div class="highlight-box" markdown="1">

**Key Impact:** Achieved a **10× throughput increase** by refactoring data enrichment pipelines with async orchestration, significantly reducing cloud compute costs.

</div>

### Core Contributions

*   **Hybrid AI Scoring Engine:** Architected an engine combining LLM-based feature extraction from unstructured property descriptions with XGBoost models for price prediction and investment recommendations.
*   **Fault-Tolerant Ingestion:** Built a resilient data ingestion engine using HomeHarvest and PostgreSQL, implementing a "Delta Sync" strategy with immutable event logging to track property lifecycles without data loss.
*   **Model Validation Pipeline:** Established a containerized training pipeline with Human-in-the-Loop validation gates, ensuring new "Challenger" models consistently outperform production "Champions" before deployment.
*   **Full-Stack Development:** Developed a FastAPI backend and React frontend backed by Supabase, implementing Row Level Security (RLS) and distributed job locking for safe, multi-tenant concurrency.
*   **Infrastructure & DevOps:** Dockerized the complete microservices stack (API, Scheduler, Trainer) for reproducible deployments across local environments and Render cloud infrastructure.

---

## DYNAMIC SOLUTION INNOVATORS
**Software Engineer** | *April 2023 – Present* | Dhaka, Bangladesh

Core member of the engineering team, designing and building mission-critical enterprise systems for major government and public sector clients. Focus on backend architecture, security, and operational excellence.

<div class="highlight-box" markdown="1">

**Key Impact:** Slashed redeployment latency by **96% (2m → 5s)** by resolving a critical GlassFish hot-swap failure, accelerating team-wide development speed.

</div>

### Core Contributions

*   Engineered secure and scalable **Java EE** applications for critical government infrastructures (NBR, MoCAT, BCIC), transforming complex bureaucratic processes into streamlined digital workflows.
*   Acted as a key member of the **internal cybersecurity team**, conducting vulnerability assessments, threat modeling, and security audits across projects.

### Key Projects

<div class="experience-card" markdown="1">

#### **E-Appeal: Digital Appeals System for NBR & USAID**
*A digital platform for managing tax-related appeals.*

*   **Pioneered the company's first enterprise-scale JSF application**, establishing engineering guidelines and architectural best practices adopted by subsequent projects.
*   Designed a **multi-layer architecture** (View, Service, Repository) with strict separation of concerns.
*   Implemented **centralized RBAC** using Jakarta Security with custom form-based authentication.
*   Integrated **Java Message Service (JMS)** for asynchronous, decoupled event handling (email/SMS notifications).

</div>

<div class="experience-card" markdown="1">

#### **Project Scratch: Internal Core Services Platform**
*An internal platform designed to accelerate development by providing reusable core services.*

*   **Engineered a centralized observability stack** using Prometheus, Loki, and Grafana — exposing JMX metrics from GlassFish for real-time monitoring.
*   **Dockerized the complete application stack** (GlassFish, PostgreSQL, MinIO, RabbitMQ).
*   **Contributed a feature enhancement to PrimeFaces open-source** (<a href="https://github.com/primefaces/primefaces/pull/12865" target="_blank" rel="noopener noreferrer">PR #12865</a>).

</div>

<div class="experience-card" markdown="1">

#### **SHMS: Smart Hotel Management System**
*A nationwide licensing and registration system for hotels and restaurants.*

*   Designed a generic, **state-driven approval workflow engine**, making the logic reusable across multiple application types.
*   Utilized **Aspect-Oriented Programming (AOP)** to cleanly separate cross-cutting concerns like notifications and auditing from core business logic.

</div>

<div class="experience-card" markdown="1">

#### **BCIC-ERP: End-to-End Enterprise Resource Planning**
*A comprehensive ERP system for process automation across 12 integrated modules.*

*   **Assumed full ownership of the Procurement and Inventory modules**, leading the entire lifecycle from business analysis (As-Is/To-Be modeling) and database schema design to hands-on development and client delivery.

</div>

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