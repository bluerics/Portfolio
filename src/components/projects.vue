<script setup lang="ts">
const projects = [
  {
    title: 'SIGNOVA',
    description:
      'An AI-powered camera-based American Sign Language to Ilocano translation system.',
    technologies: 'Python • CNN • MediaPipe • Raspberry Pi',
  },
  {
    title: 'Pharmacy Inventory System',
    description:
      'A web-based inventory system for managing medicines, suppliers, stocks, and purchase orders.',
    technologies: 'Django • PostgreSQL • REST API',
  },
  {
    title: 'SCARF',
    description:
      'An embedded systems project developed as part of our engineering coursework.',
    technologies: 'Embedded Systems • Hardware • Software',
  },
]
</script>

<template>
  <section id="projects" class="px-6 py-24">
    <div class="mx-auto max-w-6xl">
      <h2 class="mb-10 text-center text-4xl font-bold">
      <span class="text-[#34E0A1]">Projects</span>
      </h2>

      <div class="grid gap-6 md:grid-cols-3">
        <article
          v-for="project in projects"
          :key="project.title"
          class="rounded-2xl border border-gray-800 bg-gray-900 p-6 transition hover:-translate-y-2 hover:border-[#34E0A1]"
        >
          <h3 class="text-2xl font-bold">
            {{ project.title }}
          </h3>

          <p class="mt-4 leading-7 text-gray-400">
            {{ project.description }}
          </p>

          <p class="mt-6 text-sm text-[#34E0A1]">
            {{ project.technologies }}
          </p>
        </article>
      </div>
    </div>
  </section>
</template>