---
layout: archive
title: "Research Experience"
permalink: /research-experience/
author_profile: true
---

My research focuses on Natural Language Processing for low-resource languages, multimodal AI, and reasoning systems. I have published at **EMNLP** and **NAACL** workshops, with a record of competitive performance in shared tasks.

---

<div class="experience-card" markdown="1">

### **Code Generation in Bangla: Low-Resource Language Adaptation**
<small>2025 | Shared Task at the BLP Workshop, co-located with IJCNLP-AACL</small>

<span class="achievement-badge">🏆 4th Place out of 32 Teams — 85% Accuracy</span>

*   Investigated code generation in Bangla by fine-tuning open-source models (Llama 3, TigerLLM, Qwen) using parameter-efficient **LoRA** adapters to overcome data scarcity.
*   Enhanced reasoning via **Chain-of-Thought (CoT)** prompting and a self-refinement loop that iteratively critiques and corrects generated code based on execution feedback.
*   Conducted rigorous error analysis to identify failure modes in code generation tasks.
*   **Publication:** <a href="">AdversaryAI at BLP-2025 Task 2: A Think, Refine, and Generate (TriGen) System with LoRA and Self-Refinement for Code Generation</a>

</div>

<div class="experience-card" markdown="1">

### **BRAINTEASER: Advanced Commonsense Reasoning in Language Models**
<small>2024 | Shared Task at SemEval 2024, co-located with NAACL</small>

*   Designed **data augmentation pipelines** to improve model robustness for complex commonsense reasoning tasks involving lateral thinking puzzles.
*   Conducted a **comparative analysis** of advanced language models, analyzing performance gaps and reasoning patterns in non-standard logical scenarios.
*   **Publication:** <a href="https://aclanthology.org/2024.semeval-1.180.pdf" target="_blank" rel="noopener noreferrer">Deja Vu at SemEval 2024 Task 9: A Comparative Study of Advanced Language Models for Commonsense Reasoning</a>

</div>

<div class="experience-card" markdown="1">

### **Violence Inciting Text Detection (VITD) in Bangla**
<small>2023 | Shared Task at the BLP Workshop, co-located with EMNLP</small>

<span class="achievement-badge">📊 Top 20 — Improved from Rank 19 → 12 in Post-evaluation</span>

*   Applied **semi-supervised self-training** to address class imbalance, significantly improving performance on minority classes.
*   Enhanced dataset diversity through **back-translation** using the Googletrans API, improving semantic variety while correcting linguistic inconsistencies.
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