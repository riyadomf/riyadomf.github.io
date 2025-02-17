---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a researcher and software engineer specializing in security and machine learning. I have developed secure and scalable enterprise applications for critical government infrastructure in Bangladesh, ensuring data security and process automation. Additionally, I contribute to open-source projects and serve as a cybersecurity consultant for in-house projects. My research has been published in BLP workshop at EMNLP 2023 and SemEval 2024. Beyond research and development, I'am also teaching a course of JSF with Java EE at Dynamic Learning.

🎓 Education
======
**B.Sc. in Computer Science & Engineering**, Shahjalal University of Science and Technology (SUST) \
*Relevant coursework: Computer Security, Machine Learning, Software Engineering, Data Science, Cloud Computing, Data Structure and Algorithm*  

🔬 Research Interest
======
* Computer Security
* Natural Language Processing
* Artificial Intelligence
* Software Engineering

Extra Curricular Activities
======

### 🏆 Sports
I enjoy playing football in my free time as a way to stay active and unwind.

### 📸 Photography

I have a passion for nature photography, capturing the beauty of landscapes and everyday moments. <br>
*Click here to reveal some of my favourite photos:*
<button onclick="togglePhotos()">Show/Hide Photos</button>

<div class="photo-grid" id="photo-grid" style="display:none">
   <div class="photo-item">
      <img src="/images/1-shapla.jpg" alt="Photo 1" loading="lazy">
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