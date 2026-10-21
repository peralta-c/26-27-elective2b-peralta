<template>
  <section id="about" class="section">
    <h2>About Me 💻</h2>
    <div class="about-card">
      <p class="about-text">
        I am a passionate Computer Engineering student building modern software solutions. I enjoy working on low-level systems, full-stack applications, and exploring new technologies to solve real-world problems with creativity and precision.
      </p>

      <div class="about-details">
        <div class="detail-category">
          <h3>🛠️ Technical Skills</h3>
          <div class="tags">
            <span v-for="skill in technicalSkills" :key="skill" class="tag">{{ skill }}</span>
          </div>
        </div>

        <div class="detail-category">
          <h3>✨ Hobbies & Interests</h3>
          <div class="tags">
            <span v-for="hobby in hobbies" :key="hobby" class="tag">{{ hobby }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const technicalSkills = ref([
  'C', 'Python', 'HTML / CSS / JS', 'Hardware Troubleshooting', 'C++'
])

const hobbies = ref([
  'Travelling', 'Tripping with the nature✌️', 'Swimming', 'The Trouble Maker😁'
])
</script>