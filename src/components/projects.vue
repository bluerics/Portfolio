<script setup lang="ts">
import ScrollReveal from '@/components/ScrollReveal.vue'

const projects = [
  {
    number: '01',
    category: 'AI & COMPUTER VISION',
    title: 'SIGNOVA',
    description:
      'An AI-powered camera-based American Sign Language to Ilocano translation system designed to recognize selected static ASL signs and convert them into Ilocano text and speech.',
    technologies: [
      'Python',
      'CNN',
      'MediaPipe',
      'OpenCV',
      'Raspberry Pi',
    ],
    icon: 'AI',
    featured: true,
  },
  {
    number: '02',
    category: 'EMBEDDED SYSTEMS',
    title: 'SCARF',
    description:
      'An embedded systems project developed as part of our engineering coursework, combining hardware and software to create a practical technology solution.',
    technologies: [
      'Embedded Systems',
      'Hardware',
      'Software',
    ],
    icon: 'HW',
    featured: false,
  },
  {
    number: '03',
    category: 'WEB DEVELOPMENT',
    title: 'Pharmacy Inventory System',
    description:
      'A web-based inventory management system for managing medicines, suppliers, stocks, and purchase orders.',
    technologies: [
      'Django',
      'PostgreSQL',
      'REST API',
    ],
    icon: 'WEB',
    featured: false,
  },
]
</script>

<template>
  <section
    id="projects"
    class="flex min-h-screen items-center px-6 py-24"
  >
    <div class="mx-auto w-full max-w-6xl">

      <ScrollReveal>

        
        <div class="mb-14 text-center">
          <p
            class="mb-2 text-sm font-semibold uppercase tracking-[0.3em] text-[#67D5D0]"
          >
            What I've built
          </p>

          <h2 class="text-5xl font-bold text-white">
            My
            <span class="text-[#34E0A1]">Projects</span>
          </h2>

          <p
            class="mx-auto mt-5 max-w-2xl leading-7 text-[#D9F3F1]"
          >
            A selection of academic and personal projects that reflect
            my experience in software development, artificial
            intelligence, and embedded systems.
          </p>
        </div>

       
        <div
          class="project-featured group relative mb-8 overflow-hidden rounded-2xl"
        >
          
          <div
            class="absolute -right-24 -top-24 h-64 w-64 rounded-full bg-[#34E0A1]/10 blur-3xl transition duration-700 group-hover:bg-[#34E0A1]/20"
          ></div>

          <div
            class="relative grid items-center gap-10 p-8 md:grid-cols-[1fr_280px] md:p-12"
          >
            
            <div>
              <div class="mb-5 flex items-center gap-4">
                <span
                  class="text-sm font-bold tracking-[0.25em] text-[#34E0A1]"
                >
                  {{ projects[0].number }}
                </span>

                <span
                  class="h-px w-12 bg-[#34E0A1]/50"
                ></span>

                <span
                  class="text-xs font-semibold tracking-[0.2em] text-[#67D5D0]"
                >
                  {{ projects[0].category }}
                </span>
              </div>

              <h3
                class="text-4xl font-bold text-white md:text-5xl"
              >
                {{ projects[0].title }}
              </h3>

              <p
                class="mt-6 max-w-2xl leading-8 text-[#D9F3F1]"
              >
                {{ projects[0].description }}
              </p>

              
              <div class="mt-7 flex flex-wrap gap-3">
                <span
                  v-for="technology in projects[0].technologies"
                  :key="technology"
                  class="project-tag"
                >
                  {{ technology }}
                </span>
              </div>
            </div>

          
            <div class="flex justify-center">
              <div class="project-icon-large">
                <span>AI</span>
              </div>
            </div>
          </div>

          
          <div
            class="h-1 w-1/4 bg-[#34E0A1] transition-all duration-700 group-hover:w-full"
          ></div>
        </div>

        
        <div class="grid gap-8 md:grid-cols-2">

          <div
            v-for="project in projects.slice(1)"
            :key="project.title"
            class="project-card group"
          >
            
            <div class="flex items-start justify-between">
              <div>
                <span
                  class="text-sm font-bold tracking-[0.25em] text-[#34E0A1]"
                >
                  {{ project.number }}
                </span>

                <p
                  class="mt-3 text-xs font-semibold tracking-[0.15em] text-[#67D5D0]"
                >
                  {{ project.category }}
                </p>
              </div>

              
              <div class="project-icon">
                {{ project.icon }}
              </div>
            </div>

            
            <h3
              class="mt-8 text-2xl font-bold text-white transition duration-300 group-hover:text-[#34E0A1]"
            >
              {{ project.title }}
            </h3>

            
            <p
              class="mt-4 leading-7 text-[#D9F3F1]"
            >
              {{ project.description }}
            </p>

            
            <div class="mt-6 flex flex-wrap gap-2">
              <span
                v-for="technology in project.technologies"
                :key="technology"
                class="project-tag"
              >
                {{ technology }}
              </span>
            </div>

            
            <div
              class="mt-8 flex items-center gap-3 text-sm font-semibold text-[#34E0A1]"
            >
              <span
                class="h-px w-8 bg-[#34E0A1] transition-all duration-500 group-hover:w-16"
              ></span>

              Academic Project
            </div>
          </div>

        </div>

      </ScrollReveal>

    </div>
  </section>
</template>