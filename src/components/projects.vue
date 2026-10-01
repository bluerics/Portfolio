<script setup lang="ts">
import ScrollReveal from '@/components/ScrollReveal.vue'
import scarf from '@/assets/projects/scarf.png'
import pharmacy from '@/assets/projects/pharmacy.svg'
import pcb from '@/assets/projects/pcb.jpg'
import powersupply from '@/assets/projects/powersupply.jpg'


const images = import.meta.glob('../assets/projects/*.{jpg,jpeg,png,webp,svg}', {
  eager: true,
  import: 'default',
}) as Record<string, string>

const getImage = (slug: string): string | null => {
  const key = Object.keys(images).find(
    (path) =>
      path.split('/').pop()?.replace(/\.[^.]+$/, '') === slug
  )
  return key ? images[key] : null
}

const projects = [
  {
    number: '01',
    slug: 'signova',
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
    status: 'Ongoing',
  },
  {
    number: '02',
    slug: 'scarf',
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
    status: null,
  },
  {
    number: '03',
    slug: 'pharmacy',
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
    status: 'Ongoing',
  },
  {
    number: '04',
    slug: 'pcb',
    category: 'HARDWARE DESIGN',
    title: 'PCB Design',
    description:
      'A printed circuit board design project covering circuit schematics, component placement, and board layout, turning an electronic circuit into a board ready for fabrication.',
    technologies: [
      'PCB Design',
      'Schematic Design',
      'Circuit Layout',
    ],
    icon: 'PCB',
    featured: false,
    status: 'Completed',
  },
  {
    number: '05',
    slug: 'powersupply',
    category: 'POWER ELECTRONICS',
    title: 'Power Supply',
    description:
      'A power supply project focused on designing and building a circuit that converts and regulates electrical power to deliver stable voltage for electronic devices.',
    technologies: [
      'Power Electronics',
      'Circuit Design',
      'Hardware',
    ],
    icon: 'PWR',
    featured: false,
    status: 'Completed',
  },
]
</script>

<template>
  <section
    id="projects"
    class="flex min-h-screen items-center bg-[#0B0B10] px-6 py-24"
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
            class="absolute -right-24 -top-24 h-64 w-64 rounded-full bg-[#3B9EFF]/10 blur-3xl transition duration-700 group-hover:bg-[#3B9EFF]/20"
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

                <span
                  v-if="projects[0].status"
                  :class="projects[0].status === 'Completed' ? 'border-[#67D5D0]/40 bg-[#67D5D0]/10 text-[#67D5D0]' : 'border-[#34E0A1]/40 bg-[#34E0A1]/10 text-[#34E0A1]'" class="inline-flex items-center gap-2 rounded-full border px-3 py-1 text-[10px] font-semibold uppercase tracking-[0.15em]"
                >
                  <span class="h-1.5 w-1.5 rounded-full bg-current"></span>
                  {{ projects[0].status }}
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
              <div
                v-if="getImage(projects[0].slug)"
                class="project-image project-image-large"
              >
                <img
                  :src="getImage(projects[0].slug)!"
                  :alt="projects[0].title"
                />
              </div>

              <div v-else class="project-icon-large">
                <span>AI</span>
              </div>
            </div>
          </div>

          
          <div
            class="h-1 w-1/4 bg-[#3B9EFF] shadow-[0_0_12px_rgba(59,158,255,0.8)] transition-all duration-700 group-hover:w-full"
          ></div>
        </div>

        
        <div class="grid gap-8 md:grid-cols-2">

          <div
            v-for="project in projects.slice(1)"
            :key="project.title"
            class="project-card group"
          >
            
            <div
              v-if="getImage(project.slug)"
              class="project-image mb-6"
            >
              <img
                :src="getImage(project.slug)!"
                :alt="project.title"
              />
            </div>

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

                <span
                  v-if="project.status"
                  :class="project.status === 'Completed' ? 'border-[#67D5D0]/40 bg-[#67D5D0]/10 text-[#67D5D0]' : 'border-[#34E0A1]/40 bg-[#34E0A1]/10 text-[#34E0A1]'" class="mt-3 inline-flex items-center gap-2 rounded-full border px-3 py-1 text-[10px] font-semibold uppercase tracking-[0.15em]"
                >
                  <span class="h-1.5 w-1.5 rounded-full bg-current"></span>
                  {{ project.status }}
                </span>
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

<style scoped>
.project-image {
  position: relative;
  overflow: hidden;

  height: 180px;

  border: 1px solid rgba(59, 158, 255, 0.4);
  border-radius: 0.75rem;

  box-shadow: 0 0 14px rgba(59, 158, 255, 0.2);
}

.project-image-large {
  width: 100%;
  height: 240px;

  border-radius: 1.25rem;
}

.project-image img {
  display: block;
  width: 100%;
  height: 100%;

  object-fit: cover;

  transition: transform 0.6s ease;
}

.group:hover .project-image img {
  transform: scale(1.06);
}
</style>