---
layout: archive
title: "Projects & Open Source"
permalink: /projects/
author_profile: true
---

Selected projects demonstrating my work across AI/ML systems, enterprise engineering, and full-stack development.

---

<div class="experience-card" markdown="1">

### **KnowledgeRelay: AI-Based Knowledge Transfer Agent**
<small>2025 | <a href="https://github.com/riyadomf/knowledgeRelay" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

<span class="achievement-badge">🏆 6th Place — DSI AI Agent Hackathon 2025</span>

A Retrieval-Augmented Generation (RAG) system that preserves institutional knowledge and assists new team members through contextual Q&A. Built in a 24-hour onsite hackathon.

*   **Multi-Stage Ingestion Pipeline:** Automated QA-pair generation from documents to enhance retrieval accuracy beyond naive vector search.
*   **Conversational Context:** Implemented a contextualized retrieval chain that uses chat history to intelligently rephrase follow-up questions.
*   **Stack:** Python, FastAPI, LangChain, ChromaDB, OpenAI, Ollama, React

</div>

<div class="experience-card" markdown="1">

### **Open Source: PrimeFaces JPALazyDataModel Enhancement**
<small>2024 | <a href="https://github.com/primefaces/primefaces/pull/12865" target="_blank" rel="noopener noreferrer">View Pull Request #12865</a></small>

<span class="achievement-badge">🔧 Merged into Official Library</span>

Contributed a feature enhancement to PrimeFaces (12k+ ★ on GitHub), the leading open-source JSF component library.

*   **Custom Filter Injection:** Added the ability to inject custom `FilterMeta` into `JPALazyDataModel`, enabling advanced filtering capabilities beyond what the stock component offers.
*   **Developer Impact:** Allows complex, customizable filtering within PrimeFaces DataTables — used by thousands of enterprise applications globally.
*   **Stack:** Java, Jakarta EE (JSF), PrimeFaces, JPA

</div>

<div class="experience-card" markdown="1">

### **gf: GlassFish Dev Workflow CLI**
<small>2026 | <a href="https://github.com/riyadomf/glassfish-hotswap-cli" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

<span class="achievement-badge">⚡ 96% Faster Dev Cycles (2m → 5s)</span>

A cross-platform CLI tool for GlassFish development that replaces IntelliJ's GlassFish plugin with a terminal-first, AI-integrated workflow. Built by reverse-engineering JVM and Mojarra internals.

*   **JDWP Bytecode Hot-Swap:** Built a JDI-based hot-swap client (`HotSwap.java`) that connects to the running JVM's debug port and atomically swaps bytecode of changed classes in memory — with automatic fallback to full redeployment on structural changes.
*   **Root Cause Analysis via Bytecode:** Diagnosed GlassFish 8 XHTML staleness by decompiling Mojarra 4.1.6's `FaceletCacheFactoryImpl` — discovered `ProjectStage`-aware `FACELETS_REFRESH_PERIOD` defaults, and solved it via Maven profile filtering.
*   **Classloader Cache Bypass:** Enabled `.jrxml` (JasperReports) hot-reload by detecting `file://` vs `jar://` resource URLs and reading directly from the filesystem in exploded deployments.
*   **AI-Augmented Workflow:** Integrated as a Claude Code skill (`/gf`), enabling AI-driven server lifecycle management, deployment, and hot-swap from natural language.
*   **Stack:** Bash, Java (JDI/JDWP API), rsync, GlassFish 8, Claude Code Skills

</div>

<div class="experience-card" markdown="1">

### **Shopaholic: Full-Stack E-commerce Platform**
<small>2022 | <a href="https://github.com/Nowshadjunaed/Shopaholic" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

A full-stack e-commerce marketplace connecting customers, partner banks, and suppliers with real-time inventory management.

*   **RESTful API Backend:** Developed using Node.js and Express.js with user authentication, product management, and order processing.
*   **Database Design:** Designed MongoDB schemas to manage relationships between users, products, orders, and payment transactions.
*   **Reactive Frontend:** Built a responsive UI using React and Redux for global state management.
*   **Stack:** JavaScript, Node.js, Express.js, MongoDB, React, Redux

</div>

<div class="experience-card" markdown="1">

### **Brevity: Knowledge-Sharing Blog Platform**
<small>2021 | <a href="https://github.com/riyadomf/Brevity" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

A responsive blog platform connecting beginners with experts for mentorship and knowledge sharing.

*   **Full-Stack Implementation:** Built with Python/Flask backend, MySQL database, and vanilla JS frontend.
*   **Core Features:** User authentication, CRUD operations, commenting system, and user profile management.
*   **Stack:** Python, Flask, MySQL, JavaScript, HTML, CSS

</div>

<!--
### **FUTURE PROJECT TITLE**
<small>YEAR | <a href="#">GitHub Repository</a></small>

<small>*A brief, italicized description of the project's goal.*</small>

*   Contribution 1: Describe a key feature or problem you solved.
*   Contribution 2: Mention another impressive technical detail.

**Stack:** Tech 1, Tech 2, Tech 3
-->