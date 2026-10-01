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
  'Vision',
  'Web Development',
  'Databases',
]

const currentphoto = ref(0)

const nextphoto = () => {
  currentphoto.value = (currentphoto.value + 1) % photos.length
}

const previousphoto = () => {
  currentphoto.value =
    (currentphoto.value - 1 + photos.length) % photos.length
}
</script>

<template>
  <section
    id="about"
    class="flex min-h-screen items-center bg-[#050608] px-6 py-24"
  >
    <div class="mx-auto w-full max-w-6xl">
      <ScrollReveal>

        
        <div class="mb-14 text-center">
          <p
            class="mb-2 text-sm font-semibold uppercase tracking-[0.3em] text-[#67D5D0]"
          >
            Get to know me
          </p>

          <h2 class="text-5xl font-bold text-white">
            About
            <span class="text-[#34E0A1]">Me</span>
          </h2>
        </div>

        <div class="grid items-stretch gap-12 lg:grid-cols-[1.05fr_1fr]">

          <!-- Left: photo gallery -->
          <div>
            <div class="mb-5">
              <p
                class="text-sm font-semibold uppercase tracking-[0.2em] text-[#67D5D0]"
              >
                My Journey
              </p>

              <h4 class="mt-2 text-2xl font-bold text-white">
                Photos
              </h4>
            </div>

            <div class="ab-frame">
              <img
                :src="photos[currentphoto]"
                :key="currentphoto"
                alt="Photo of Rica"
                class="ab-photo"
              />

              <button
                type="button"
                class="ab-arrow ab-arrow-left"
                aria-label="Previous photo"
                @click="previousphoto"
              >
                ←
              </button>

              <button
                type="button"
                class="ab-arrow ab-arrow-right"
                aria-label="Next photo"
                @click="nextphoto"
              >
                →
              </button>

              <span class="ab-counter">
                {{ currentphoto + 1 }} / {{ photos.length }}
              </span>
            </div>

            <div class="ab-thumbs">
              <button
                v-for="(photo, index) in photos"
                :key="index"
                type="button"
                class="ab-thumb"
                :class="{ 'ab-thumb-active': index === currentphoto }"
                :aria-label="`Show photo ${index + 1}`"
                @click="currentphoto = index"
              >
                <img :src="photo" alt="" />
              </button>
            </div>
          </div>

          
          <div class="ab-panel-wrap">
          <div class="ab-panel">

            <div class="flex items-center gap-5">
              <div class="ab-avatar">
                <img :src="profile" alt="Rica Fernando" />
              </div>

              <div>
                <h3 class="text-xl font-bold text-white">
                  Rica Fernando
                </h3>

                <p class="mt-1 text-[#67D5D0]">
                  Computer Engineering Student
                </p>
              </div>
            </div>

            <div class="ab-divider"></div>

            <p
              class="text-sm font-semibold uppercase tracking-[0.2em] text-[#67D5D0]"
            >
              Who I am
            </p>

            <h3 class="mt-2 text-2xl font-bold text-white">
              Building ideas into
              <span class="text-[#34E0A1]">technology.</span>
            </h3>

            <p class="mt-4 text-sm leading-6 text-[#D9F3F1]">
              I am a Computer Engineering student with a strong interest
              in technology, software development, artificial
              intelligence, and embedded systems. I like understanding
              how things work from the circuit level up to the
              application that people actually use.
            </p>

            <p class="mt-3 text-sm leading-6 text-[#D9F3F1]">
              I enjoy learning how hardware and software can work
              together to create useful and innovative solutions.
              Through my academic projects, I have explored web
              development, computer vision, artificial intelligence,
              databases, and embedded systems, including an AI-powered
              sign language translation system, an embedded systems
              project, and a web-based pharmacy inventory system.
            </p>

            <p class="mt-3 text-sm leading-6 text-[#D9F3F1]">
              I am continuously developing my skills, learning new tools,
              and looking forward to creating technology that can solve
              real-world problems and make a positive difference.
            </p>

            <div class="ab-tags mt-5 flex flex-wrap gap-2">
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
        </div>

      </ScrollReveal>
    </div>
  </section>
</template>

<style scoped>

