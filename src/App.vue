<script setup lang="ts">
import bg from '@/assets/bg.mp4'
import navbar from '@/components/navbar.vue'
import home from '@/components/home.vue'
import about from '@/components/about.vue'
import skills from '@/components/skills.vue'
import projects from '@/components/projects.vue'
import contact from '@/components/contact.vue'
</script>

<template>
   <div class="relative min-h-screen overflow-hidden text-white">

    <video
      :src="bg"
      autoplay
      muted
      loop
      playsinline
      class=" fixed  inset-0 h-full w-full object-cover"
    ></video>

   
    <div class="absolute inset-0 bg-[#03363D]/60"></div>

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