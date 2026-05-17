---
layout: archive
title: "Projects & Open Source"
permalink: /projects/
author_profile: true
---

Selected projects demonstrating my work across AI/ML systems, enterprise engineering, and full-stack development.

---

<div class="experience-card" markdown="1">

### **gf: GlassFish Dev Workflow CLI**
<small>2026 | <a href="https://github.com/riyadomf/glassfish-hotswap-cli" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

<span class="achievement-badge">⚡ 96% Faster Dev Cycles (2m → 5s)</span>

A cross-platform GlassFish development CLI that replaces IDE-driven deployment workflows with terminal-first hot-swap and AI-assisted server management.

*   **JDWP Bytecode Hot-Swap:** Built a JDI-based hot-swap client that injects modified bytecode into running JVMs with automatic fallback to full redeployment on structural class changes.
*   **JVM & Framework Reverse Engineering:** Diagnosed GlassFish XHTML staleness by tracing Mojarra Facelets cache internals and identifying `ProjectStage`-dependent refresh behavior.
*   **JasperReports Hot Reloading:** Bypassed JasperReports classloader caching by resolving report resources directly from exploded deployment paths.
*   **AI-Augmented Workflow:** Integrated as a Claude Code skill (`/gf`) enabling AI-driven deployment, server lifecycle management, and hot-swap operations from natural-language commands.
*   **Stack:** Bash, Java (JDI/JDWP API), GlassFish 8, rsync, Claude Code Skills

</div>


<div class="experience-card" markdown="1">

### **KnowledgeRelay: AI Knowledge Transfer Agent**
<small>2025 | <a href="https://github.com/riyadomf/knowledgeRelay" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

<span class="achievement-badge">🏆 6th Place — DSI AI Agent Hackathon 2025</span>

A Retrieval-Augmented Generation (RAG) system built during a 24-hour onsite hackathon to preserve institutional knowledge and assist onboarding engineers through contextual Q&A.

*   **Multi-Stage Knowledge Ingestion:** Generated structured QA pairs from internal documents to improve retrieval quality beyond direct vector similarity search.
*   **Context-Aware Retrieval:** Implemented conversational query rewriting using chat history for more accurate follow-up question handling.
*   **Hybrid Local/Cloud LLM Support:** Supported both OpenAI APIs and locally hosted Ollama models for flexible deployment.
*   **Stack:** Python, FastAPI, LangChain, ChromaDB, OpenAI, Ollama, React

</div>

<div class="experience-card" markdown="1">

### **Open Source: PrimeFaces JPALazyDataModel Enhancement**
<small>2024 | <a href="https://github.com/primefaces/primefaces/pull/12865" target="_blank" rel="noopener noreferrer">View Pull Request #12865</a></small>

<span class="achievement-badge">🔧 Merged into Official Library</span>

Contributed a feature enhancement to PrimeFaces, a widely used open-source JSF component library.

*   **Custom Filter Injection:** Added support for injecting custom `FilterMeta` into `JPALazyDataModel`, enabling advanced filtering beyond the stock component behavior.
*   **Framework Integration:** Extended the DataTable filtering pipeline while preserving compatibility with existing PrimeFaces query generation patterns.
*   **Stack:** Java, Jakarta EE (JSF), PrimeFaces, JPA

</div>

<div class="experience-card" markdown="1">

### **Shopaholic: E-Commerce Marketplace**
<small>2022 | <a href="https://github.com/Nowshadjunaed/Shopaholic" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

A full-stack e-commerce platform connecting customers, suppliers, and partner banks with inventory and order management capabilities.

*   Built REST APIs for authentication, product management, and order workflows using Node.js and Express.js.
*   Developed a React/Redux frontend with MongoDB-backed inventory and transaction management.
*   **Stack:** JavaScript, Node.js, Express.js, MongoDB, React, Redux

</div>


<!--
### **FUTURE PROJECT TITLE**
<small>YEAR | <a href="#">GitHub Repository</a></small>

<small>*A brief, italicized description of the project's goal.*</small>

*   Contribution 1: Describe a key feature or problem you solved.
*   Contribution 2: Mention another impressive technical detail.

**Stack:** Tech 1, Tech 2, Tech 3
-->