.ab-frame {
  position: relative;
  aspect-ratio: 4 / 5;
  max-height: 640px;
  width: 100%;

  overflow: hidden;

  border: 1px solid rgba(103, 213, 208, 0.3);
  border-radius: 1.25rem;

  background: #050608;

  box-shadow: 0 25px 60px rgba(0, 0, 0, 0.35);

  transition:
    border-color 0.4s ease,
    box-shadow 0.4s ease;
}

.ab-frame:hover {
  border-color: rgba(52, 224, 161, 0.6);
  box-shadow:
    0 25px 60px rgba(0, 0, 0, 0.45),
    0 0 40px rgba(52, 224, 161, 0.08);
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

  width: 44px;
  height: 44px;

  border: 1px solid rgba(103, 213, 208, 0.4);
  border-radius: 50%;

  background: rgba(5, 6, 8, 0.75);
  color: #34e0a1;

  font-size: 1.2rem;
  font-weight: bold;

  cursor: pointer;

  transform: translateY(-50%);

  transition:
    transform 0.3s ease,
    border-color 0.3s ease,
    box-shadow 0.3s ease;
}

.ab-arrow:hover {
  transform: translateY(-50%) scale(1.1);
  border-color: #34e0a1;
  box-shadow: 0 0 15px rgba(52, 224, 161, 0.2);
}

.ab-arrow-left {
  left: 14px;
}

.ab-arrow-right {
  right: 14px;
}

.ab-counter {
  position: absolute;
  bottom: 14px;
  right: 14px;

  border: 1px solid rgba(103, 213, 208, 0.3);
  border-radius: 9999px;

  background: rgba(5, 6, 8, 0.75);
  padding: 0.25rem 0.75rem;

  color: #bdd9d7;
  font-size: 0.75rem;
  font-weight: 600;
}


.ab-thumbs {
  display: flex;
  gap: 0.6rem;

  margin-top: 1rem;
  padding-bottom: 0.5rem;

  overflow-x: auto;
}

.ab-thumb {
  flex: 0 0 auto;

  width: 64px;
  height: 64px;

  overflow: hidden;

  border: 2px solid transparent;
  border-radius: 0.75rem;

  background: #050608;

  opacity: 0.5;
  cursor: pointer;

  transition:
    opacity 0.3s ease,
    border-color 0.3s ease,
    transform 0.3s ease;
}

.ab-thumb img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.ab-thumb:hover {
  opacity: 0.85;
  transform: translateY(-2px);
}

.ab-thumb-active {
  opacity: 1;
  border-color: #34e0a1;
}

/* Right panel */
.ab-panel {
  border: 1px solid rgba(103, 213, 208, 0.25);
  border-radius: 1.5rem;

  background: #050608;
  padding: 2rem;

  box-shadow: 0 25px 60px rgba(0, 0, 0, 0.3);

  transition:
    border-color 0.4s ease,
    box-shadow 0.4s ease;
}

.ab-panel:hover {
  border-color: rgba(52, 224, 161, 0.45);
  box-shadow:
    0 25px 60px rgba(0, 0, 0, 0.4),
    0 0 40px rgba(52, 224, 161, 0.08);
}

.ab-avatar {
  flex: 0 0 auto;

  width: 72px;
  height: 72px;

  overflow: hidden;

  border: 3px solid #34e0a1;
  border-radius: 50%;

  box-shadow: 0 0 25px rgba(52, 224, 161, 0.15);
}

.ab-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.ab-tags .skill-tag {
  padding: 0.35rem 0.75rem;
  font-size: 0.8rem;
}

.ab-divider {
  height: 1px;
  margin: 1.25rem 0;

  background: linear-gradient(
    to right,
    rgba(52, 224, 161, 0.5),
    transparent
  );
}


@media (min-width: 1024px) {
  .ab-panel-wrap {
    position: relative;
  }

  .ab-panel {
    position: absolute;
    inset: 0;
    overflow-y: auto;
  }
}

@media (max-width: 640px) {
  .ab-panel {
    padding: 1.75rem 1.25rem;
  }

  .ab-frame {
    aspect-ratio: 1 / 1;
  }
}
</style>