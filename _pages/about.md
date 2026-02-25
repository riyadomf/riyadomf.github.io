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
*Click to reveal some of my photos:*
<button onclick="togglePhotos()">Show/Hide Photos</button>

<div class="photo-grid" id="photo-grid" style="display:none">
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
.photo-grid {
   display: grid;
   grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
   grid-gap: 10px;
}

.photo-item {
   display: flex;
   justify-content: center;
   align-items: center;
   overflow: hidden;
   border-radius: 8px;
   box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
   min-height: 200px;
   background: #f1f5f9;
}

.photo-item img {
   max-width: 100%;
   height: auto;
   transition: transform 0.3s ease;
}

.photo-item:hover img {
   transform: scale(1.05);
}
</style>

<script>
function togglePhotos() {
   var x = document.getElementById("photo-grid");
   if (x.style.display === "none") {
      x.style.display = "grid";
   } else {
      x.style.display = "none";
   }
}
</script>