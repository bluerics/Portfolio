<script setup lang="ts">
import ScrollReveal from '@/components/ScrollReveal.vue'

const skillCategories = [
  {
    title: 'Programming',
    icon: '</>',
    skills: ['Python', 'C++', 'C', 'JavaScript', 'TypeScript'],
  },
  {
    title: 'Web Development',
    icon: 'WEB',
    skills: ['Vue.js', 'HTML', 'CSS', 'Tailwind CSS', 'Django', 'REST API'],
  },
  {
    title: 'Embedded Systems',
    icon: 'HW',
    skills: [
      'Raspberry Pi',
      'Sensors',
      'Microcontrollers',
      'Embedded Programming',
      'Hardware Integration',
    ],
  },
  {
    title: 'Database & Backend',
    icon: 'DB',
    skills: ['PostgreSQL', 'MySQL', 'Django', 'REST API'],
  },
]
</script>

<template>
  <section
    id="skills"
    class="flex min-h-screen items-center px-6 py-24"
  >
    <div class="mx-auto w-full max-w-6xl">

      <ScrollReveal>

        <!-- Heading -->
        <div class="mb-14 text-center">
          <p
            class="mb-2 text-sm font-semibold uppercase tracking-[0.3em] text-[#67D5D0]"
          >
            What I work with
          </p>

          <h2 class="text-5xl font-bold">
            <span class="text-[#34E0A1]">Skills</span>
          </h2>

          <p
            class="mx-auto mt-5 max-w-2xl leading-7 text-[#D9F3F1]"
          >
            A collection of technologies and tools I have learned and
            used throughout my academic projects and development work.
          </p>
        </div>

        <!-- Skills -->
        <div class="grid grid-cols-1 gap-6 md:grid-cols-2">

          <!-- Skill Card -->
          <div
            v-for="category in skillCategories"
            :key="category.title"
            class="skill-card group"
          >

            <!-- Icon -->
            <div
              class="mb-6 flex h-14 w-14 items-center justify-center rounded-xl border border-[#34E0A1]/30 bg-[#34E0A1]/10 font-bold text-[#34E0A1] transition duration-300 group-hover:border-[#34E0A1] group-hover:bg-[#34E0A1]/20"
            >
              {{ category.icon }}
            </div>

            <!-- Title -->
            <h3
              class="text-2xl font-bold text-white transition duration-300 group-hover:text-[#34E0A1]"
            >
              {{ category.title }}
            </h3>

            <!-- Skills -->
            <div class="mt-5 flex flex-wrap gap-3">
              <span
                v-for="skill in category.skills"
                :key="skill"
                class="skill-tag"
              >
                {{ skill }}
              </span>
            </div>

            <!-- Line -->
            <div
              class="mt-7 h-px w-12 bg-[#34E0A1] transition-all duration-500 group-hover:w-full"
            ></div>

          </div>

        </div>

        <!-- Bottom text -->
        <div class="mt-10 text-center">
          <p class="text-sm text-[#BDD9D7]">
            Always learning. Always building. Always improving.
          </p>
        </div>

      </ScrollReveal>

    </div>
  </section>
</template>