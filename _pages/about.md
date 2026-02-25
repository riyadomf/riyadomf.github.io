---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I build **production AI systems** and **enterprise software** that solve real-world problems at scale. My work sits at the intersection of applied machine learning, systems engineering, and NLP research — with publications at **EMNLP** and **NAACL**, and a track record of shipping code that runs in production.

<div class="stats-grid">
  <div class="stat-card">
    <span class="stat-number">3</span>
    <span class="stat-label">Publications</span>
  </div>
  <div class="stat-card">
    <span class="stat-number">10×</span>
    <span class="stat-label">Pipeline Speedup</span>
  </div>
  <div class="stat-card">
    <span class="stat-number">4th / 32</span>
    <span class="stat-label">BLP 2025 Shared Task</span>
  </div>
</div>

## What I Do

**At [Altri.ai](https://altri.ai)** — I architect hybrid AI scoring engines that combine LLM-based feature extraction with traditional ML (XGBoost) for real estate investment analysis. I optimized ML pipelines to achieve a **10× throughput increase** using async orchestration and built fault-tolerant RAG systems for institutional knowledge preservation.

**At [Dynamic Solution Innovators](https://dsinnovators.com/)** — I engineer secure, scalable enterprise applications for government clients (NBR, MoCAT, BCIC) using **Java EE**. I pioneered the company's first enterprise-scale JSF application, contributed to [PrimeFaces open-source](https://github.com/primefaces/primefaces/pull/12865), and serve on the internal cybersecurity team.

**In Research** — I focus on low-resource NLP, most recently placing **4th out of 32 teams** in the Code Generation in Bangla shared task (BLP 2025) using LoRA fine-tuning and Chain-of-Thought reasoning.

**As an Instructor** — I teach [Enterprise Web Development with JEE and JSF](https://dynamic-learning.innovatorslab.net/) at Dynamic Learning, translating production experience into practical curriculum.

---

🎓 Education
======
**B.Sc. in Computer Science & Engineering**, Shahjalal University of Science and Technology (SUST)  
*CGPA: 3.53/4.00 (Last two years: 3.83)*

**Standardized Tests:**  
GRE: 317/340 (Q: 160, V: 157, AW: 3.0) | TOEFL: 104/120 (R: 29, L: 27, S: 23, W: 25)

---

🔬 Research Interests
======
* **Low-Resource NLP** — Code generation and text classification for low-resource languages (Bangla)
* **AI & Security** — Adversarial ML, model robustness, and using AI/ML to enhance cybersecurity
* **Retrieval-Augmented Generation** — Building knowledge transfer systems with vector databases

---

Beyond Work
======

### 🏆 Sports
I play football in my free time to stay active and competitive.

### 📸 Photography

I'm passionate about nature photography — capturing landscapes and everyday moments.

<button class="photo-toggle-btn" onclick="togglePhotos()" id="photo-toggle-btn">
  <span class="photo-toggle-icon">📷</span> View My Photos
</button>

<div class="photo-grid" id="photo-grid">
   <div class="photo-item">
      <img src="/images/1-shapla.jpg" alt="Photo 1" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/996.jpg" alt="Photo 996" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/997.jpg" alt="Photo 997" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/998.jpg" alt="Photo 998" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/999.jpg" alt="Photo 999" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/2-togor.jpg" alt="Photo 2" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/9-khulna.jpg" alt="Photo 9" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/5-dohs.jpg" alt="Photo 5" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/7-ambarkhana.jpg" alt="Photo 7" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/8-cat.jpg" alt="Photo 8" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/4-dohs.jpg" alt="Photo 4" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/10-tangu.jpg" alt="Photo 10" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/6-saintmartin.jpg" alt="Photo 6" loading="lazy">
   </div>
   <div class="photo-item">
      <img src="/images/3-turongchora.jpg" alt="Photo 3" loading="lazy">
   </div>

</div>


<style>
/* Photo toggle button */
.photo-toggle-btn {
   display: inline-flex;
   align-items: center;
   gap: 0.4em;
   padding: 0.6em 1.4em;
   border: none;
   border-radius: 24px;
   background: linear-gradient(135deg, #0f766e, #14b8a6);
   color: #fff;
   font-family: inherit;
   font-size: 0.9em;
   font-weight: 600;
   letter-spacing: 0.2px;
   cursor: pointer;
   transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
   box-shadow: 0 2px 12px rgba(15, 118, 110, 0.25);
   margin: 0.5em 0 1em;
}

.photo-toggle-btn:hover {
   transform: translateY(-2px);
   box-shadow: 0 6px 20px rgba(15, 118, 110, 0.3);
}

.photo-toggle-btn:active {
   transform: translateY(0);
   box-shadow: 0 2px 8px rgba(15, 118, 110, 0.2);
}

.photo-toggle-btn.active {
   background: linear-gradient(135deg, #334155, #475569);
   box-shadow: 0 2px 12px rgba(51, 65, 85, 0.25);
}

.photo-toggle-icon {
   font-size: 1.1em;
   transition: transform 0.3s ease;
}

.photo-toggle-btn:hover .photo-toggle-icon {
   transform: scale(1.15);
}

/* Photo grid */
.photo-grid {
   display: grid;
   grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
   gap: 14px;
   max-height: 0;
   overflow: hidden;
   opacity: 0;
   transition: max-height 0.5s cubic-bezier(0.4, 0, 0.2, 1),
               opacity 0.4s ease,
               margin 0.4s ease;
   margin-top: 0;
}

.photo-grid.visible {
   max-height: 4000px;
   opacity: 1;
   margin-top: 0.5em;
}

.photo-item {
   display: flex;
   justify-content: center;
   align-items: center;
   overflow: hidden;
   border-radius: 12px;
   box-shadow: 0 2px 12px rgba(0, 0, 0, 0.08), 0 4px 24px rgba(0, 0, 0, 0.04);
   min-height: 200px;
   background: #f1f5f9;
   transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.photo-item:hover {
   transform: translateY(-3px);
   box-shadow: 0 8px 30px rgba(0, 0, 0, 0.12), 0 2px 8px rgba(0, 0, 0, 0.06);
}

.photo-item img {
   max-width: 100%;
   height: auto;
   transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.photo-item:hover img {
   transform: scale(1.06);
}
</style>

<script>
function togglePhotos() {
   var grid = document.getElementById("photo-grid");
   var btn = document.getElementById("photo-toggle-btn");
   grid.classList.toggle("visible");
   btn.classList.toggle("active");
   if (grid.classList.contains("visible")) {
      btn.innerHTML = '<span class="photo-toggle-icon">✕</span> Hide Photos';
   } else {
      btn.innerHTML = '<span class="photo-toggle-icon">📷</span> View My Photos';
   }
}
</script>