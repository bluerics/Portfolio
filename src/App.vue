<script setup lang="ts">
import navbar from '@/components/navbar.vue'
import home from '@/components/home.vue'
import about from '@/components/about.vue'
import skills from '@/components/skills.vue'
import projects from '@/components/projects.vue'
import contact from '@/components/contact.vue'
</script>

<template>
   <div class="relative min-h-screen overflow-hidden bg-[#0A0A0A] text-white">
    <div class="relative z-10">

    <navbar />

    <main>
      <home />
      <about />
      <skills />
      <projects />
      <contact />
    </main>
    </div>

  </div>
</template>