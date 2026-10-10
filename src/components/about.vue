<script setup lang="ts">
import { ref } from 'vue'
import ScrollReveal from '@/components/ScrollReveal.vue'

import profile from '@/assets/profile.png'
import photo1 from '@/assets/photos/photo1.jpg'
import photo2 from '@/assets/photos/photo2.jpg'
import photo3 from '@/assets/photos/photo3.jpg'
import photo4 from '@/assets/photos/photo4.jpg'
import photo5 from '@/assets/photos/photo5.jpg'
import photo6 from '@/assets/photos/photo6.jpg'
import photo7 from '@/assets/photos/photo7.jpg'
import photo8 from '@/assets/photos/photo8.jpg'
import photo9 from '@/assets/photos/photo9.jpg'
import photo10 from '@/assets/photos/photo10.jpg'

const photos = [
  photo1,
  photo2,
  photo3,
  photo4,
  photo5,
  photo6,
  photo7,
  photo8,
  photo9,
  photo10,
]

const focusAreas = [
  'Software Development',
  'Artificial Intelligence',
  'Embedded Systems',
  'Computer Vision',
  'Web Development',
  'Databases',
]

const currentPhoto = ref(0)

const nextPhoto = () => {
  currentPhoto.value = (currentPhoto.value + 1) % photos.length
}

const previousPhoto = () => {
  currentPhoto.value =
    (currentPhoto.value - 1 + photos.length) % photos.length
}
</script>

<template>
  <section
    id="about"
    class="flex min-h-screen items-center bg-[#1A2D42] px-6 py-24 text-[#D4D8DD]"
  >
    <div class="mx-auto w-full max-w-6xl">
      <ScrollReveal>
        
        <div class="mb-14 text-center">
          <p
            class="mb-2 text-sm font-semibold uppercase tracking-[0.3em] text-[#AAB7B7]"
          >
            Get to know me
          </p>

          <h2 class="text-5xl font-bold text-[#D4D8DD] sm:text-5xl">
            About <span class="text-[#AAB7B7]">Me</span>
          </h2>
        </div>

        
        <div
          class="grid items-center gap-10 lg:grid-cols-[0.9fr_1.1fr] lg:gap-14"
        >
        
          <div class="mx-auto w-full max-w-[470px]">
            <div class="mb-5">
              <p
                class="text-sm font-semibold uppercase tracking-[0.2em] text-[#AAB7B7]"
              >
                My Journey
              </p>

              <h4 class="mt-2 text-2xl font-bold text-[#D4D8DD]">
                Photos
              </h4>
            </div>

            <div class="ab-frame">
              <img
                :src="photos[currentPhoto]"
                :key="currentPhoto"
                alt="Photo of Rica"
                class="ab-photo"
              />

              <button
                type="button"
                class="ab-arrow ab-arrow-left"
                aria-label="Previous photo"
                @click="previousPhoto"
              >
                ←
              </button>

              <button
                type="button"
                class="ab-arrow ab-arrow-right"
                aria-label="Next photo"
                @click="nextPhoto"
              >
                →
              </button>

              <span class="ab-counter">
                {{ currentPhoto + 1 }} / {{ photos.length }}
              </span>
            </div>

            
            <div class="ab-thumbs">
              <button
                v-for="(photo, index) in photos"
                :key="index"
                type="button"
                class="ab-thumb"
                :class="{ 'ab-thumb-active': index === currentPhoto }"
                :aria-label="`Show photo ${index + 1}`"
                :aria-pressed="index === currentPhoto"
                @click="currentPhoto = index"
              >
                <img :src="photo" alt="" />
              </button>
            </div>
          </div>

          
          <div class="ab-panel">
           
            <div class="flex items-center gap-5">
              <div class="ab-avatar">
                <img :src="profile" alt="Rica Fernando" />
              </div>

              <div>
                <h3 class="text-xl font-bold text-[#D4D8DD]">
                  Rica Fernando
                </h3>

                <p class="mt-1 text-[#AAB7B7]">
                  Computer Engineering Student
                </p>
              </div>
            </div>

            <div class="ab-divider"></div>

            <p
              class="text-sm font-semibold uppercase tracking-[0.2em] text-[#AAB7B7]"
            >
              Who I am
            </p>

            <h3 class="mt-2 text-2xl font-bold text-[#D4D8DD] sm:text-3xl">
              Building ideas into
              <span class="text-[#AAB7B7]">technology.</span>
            </h3>

            <p class="mt-4 text-sm leading-7 text-[#C0C8CA]">
              I am a Computer Engineering student with a strong interest
              in technology, software development, artificial
              intelligence, and embedded systems. I like understanding
              how things work from the circuit level up to the
              applications that people actually use.
            </p>

            <p class="mt-3 text-sm leading-7 text-[#C0C8CA]">
              I enjoy learning how hardware and software can work
              together to create useful and innovative solutions.
              Through my academic projects, I have explored web
              development,artificial intelligence,
              databases, and embedded systems, including an AI-powered
              sign language translation system, an embedded systems
              project, and a web-based pharmacy inventory system.
            </p>

            <p class="mt-3 text-sm leading-7 text-[#C0C8CA]">
              I am continuously developing my skills, learning new tools,
              and looking forward to creating technology that can solve
              real-world problems and make a positive difference.
            </p>

            <div class="ab-tags mt-6 flex flex-wrap gap-2">
              <span
                v-for="area in focusAreas"
                :key="area"
                class="skill-tag"
              >
                {{ area }}
              </span>
            </div>
          </div>
        </div>
      </ScrollReveal>
    </div>
  </section>
