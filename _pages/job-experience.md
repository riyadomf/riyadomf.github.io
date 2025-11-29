---
layout: archive
title: "Job Experience"
permalink: /job-experience/
author_profile: true
---

I am a Software Engineer and AI Engineer with experience building production-grade ML systems, enterprise applications, and secure infrastructure. My work spans the full stack—from architecting hybrid AI pipelines to engineering mission-critical government systems.

---

## ALTRI.AI
**AI Engineer** | *October 2025 – Present* | Remote, US

I design and build production AI systems for real estate investment analysis, combining modern LLMs with traditional ML to deliver actionable insights at scale.

### Core Responsibilities

*   **Hybrid AI Scoring Engine**: Architected a hybrid AI scoring engine combining LLM-based feature extraction from unstructured property descriptions with traditional ML models for price prediction and investment recommendations.
*   **Pipeline Optimization**: Refactored the data enrichment pipeline using **Python asyncio**, achieving a **10x throughput increase** and significantly reducing cloud compute costs by parallelizing I/O-bound LLM operations.
*   **Fault-Tolerant Ingestion**: Built a resilient data ingestion engine using HomeHarvest and PostgreSQL, implementing a "Delta Sync" strategy with immutable event logging to track property lifecycles without data loss.
*   **Model Validation Pipeline**: Established a containerized training pipeline with Human-in-the-Loop validation gates, ensuring new "Challenger" models consistently outperform production "Champions" before deployment.
*   **Full-Stack Development**: Developed a FastAPI backend and React frontend backed by Supabase, implementing Row Level Security (RLS) and distributed job locking for safe, multi-tenant concurrency.
*   **Infrastructure & DevOps**: Dockerized the complete microservices stack (API, Scheduler, Trainer) for reproducible deployments across local environments and Render cloud infrastructure.

---

## DYNAMIC SOLUTION INNOVATORS
**Software Engineer** | *April 2023 – Present* | Dhaka, Bangladesh

As a core member of the engineering team, I design and build mission-critical enterprise systems for major government and public sector clients. My role encompasses the full software development lifecycle, with a strong focus on backend architecture, security, and operational excellence.

### Core Responsibilities

*   Engineered secure and scalable **Java EE** applications for critical government infrastructures (NBR, MoCAT, BCIC), translating complex offline bureaucratic processes into streamlined digital workflows.
*   Acted as a key member of the **internal cybersecurity team**, conducting vulnerability assessments, threat modeling sessions, and security audits across organizational projects.
*   Optimized team-wide development speed by resolving a critical GlassFish hot-swap failure, **slashing redeployment latency by 96% (2m → 5s)**.

### Key Projects

#### **E-Appeal: Digital Appeals System for NBR & USAID**
*A digital platform for managing tax-related appeals.*

*   **Pioneered the company's first enterprise-scale JSF application**, establishing engineering guidelines and architectural best practices that became the standard for subsequent projects.
*   Designed and implemented a **multi-layer architecture** (View, Service, Repository) with strict separation of concerns.
*   Implemented a **centralized RBAC security model** using Jakarta Security with custom form-based authentication.
*   Integrated **Java Message Service (JMS)** for asynchronous, decoupled event handling (email/SMS notifications), improving system resilience and fault tolerance.

#### **Project Scratch: Internal Core Services Platform**
*An internal platform designed to accelerate development by providing reusable core services.*

*   **Engineered a centralized observability stack** using Prometheus, Loki, and Grafana. Exposed JMX metrics from GlassFish to a Prometheus endpoint for real-time application and infrastructure monitoring.
*   **Dockerized the complete application stack**, including GlassFish, PostgreSQL, MinIO, and RabbitMQ, creating a portable development environment.
*   **Developed a reusable Lazy Data Model component** for PrimeFaces and successfully **contributed a related feature enhancement to the official PrimeFaces open-source library** (<a href="https://github.com/primefaces/primefaces/pull/12865" target="_blank" rel="noopener noreferrer">PR #12865</a>).

#### **SHMS: Smart Hotel Management System**
*A nationwide licensing and registration system for hotels and restaurants.*

*   Contributed to the design and implementation of a generic, **state-driven approval workflow** engine, making the logic reusable across multiple application types and minimizing code duplication.
*   Utilized **Aspect-Oriented Programming (AOP)** principles to cleanly separate cross-cutting concerns like notifications and auditing from core business logic.

#### **BCIC-ERP: End-to-End Enterprise Resource Planning**
*A comprehensive ERP system for process automation across 12 integrated modules.*

*   **Assumed full ownership of the Procurement and Inventory modules**, leading its entire lifecycle from business analysis (As-Is/To-Be modeling) and database schema design to hands-on development and successful client delivery.

---

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