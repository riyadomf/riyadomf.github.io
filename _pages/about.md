---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm an **AI Engineer** and a **Software Engineer** with a strong foundation in machine learning, and enterprise systems. I build production-grade AI systems that combine modern LLMs with traditional ML for real-world applications.

At Altri.ai, I architect hybrid AI scoring engines that extract insights from unstructured data using LLMs and XGBoost. I've optimized ML pipelines to achieve **10x throughput increases** and built fault-tolerant RAG systems for knowledge preservation.

At DSI, I engineer secure, scalable enterprise applications for government infrastructures using **Java EE**, transforming complex bureaucratic processes into streamlined digital workflows. I've contributed to open-source projects (notably [PrimeFaces](https://github.com/primefaces/primefaces/pull/12865)) and served on cybersecurity teams conducting vulnerability assessments.

My research has been published at **EMNLP** (BLP Workshop) and **NAACL** (SemEval), focusing on low-resource NLP. Most recently, I placed **4th out of 32 teams** in the Code Generation in Bangla shared task (BLP 2025) using LoRA fine-tuning and Chain-of-Thought reasoning.

I also teach **Enterprise Web Development with JEE and JSF** at [Dynamic Learning](https://dynamic-learning.innovatorslab.net/), sharing practical knowledge from building production systems.

🎓 Education
======
**B.Sc. in Computer Science & Engineering**, Shahjalal University of Science and Technology (SUST)  
*CGPA: 3.53/4.00 (Last two years: 3.83)*

**Standardized Tests:**  
GRE: 317/340 (Q: 160, V: 157, AW: 3.0) | TOEFL: 104/120 (R: 29, L: 27, S: 23, W: 25)

🔬 Research Interests
======
* **Low-Resource NLP**: Code generation and text classification in low-resource languages (Bangla)
* **AI & Security Intersection**: Adversarial ML, model robustness, secure AI system design, and using AI/ML to enhance cybersecurity
* **Software Security**: Application security, vulnerability assessment, and secure software development practices
* **Retrieval-Augmented Generation (RAG)**: Building knowledge transfer systems with vector databases

Beyond Work
======

### 🏆 Sports
I enjoy playing football in my free time as a way to stay active and unwind.

### 📸 Photography

I have a passion for nature photography, capturing landscapes and everyday moments.  
*Click to reveal some of my favorite photos:*
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
   border-radius: 5px;
   box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
   min-height: 200px; /* Ensures space is reserved before image loads */
   background: #f0f0f0; /* Light grey placeholder */
}

.photo-item img {
   max-width: 100%;
   height: auto;
   transition: transform 0.3s ease;
}

.photo-item:hover img {
   transform: scale(1.1);
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