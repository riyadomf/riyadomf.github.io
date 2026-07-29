---
layout: archive
title: "Research Experience"
permalink: /research-experience/
author_profile: true
---

I work on AI agents for site reliability engineering and software engineering, and on NLP for low-resource languages. I have three shared-task papers at workshops co-located with EMNLP 2023, NAACL 2024, and IJCNLP-AACL 2025, and I currently contribute to SREGym, an open-source benchmark for AI-driven site reliability engineering.

---

<div class="experience-card" markdown="1">

### **Agentic Site Reliability Engineering: AI for SRE**
<small>2026 | Research Intern, advised by Prof. Tianyin Xu (UIUC)</small>

<span class="achievement-badge">🔬 Contributing to SREGym, a Benchmark for AI SRE Agents</span>

*   Working on the **SREGym v2 paper**: extending SREGym, an open-source benchmark for evaluating AI agents on cloud-native system failures, from synthetic faults to real-world failure scenarios, and analyzing how agents behave on them.
*   Conducting case studies and postmortem analysis of real-world outages, projecting them into reproducible benchmark problems.
*   Designing fault scenarios and evaluation oracles that expose documented agent weaknesses: cross-layer reasoning gaps, greedy diagnosis anchoring, and reward hacking.
*   Contributed a merged fault scenario reproducing a real Kubernetes admission-control incident, with a reward-hack-resistant evaluation oracle (details on the [Projects](/projects/) page).

</div>

<div class="experience-card" markdown="1">

### **Code Generation in Bangla: Low-Resource Language Adaptation**
<small>2025 | Shared Task at the BLP Workshop, co-located with IJCNLP-AACL</small>

<span class="achievement-badge">🏆 4th Place out of 32 Teams (Pass@1 0.85)</span>

*   Investigated code generation in Bangla by fine-tuning open-source models (Llama 3, TigerLLM, Qwen) with parameter-efficient LoRA adapters to overcome data scarcity.
*   Improved generation quality with Chain-of-Thought prompting and a self-refinement loop that critiques and corrects generated code based on execution feedback.
*   Categorized failing generations by error type (syntax, runtime, misread problem statements) to guide the refinement loop.
*   **Publication:** <a href="https://aclanthology.org/2025.banglalp-1.65.pdf">AdversaryAI at BLP-2025 Task 2: A Think, Refine, and Generate (TriGen) System with LoRA and Self-Refinement for Code Generation</a>

</div>

<div class="experience-card" markdown="1">

### **BRAINTEASER: Advanced Commonsense Reasoning in Language Models**
<small>2024 | Shared Task at SemEval 2024, co-located with NAACL</small>

*   Designed data augmentation pipelines to improve model robustness on commonsense reasoning tasks built around lateral thinking puzzles.
*   Conducted a **comparative analysis** of language models, analyzing performance gaps and reasoning patterns in non-standard logical scenarios.
*   **Publication:** <a href="https://aclanthology.org/2024.semeval-1.180.pdf" target="_blank" rel="noopener noreferrer">Deja Vu at SemEval 2024 Task 9: A Comparative Study of Advanced Language Models for Commonsense Reasoning</a>

</div>

<div class="experience-card" markdown="1">

### **Violence Inciting Text Detection (VITD) in Bangla**
<small>2023 | Shared Task at the BLP Workshop, co-located with EMNLP</small>

<span class="achievement-badge">📊 Ranked 12th in Post-evaluation (19th Official)</span>

*   Applied semi-supervised self-training to address class imbalance and improve performance on minority classes.
*   Increased dataset diversity through back-translation with the Googletrans API, improving semantic variety while correcting linguistic inconsistencies.
*   Implemented an **ensemble approach** combining multiple transformer models with bagging and majority voting to reduce prediction variance.
*   **Publication:** <a href="https://aclanthology.org/2023.banglalp-1.32.pdf" target="_blank" rel="noopener noreferrer">Team_Syrax at BLP-2023 Task 1: Data Augmentation and Ensemble Based Approach for Violence Inciting Text Detection in Bangla</a>

</div>

<div class="experience-card" markdown="1">

### **Improving Answer Space Diversity in Visual Question Answering (VQA)**
<small>2022 | Undergraduate Thesis Project</small>

*   Conducted a comparative study of VQA methods, identifying core limitations in answer distribution.
*   Addressed the **"Answer Space Diversity" limitation** by augmenting training data with automatically generated, contextually relevant QA pairs using template-based synthesis.
*   Demonstrated improved performance on long-tail answer categories, reducing model bias toward frequent answers.

</div>

<!--
### **FUTURE RESEARCH PROJECT TITLE**
<small>YEAR | Context (e.g., Conference, Lab Project, etc.)</small>

*   Contribution 1: Describe the core problem you solved.
*   Contribution 2: Mention the specific technique or method you used.
*   **Publication:** [Link to paper, if applicable](#)
-->