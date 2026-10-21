<template>
  <section id="achievements" class="section">
    <h2>Certificates & Achievements 🏆</h2>
    <div class="projects-grid">
      <div v-for="cert in certificates" :key="cert.title" class="project-card cert-card">
        <div class="cert-img-container">
          <img :src="cert.img" :alt="cert.title" class="cert-img">
        </div>
        <h3>{{ cert.title }}</h3>
        <p>{{ cert.subtitle }}</p>
        <a :href="cert.img" target="_blank" class="project-link">View Certificate &rarr;</a>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Certificate {
  title: string
  subtitle: string
  img: string
}

const certificates = ref<Certificate[]>([
  { title: 'Regional ITE Summit 2026', subtitle: 'St. Paul University Philippines • July 20-22, 2026', img: '/images/peralta.jpg' },
  { title: 'Safe Spaces Act Symposium', subtitle: 'Cagayan State University • September 18, 2026', img: '/images/OJT.jpg' },
  { title: 'Engineering Your Online Reputation', subtitle: 'ICpEP Region 2 • September 20, 2025', img: '/images/Talaktech-1.jpg' },
  { title: 'Data Analytics 101', subtitle: 'ICpEP Region 2 • October 4, 2025', img: '/images/Talaktech-2.jpg' },
  { title: 'Machine Learning & Deep Learning', subtitle: 'ICpEP Region 2 • October 11, 2025', img: '/images/Talaktech-3.jpg' },
  { title: 'Quantum Computing', subtitle: 'ICpEP Region 2 • October 18, 2025', img: '/images/Talaktech-4.jpg' },
  { title: 'The Digital Mirror', subtitle: 'ICpEP Region 2 • November 29, 2025', img: '/images/Talaktech-5.jpg' },
  { title: 'Patent and IP Rights', subtitle: 'ICpEP Region 2 • December 8, 2025', img: '/images/Talaktech-6.jpg' },
  { title: 'Digital Transformation in Smart Cities', subtitle: 'ICpEP Region 2 • December 8, 2025', img: '/images/Talaktech-7.jpg' },
  { title: 'Research Writing & Presentation', subtitle: 'ICpEP Region 2 • December 8, 2025', img: '/images/Talaktech-8.jpg' },
  { title: 'Internship', subtitle: 'One Point Contact Inc., Pasig City • June 9, 2026', img: '/images/ooo.jpg' },
  { title: 'Frontiers of Computer Engineering: 2025 International Conference (Day 1)', subtitle: 'Cagayan State University - Carig Campus • December 12, 2025', img: '/images/Frontier1.jpg' },
  { title: 'Frontiers of Computer Engineering: 2025 International Conference (Day 2)', subtitle: 'Cagayan State University - Carig Campus • December 13, 2025', img: '/images/Frontier2.jpg' },
])
</script>