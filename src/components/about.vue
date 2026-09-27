<script setup lang="ts">
import { ref } from 'vue'

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

const currentphoto = ref(0)

const nextphoto = () => {
  currentphoto.value =
    (currentphoto.value + 1) % photos.length
}

const previousphoto = () => {
  currentphoto.value =
    (currentphoto.value - 1 + photos.length) %
    photos.length
}
</script>

<template>
  <section
    id="about"
    class="flex min-h-screen items-center px-6 py-24"
  >
    <div class="mx-auto w-full max-w-6xl">

      
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

      
      <div class="about-card">

        
        <div class="about-profile">

          
          <div class="about-photo">
            <img
              :src="profile"
              alt="Rica Fernando"
            />
          </div>

          <h3 class="mt-6 text-2xl font-bold text-white">
            Rica Fernando
          </h3>

          <p class="mt-2 text-[#67D5D0]">
            Computer Engineering Student
          </p>

        </div>


        
        <div class="about-content">

          <p
            class="text-sm font-semibold uppercase tracking-[0.2em] text-[#67D5D0]"
          >
            Who I am
          </p>

          <h3
            class="mt-3 text-3xl font-bold text-white"
          >
            Building ideas into
            <span class="text-[#34E0A1]">
              technology.
            </span>
          </h3>

          <p
            class="mt-5 leading-7 text-[#D9F3F1]"
          >
            I am a Computer Engineering student with an interest
            in technology, software development, artificial
            intelligence, and embedded systems.
          </p>

          <p
            class="mt-4 leading-7 text-[#D9F3F1]"
          >
            I enjoy learning how hardware and software can work
            together to create useful and innovative solutions.
            Through my academic projects, I have explored web
            development, computer vision, artificial intelligence,
            databases, and embedded systems.
          </p>

          <p
            class="mt-4 leading-7 text-[#D9F3F1]"
          >
            I am continuously developing my skills and looking
            forward to creating technology that can solve
            real-world problems.
          </p>


          
          <div class="mt-10">

            <div class="mb-5">
              <p
                class="text-sm font-semibold uppercase tracking-[0.2em] text-[#67D5D0]"
              >
                My Journey
              </p>

              <h4
                class="mt-2 text-2xl font-bold text-white"
              >
                Photos
              </h4>
            </div>


            
            <div class="photo-wrapper">

              <img
                :src="photos[currentphoto]"
                :key="currentphoto"
                alt="photo"
                class="photo-image"
              />

            </div>


            
            <div
              class="mt-5 flex items-center justify-center gap-6"
            >

              
              <button
                type="button"
                class="gallery-button"
                aria-label="Previous photo"
                @click="previousphoto"
              >
                ←
              </button>


              
              <span
                class="min-w-[60px] text-center text-sm font-semibold text-[#BDD9D7]"
              >
                {{ currentphoto + 1 }}
                /
                {{ photos.length }}
              </span>


              
              <button
                type="button"
                class="gallery-button"
                aria-label="Next photo"
                @click="nextphoto"
              >
                →
              </button>

            </div>

          </div>

        </div>

      </div>
    </div>
  </section>
</template>