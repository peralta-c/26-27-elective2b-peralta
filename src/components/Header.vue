<template>
  <header>
    <div class="logo">chrislyn.dev ✨</div>

    <button
        class="menu-toggle"
        @click="open = !open"
        :aria-expanded="open"
        aria-label="Toggle menu"
    >
      <i :class="open ? 'fa-solid fa-xmark' : 'fa-solid fa-bars'"></i>
    </button>

    <nav :class="{ open }">
      <a href="#about" @click="open = false"><i class="fa-regular fa-id-card"></i> About</a>
      <a href="#projects" @click="open = false"><i class="fa-regular fa-folder"></i> Projects</a>
      <a href="#achievements" @click="open = false"><i class="fa-solid fa-award"></i> Achievements</a>
      <a href="#contact" @click="open = false"><i class="fa-regular fa-envelope"></i> Contact</a>
      <a href="/CHRISLYN_CV.pdf" download class="nav-cv-btn">📄 CV</a>
    </nav>
  </header>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const open = ref(false)
</script>