
<script setup lang="ts">
import { computed } from 'vue'

const images = import.meta.glob(
  '../assets/projects/*.{jpg,jpeg,png,webp,svg}',
  {
    eager: true,
    import: 'default',
    query: '?url',
  },
)

const getImage = (slug: string): string | undefined => {
  const entry = Object.entries(images).find(([path]) =>
    path.split('/').pop()?.split('.')[0] === slug,
  )

  return entry?.[1] as string | undefined
}

const projects = [
  {
    number: '01',
    slug: 'signova',
    category: 'AI & COMPUTER VISION',
    title: 'SIGNOVA',
    description:
      'An AI-powered camera-based ASL-to-Ilocano translation system that recognizes selected static signs and converts them into Ilocano text and speech.',
    technologies: ['Python', 'CNN', 'MediaPipe', 'Raspberry Pi'],
    status: 'Ongoing',
  },
  {
    number: '02',
    slug: 'scarf',
    category: 'EMBEDDED SYSTEMS',
    title: 'SCARF',
    description:
      'An embedded systems project combining hardware and software to create a practical technology solution.',
    technologies: ['Embedded Systems', 'Hardware'],
    status: 'Completed',
  },
  {
    number: '03',
    slug: 'pharmacy',
    category: 'WEB DEVELOPMENT',
    title: 'Pharmacy Inventory System',
    description:
      'A system for managing medicines, suppliers, stocks, and purchase orders.',
    technologies: ['Django', 'PostgreSQL', 'REST API'],
    status: 'Ongoing',
  },
  {
    number: '04',
    slug: 'pcb',
    category: 'HARDWARE DESIGN',
    title: 'PCB Design',
    description:
      'A circuit board design project covering schematics, component placement, and board layout.',
    technologies: ['PCB Design', 'Circuit Layout'],
    status: 'Completed',
  },
  {
    number: '05',
    slug: 'powersupply',
    category: 'POWER ELECTRONICS',
    title: 'Power Supply',
    description:
      'A circuit design project focused on providing stable voltage for electronic devices.',
    technologies: ['Power Electronics', 'Circuit Design'],
    status: 'Completed',
  },
]

const featured = computed(() => projects[0]!)
const otherProjects = computed(() => projects.slice(1))
</script>

<template>
  <section id="projects" class="projects-section">
    <div class="section-heading">
      <p class="eyebrow">WHAT I'VE BUILT</p>
      <h2><span>Projects</span></h2>
      <p class="section-description">
        A collection of projects I've developed through learning and experimentation.
      </p>
    </div>

    <div class="projects-layout">
      
      <article class="project-featured">
        <div class="featured-content">
          <div class="project-top">
            <span class="project-number">{{ featured.number }}</span>
            <span v-if="featured.status" class="status">
              {{ featured.status }}
            </span>
          </div>

          <p class="category">{{ featured.category }}</p>
          <h3>{{ featured.title }}</h3>
          <p class="project-description">{{ featured.description }}</p>

          <div class="tags">
            <span
              v-for="tech in featured.technologies"
              :key="tech"
              class="project-tag"
            >
              {{ tech }}
            </span>
          </div>

          <div class="featured-image">
            <img
              v-if="getImage(featured.slug)"
              :src="getImage(featured.slug)"
              :alt="`${featured.title} preview`"
            />
            <span v-else class="image-placeholder">SIGNOVA</span>
          </div>
        </div>
      </article>

    
      <div class="other-projects">
        <article
          v-for="project in otherProjects"
          :key="project.slug"
          class="project-card"
        >
          <div class="project-top">
            <span class="project-number">{{ project.number }}</span>
            <span v-if="project.status" class="status">
              {{ project.status }}
            </span>
          </div>

          <p class="category">{{ project.category }}</p>
          <h3>{{ project.title }}</h3>
          <p class="project-description">{{ project.description }}</p>

          <div class="tags">
            <span
              v-for="tech in project.technologies"
              :key="tech"
              class="project-tag"
            >
              {{ tech }}
            </span>
          </div>

          <div class="project-image">
            <img
              v-if="getImage(project.slug)"
              :src="getImage(project.slug)"
              :alt="`${project.title} preview`"
            />
            <span v-else class="image-placeholder">
              {{ project.title }}
            </span>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<style scoped>

.projects-section {
  padding: 3rem 1.25rem;
  background: #0b0b10;
  color: #d4d8dd;
}

.section-heading {
  margin: 0 auto 1.5rem;
  text-align: center;
}

.eyebrow {
  margin-bottom: 0.4rem;
  color: #3b9eff;
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.18em;
}

