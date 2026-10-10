<script setup lang="ts">
import navbar from '@/components/navbar.vue'
import home from '@/components/home.vue'
import about from '@/components/about.vue'
import skills from '@/components/skills.vue'
import projects from '@/components/projects.vue'
import contact from '@/components/contact.vue'
import Footer from '@/components/Footer.vue'
</script>

<template>
   <div class="relative min-h-screen overflow-x-hidden bg-[#1A2D42] text-[#D4D8DD]">
    <div class="relative z-10">

    <navbar />

    <main>
      <home />
      <about />
      <skills />
      <projects />
      <contact />
    
    </main>
    <Footer />
    </div>

  </div>
</template>