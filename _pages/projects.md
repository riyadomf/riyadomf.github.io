---
layout: archive
title: "Projects & Open Source"
permalink: /projects/
author_profile: true
---

Selected projects demonstrating my work across AI/ML systems, enterprise engineering, and full-stack development.

---

<div class="experience-card" markdown="1">

### **Open Source: SREGym Fault Scenario Contribution**
<small>2026 | <a href="https://github.com/SREGym/SREGym/pull/886" target="_blank" rel="noopener noreferrer">Merged PR #886</a></small>

<span class="achievement-badge">🔧 Merged into SREGym (AI SRE Benchmark)</span>

Contributed a fault scenario to **SREGym**, an open-source benchmark for evaluating AI agents on realistic system failures.

*   **Reproduced a real Kubernetes incident:** modeled a documented admission-control failure (<a href="https://github.com/kubernetes/kubernetes/issues/128162" target="_blank" rel="noopener noreferrer">issue #128162</a>) where multiple mutating admission webhooks' cumulative timeouts exceed the API server's global admission deadline, silently blocking all pod creation with no crash.
*   **Realistic, agent-resistant design:** used real HTTPS admission servers and ecosystem-named decoy webhooks (not dummy backends) so agents can't dismiss the setup, plus a deliberate "near-miss" policy that looks corrective but fails.
*   **Reward-hack-resistant oracle:** built a four-property mitigation oracle culminating in a fresh probe-pod admission test that rejects fixes masking the symptom (e.g., deleting all webhooks) without restoring the required control-plane path.
*   **Stack:** Python, Kubernetes (admission webhooks, NetworkPolicy, RBAC), Docker/kind

</div>

<div class="experience-card" markdown="1">

### **gf: GlassFish Dev Workflow CLI**
<small>2026 | <a href="https://github.com/riyadomf/glassfish-hotswap-cli" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

<span class="achievement-badge">⚡ Edit-Deploy Cycles: 2 min → 5 s</span>

A cross-platform GlassFish development CLI that replaces IDE-driven deployment workflows with terminal-first hot-swap and AI-assisted server management.

*   **JDWP Bytecode Hot-Swap:** Built a JDI-based hot-swap client that injects modified bytecode into running JVMs with automatic fallback to full redeployment on structural class changes.
*   **JVM & Framework Reverse Engineering:** Diagnosed GlassFish XHTML staleness by tracing Mojarra Facelets cache internals and identifying `ProjectStage`-dependent refresh behavior.
*   **JasperReports Hot Reloading:** Bypassed JasperReports classloader caching by resolving report resources directly from exploded deployment paths.
*   **AI-Augmented Workflow:** Integrated as a Claude Code skill (`/gf`) enabling AI-driven deployment, server lifecycle management, and hot-swap operations from natural-language commands.
*   **Stack:** Bash, Java (JDI/JDWP API), GlassFish 8, rsync, Claude Code Skills

</div>


<div class="experience-card" markdown="1">

### **Token-Efficient LLM Query Router**
<small>2026 | AMD Hackathon Act II, Track 1 | <a href="https://github.com/riyadomf/llm-query-router" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

<span class="achievement-badge">⚙️ Precision-Gated Cascade: Zero-Token Tiers First</span>

An agent that answers 8 task categories (factual Q&A, math, sentiment, summarization, NER, code debugging, logic, code generation) while minimizing paid API token spend under a hard accuracy gate.

*   **Precision-gated cascade:** a zero-token regex router (64/64 on dev and adversarial paraphrases), then a non-generative ONNX sentiment classifier shipped only after measuring 100% precision, then a LoRA fine-tuned Qwen2.5-1.5B for local factual Q&A and NER, with a cloud model as accuracy backstop. Each tier answers only what it can prove it handles; everything uncertain escalates.
*   **Program-aided math:** instead of having the model compute, it emits a symbolic expression evaluated by a sandboxed AST interpreter. Arithmetic errors disappear as a category and output tokens drop about 90%.
*   **Verification guards over self-assessment:** model-reported confidence measured unreliable at this scale, so local answers pass deterministic checks instead. An entity-completeness check catches 99% of dropped entities in NER output.
*   **Runtime speed calibration:** detects the grading host's actual throughput and enables a local tier only when it can finish in time.
*   **Evidence-driven iteration:** an offline LLM-as-judge harness mirroring the official rubric tested every change before a submission was spent, across 17 measured releases with root-cause analysis for a production timeout, an accuracy-gate failure, and a token regression from an over-broad regex. Immutable Docker tags per submission kept every graded build reproducible.
*   **Stack:** Python, PyTorch, Unsloth/LoRA, ONNX Runtime, Docker, Fireworks API

</div>

<div class="experience-card" markdown="1">

### **KnowledgeRelay: AI Knowledge Transfer Agent**
<small>2025 | <a href="https://github.com/riyadomf/knowledgeRelay" target="_blank" rel="noopener noreferrer">GitHub Repository</a></small>

<span class="achievement-badge">🏆 6th Place, DSI AI Agent Hackathon 2025</span>

Built in a 24-hour onsite hackathon to solve a problem every team has: when someone leaves, the unwritten knowledge leaves with them. The agent captures that knowledge before departure, then answers new joiners' questions from it.

*   **Adaptive knowledge capture:** interactively prompts an outgoing member with context-aware questions generated from the ongoing conversation, so the knowledge base is built by interview rather than by hoping someone writes documentation.
*   **Document and code ingestion:** extracts knowledge from uploaded PDFs, Word files, and source code, with separate chunking strategies for code and prose.
*   **Grounded retrieval:** rewrites follow-up questions into self-contained queries using prior conversation context, and attributes every answer back to its source file.
*   **Hybrid local/cloud LLMs:** runs against OpenAI APIs or locally hosted Ollama models.
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