</template>

<style scoped>

#about {
  background: #1A2D42;
  color: #D4D8DD;
}


.ab-frame {
  position: relative;
  width: 100%;
  aspect-ratio: 5 / 4;
  max-height: 520px;
  overflow: hidden;
  border: 1px solid rgba(170, 183, 183, 0.35);
  border-radius: 1rem;
  background: #2E4156;
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
  transition:
    border-color 0.3s ease,
    box-shadow 0.3s ease;
}

.ab-frame:hover {
  border-color: #AAB7B7;
  box-shadow: 0 18px 40px rgba(0, 0, 0, 0.25);
}

.ab-photo {
  position: absolute;
  inset: 0;
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
  animation: abFade 0.45s ease;
}

@keyframes abFade {
  from {
    opacity: 0;
    transform: scale(1.03);
  }

  to {
    opacity: 1;
    transform: scale(1);
  }
}


.ab-arrow {
  position: absolute;
  top: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 42px;
  height: 42px;
  border: 1px solid rgba(212, 216, 221, 0.4);
  border-radius: 50%;
  background: rgba(26, 45, 66, 0.85);
  color: #D4D8DD;
  font-size: 1.2rem;
  font-weight: bold;
  cursor: pointer;
  transform: translateY(-50%);
  transition:
    transform 0.3s ease,
    border-color 0.3s ease,
    background 0.3s ease;
}

.ab-arrow:hover {
  transform: translateY(-50%) scale(1.08);
  border-color: #D4D8DD;
  background: #2E4156;
}

.ab-arrow:focus-visible,
.ab-thumb:focus-visible {
  outline: 2px solid #D4D8DD;
  outline-offset: 3px;
}

.ab-arrow-left {
  left: 12px;
}

.ab-arrow-right {
  right: 12px;
}


.ab-counter {
  position: absolute;
  right: 12px;
  bottom: 12px;
  padding: 0.3rem 0.75rem;
  border: 1px solid rgba(212, 216, 221, 0.25);
  border-radius: 9999px;
  background: rgba(26, 45, 66, 0.9);
  color: #D4D8DD;
  font-size: 0.75rem;
  font-weight: 600;
}


.ab-thumbs {
  display: flex;
  gap: 0.6rem;
  margin-top: 1rem;
  padding: 2px 2px 0.6rem;
  overflow-x: auto;
  scrollbar-width: thin;
  scrollbar-color: #AAB7B7 #2E4156;
}

.ab-thumb {
  flex: 0 0 auto;
  width: 58px;
  height: 58px;
  overflow: hidden;
  border: 2px solid transparent;
  border-radius: 0.65rem;
  background: #2E4156;
  opacity: 0.65;
  cursor: pointer;
  transition:
    opacity 0.3s ease,
    border-color 0.3s ease,
    transform 0.3s ease;
}

.ab-thumb img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.ab-thumb:hover {
  opacity: 0.9;
  transform: translateY(-2px);
}

.ab-thumb-active {
  opacity: 1;
  border-color: #D4D8DD;
}

.ab-panel {
  width: 100%;
  min-width: 0;
  padding: 0;
  border: none;
  border-radius: 0;
  background: transparent;
  box-shadow: none;
}


.ab-avatar {
  flex: 0 0 auto;
  width: 68px;
  height: 68px;
  overflow: hidden;
  border: 2px solid #AAB7B7;
  border-radius: 50%;
  background: #2E4156;
}

.ab-avatar img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}


.ab-divider {
  height: 1px;
  margin: 1.4rem 0;
  background: linear-gradient(to right, #AAB7B7, transparent);
}


.ab-tags .skill-tag {
  display: inline-block;
  padding: 0.4rem 0.75rem;
  border: 1px solid rgba(170, 183, 183, 0.25);
  border-radius: 9999px;
  background: #2E4156;
  color: #D4D8DD;
  font-size: 0.8rem;
  transition:
    background 0.3s ease,
    border-color 0.3s ease;
}

.ab-tags .skill-tag:hover {
  border-color: #AAB7B7;
  background: #364D64;
}


@media (max-width: 1023px) {
  .ab-frame {
    max-width: 400px;
    max-height: 480px;
    margin-inline: auto;
  }

  .ab-thumbs {
    max-width: 400px;
    margin-inline: auto;
    margin-top: 1rem;
  }

  .ab-panel {
    max-width: 650px;
    margin-inline: auto;
  }
}

@media (max-width: 640px) {
  #about {
    padding-top: 6rem;
    padding-bottom: 5rem;
  }

  .ab-frame {
    max-width: 330px;
    max-height: 420px;
  }

  .ab-thumb {
    width: 52px;
    height: 52px;
  }

  .ab-avatar {
    width: 60px;
    height: 60px;
  }
}

@media (prefers-reduced-motion: reduce) {
  .ab-photo {
    animation: none;
  }

  .ab-arrow,
  .ab-thumb,
  .ab-frame,
  .ab-tags .skill-tag {
    transition: none;
  }
}
</style>

