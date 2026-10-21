<template>
  <section class="hero">
    <div class="hero-content">
      <div class="profile-img-container">
        <!-- Use :src instead of src so Vite treats it cleanly -->
        <img :src="'/images/len.jpg'" alt="Chrislyn Peralta" class="profile-img">
      </div>
      <h1><span class="highlight">Chrislyn Peralta</span></h1>
      <p>4th Year Student | Bachelor of Science in Computer Engineering</p>
      <div class="hero-buttons">
        <a href="#projects" class="btn">View My Work ✨</a>
        <a href="/CHRISLYN_CV.pdf" download="CHRISLYN_CV.pdf" class="btn btn-secondary">Download CV</a>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>