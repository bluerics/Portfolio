<script setup lang="ts">
const skills = [
  'Python',
  'C++',
  'Django',
  'PostgreSQL',
  'Git & GitHub',
]
</script>

<template>
  <section id="skills" class="px-6 py-24">
    <div class="mx-auto max-w-5xl">
      <h2 class="mb-10 text-center text-4xl font-bold">
       <span class="text-[#34E0A1]">Skills</span>
      </h2>

      <div class="grid grid-cols-2 gap-4 md:grid-cols-3">
        <div
          v-for="skill in skills"
          :key="skill"
          class="rounded-xl border border-black-800 bg-gray-950 p-5 text-center transition hover:-translate-y-1 hover:border-[#34E0A1]"
        >
          {{ skill }}
        </div>
      </div>
    </div>
  </section>
</template>