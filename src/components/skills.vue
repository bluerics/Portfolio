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
  {
    title: 'PCB Design',
    icon: 'PCB',
    skills: [
      'Schematic Design',
      'Circuit Layout',
      'PCB Layout',
      'Component Selection',
    ],
  },
  {
    title: 'Power Supply',
    icon: 'PWR',
    skills: [
      'Power Electronics',
      'Voltage Regulation',
      'Circuit Design',
      'Circuit Testing',
    ],
  },
]
</script>

<template>
  <section
    id="skills"
    class="flex min-h-screen items-center bg-[#101418] px-6 py-24"
  >
    <div class="mx-auto w-full max-w-6xl">

      <ScrollReveal>

      
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

        
        <div class="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">

          <div
            v-for="(category, index) in skillCategories"
            :key="category.title"
            class="sk-card group"
          >

            <span class="sk-number">
              {{ String(index + 1).padStart(2, '0') }}
            </span>

            <div class="sk-icon">
              {{ category.icon }}
            </div>

            <h3 class="sk-title">
              {{ category.title }}
            </h3>

            <div class="mt-5 flex flex-wrap justify-center gap-2">
              <span
                v-for="skill in category.skills"
                :key="skill"
                class="skill-tag"
              >
                {{ skill }}
              </span>
            </div>

            <div class="sk-line"></div>

          </div>

        </div>

        
        <div class="mt-10 text-center">
          <p class="text-sm text-[#BDD9D7]">
            Always learning. Always building. Always improving.
          </p>
        </div>

      </ScrollReveal>

    </div>
  </section>
</template>

<style scoped>
.sk-card {
  position: relative;
  overflow: hidden;

  display: flex;
  flex-direction: column;
  align-items: center;

  padding: 2.25rem 1.5rem 2rem;

  border: 1px solid rgba(103, 213, 208, 0.25);
  border-radius: 1.25rem;

  background: #101418;

  text-align: center;

  transition:
    transform 0.4s ease,
    border-color 0.4s ease,
    box-shadow 0.4s ease;
}

.sk-card:hover {
  transform: translateY(-8px);

  border-color: #34e0a1;

  box-shadow:
    0 20px 45px rgba(0, 0, 0, 0.35),
    0 0 30px rgba(52, 224, 161, 0.08);
}

.sk-number {
  position: absolute;
  top: 1rem;
  left: 1.25rem;

  color: rgba(103, 213, 208, 0.5);

  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 0.2em;

  transition: color 0.3s ease;
}

.sk-card:hover .sk-number {
  color: #34e0a1;
}

.sk-icon {
  display: flex;
  align-items: center;
  justify-content: center;

  width: 72px;
  height: 72px;

  margin-bottom: 1.25rem;

  border: 1px solid rgba(52, 224, 161, 0.35);
  border-radius: 50%;

  background: rgba(52, 224, 161, 0.08);

  color: #34e0a1;

  font-size: 0.95rem;
  font-weight: 800;

  box-shadow: 0 0 25px rgba(52, 224, 161, 0.08);

  transition:
    transform 0.4s ease,
    border-color 0.3s ease,
    background 0.3s ease;
}

.sk-card:hover .sk-icon {
  transform: scale(1.08);

  border-color: #34e0a1;
  background: rgba(52, 224, 161, 0.15);
}

.sk-title {
  color: #fff;

  font-size: 1.4rem;
  font-weight: 700;

  transition: color 0.3s ease;
}

.sk-card:hover .sk-title {
  color: #34e0a1;
}

.sk-line {
  width: 3rem;
  height: 1px;

  margin-top: auto;
  padding-top: 0;

  background: #34e0a1;

  transition: width 0.5s ease;
}

.sk-card > .sk-line {
  margin-top: 1.75rem;
}

.sk-card:hover .sk-line {
  width: 100%;
}
</style>