.section-heading h2 {
  margin: 0;
  font-size: clamp(1.7rem, 4vw, 2.2rem);
  font-weight: 800;
}

.section-heading h2 span {
  color: #d4d8dd;
}

.section-description {
  margin-top: 0.4rem;
  color: #aab7b7;
  font-size: 0.8rem;
}

.projects-layout {
  display: grid;
  grid-template-columns: 0.9fr 1.1fr;
  gap: 1rem;
  align-items: stretch;
  max-width: 1050px;
  margin: 0 auto;
  padding: 8px;
}

.project-featured,
.project-card {
  position: relative;
  min-width: 0;
  border: 1px solid rgba(59, 158, 255, 0.22);
  border-radius: 0.75rem;
  background: #121820;
  cursor: pointer;
  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease,
    border-color 0.25s ease;
}

.project-featured {
  overflow: hidden;
}

.featured-content {
  display: flex;
  flex-direction: column;
  height: 100%;
  padding: 0.85rem;
}

.other-projects {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  grid-auto-rows: minmax(0, auto);
  align-items: stretch;
  gap: 1rem;
  min-width: 0;
}

.project-card {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  padding: 0.75rem;
  overflow: hidden;
}

.project-featured:hover,
.project-card:hover {
  transform: translateY(-5px);
  border-color: #3b9eff;
  box-shadow: 0 8px 20px rgba(59, 158, 255, 0.22);
  z-index: 2;
}

.project-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.3rem;
}

.project-number {
  color: #3b9eff;
  font-size: 0.7rem;
  font-weight: 700;
}

.status {
  padding: 0.15rem 0.35rem;
  border-radius: 999px;
  background: rgba(59, 158, 255, 0.1);
  color: #75bcff;
  font-size: 0.55rem;
}

.category {
  margin: 0.45rem 0 0.25rem;
  color: #aab7b7;
  font-size: 0.58rem;
  font-weight: 600;
  letter-spacing: 0.06em;
}

.project-card h3,
.project-featured h3 {
  margin: 0;
  color: #f3f6f8;
  font-size: 0.9rem;
  font-weight: 700;
  line-height: 1.3;
  overflow-wrap: anywhere;
}

.project-description {
  display: block;
  margin: 0.4rem 0 0.55rem;
  color: #aab7b7;
  font-size: 0.7rem;
  line-height: 1.4;
  overflow-wrap: anywhere;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.25rem;
}

.project-tag {
  padding: 0.15rem 0.35rem;
  border: 1px solid rgba(170, 183, 183, 0.15);
  border-radius: 999px;
  background: #1a2d42;
  color: #d4d8dd;
  font-size: 0.55rem;
}

.featured-image,
.project-image {
  width: 100%;
  overflow: hidden;
  border-radius: 0.5rem;
  background: #1a2d42;
}

.featured-image {
  height: 100px;
  margin-top: 0.75rem;
}

.project-image {
  height: 55px;
  flex-shrink: 0;
  margin-top: 0.65rem;
}

.featured-image img,
.project-image img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: contain;
  transition: transform 0.3s ease;
}

.project-featured:hover img,
.project-card:hover img {
  transform: scale(1.05);
}

.image-placeholder {
  display: flex;
  width: 100%;
  height: 100%;
  align-items: center;
  justify-content: center;
  padding: 0.4rem;
  color: #75bcff;
  font-size: 0.7rem;
  font-weight: 700;
  text-align: center;
}

@media (prefers-reduced-motion: reduce) {
  .project-card,
  .project-featured,
  .project-card img,
  .project-featured img {
    transition: none;
  }

  .project-card:hover,
  .project-featured:hover {
    transform: none;
  }
}

@media (max-width: 700px) {
  .projects-section {
    padding: 2.5rem 1rem;
  }

  .projects-layout {
    grid-template-columns: 1fr;
  }

  .other-projects {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 480px) {
  .other-projects {
    grid-template-columns: 1fr;
  }

  .project-image {
    height: 90px;
  }
}
.project-card,
.project-featured {
  position: relative;
  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease,
    border-color 0.3s ease;
  transform-origin: center;
  will-change: transform;
}

.project-card:hover,
.project-featured:hover {
  transform: translateY(-8px) scale(1.03);
  border-color: #3b9eff;
  box-shadow: 0 12px 30px rgba(59, 158, 255, 0.3);
  z-index: 10;
}


.project-card img,
.project-featured img {
  transition: transform 0.35s ease;
}

.project-card:hover img,
.project-featured:hover img {
  transform: scale(1.08);
}

</style>