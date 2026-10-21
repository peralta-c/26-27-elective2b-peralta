<template>
  <section id="projects" class="section">
    <h2>Featured Projects</h2>
    <div class="projects-grid">
      <div
          v-for="project in projects"
          :key="project.id"
          class="project-card"
          :data-id="project.id"
      >
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <div class="card-footer">
          <button
              class="like-btn"
              :class="{ liked: project.isLiked }"
              @click="toggleLike(project)"
          >
            <i :class="project.isLiked ? 'fa-solid fa-heart' : 'fa-regular fa-heart'"></i>
          </button>
          <span class="like-count">{{ project.likes }} {{ project.likes === 1 ? 'like' : 'likes' }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'

interface Project {
  id: string
  title: string
  description: string
  likes: number
  isLiked: boolean
}

const projects = ref<Project[]>([
  {
    id: 'project-power-supply',
    title: 'Custom Regulated Power Supply',
    description: 'Designed and assembled a custom regulated power supply circuit designed to deliver stable voltage outputs for microcontrollers, sensors, and electronic testing benches.',
    likes: 0,
    isLiked: false
  },
  {
    id: 'project-pic-board',
    title: 'Custom PIC Development Board',
    description: 'Engineered a custom PIC microcontroller development board equipped with peripheral interfacing, power management, and breakout header pins for embedded C/C++ prototyping.',
    likes: 0,
    isLiked: false
  },
  {
    id: 'project-gas-sensor',
    title: 'Gas Sensor',
    description: 'A multi-gas detection module integrated with analog signal conditioning, adjustable threshold triggers, and microcontroller interfacing for real-time environmental monitoring.',
    likes: 0,
    isLiked: false
  },
  {
    id: 'project-job-portal',
    title: 'Computer Engineering Alumni Job Portal',
    description: 'A centralized web platform built to connect alumni with career opportunities, featuring skill profiling and employer connections. Contributed to UI/UX and research documentation.',
    likes: 0,
    isLiked: false
  },
  {
    id: 'project-eco-charge',
    title: 'Eco-Charge',
    description: 'An energy-efficient alternative charging station prototype converting recycled plastic deposits into device charging power. Assisted in hardware assembly and research formulation.',
    likes: 0,
    isLiked: false
  },
  {
    id: 'project-hydrocast',
    title: 'HydroCast',
    description: 'An ESP32 & LoRa-based early warning flood risk mapping and telemetry system integrated with the Open-Meteo API for real-time flood monitoring and weather forecasting.',
    likes: 0,
    isLiked: false
  }
])

onMounted(() => {
  projects.value.forEach(project => {
    const isLiked = localStorage.getItem(`liked_${project.id}`) === 'true'
    const count = parseInt(localStorage.getItem(`count_${project.id}`) || '0', 10)
    project.isLiked = isLiked
    project.likes = count
  })
})

const toggleLike = (project: Project) => {
  project.isLiked = !project.isLiked
  if (project.isLiked) {
    project.likes += 1
    localStorage.setItem(`liked_${project.id}`, 'true')
  } else {
    project.likes = Math.max(0, project.likes - 1)
    localStorage.setItem(`liked_${project.id}`, 'false')
  }
  localStorage.setItem(`count_${project.id}`, project.likes.toString())
}
</script>