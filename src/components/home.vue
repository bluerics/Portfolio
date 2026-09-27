<script setup lang="ts">
import profile from '@/assets/profile.png'
</script>

<template>
  <section
    id="home"
    class="flex min-h-screen items-center px-6 pt-20"
  >
    <div
      class="mx-auto grid w-full max-w-6xl items-center gap-12 md:grid-cols-2"
    >

      
      <div class="text-center md:text-left">
        <p class="text-3xl font-bold text-white">
          Hi, I'm
        </p>

        <h1 class="text-7xl font-bold text-[#34E0A1] md:text-6xl">
          Rica Fernando
        </h1>

        <h2 class="mt-4 text-3xl font-semibold text-white">
          Computer Engineering Student
        </h2>

        <p class="mt-6 max-w-xl leading-7 text-[#D9F3F1]">
          I am interested in software development, artificial intelligence,
          embedded systems, and creating useful technology solutions.
        </p>

        <div class="mt-8 flex justify-center gap-4 md:justify-start">
          <a
            href="#projects"
            class="rounded-lg bg-[#67D5D0] px-6 py-3 font-semibold text-[#03363D] transition hover:bg-[#34E0A1]"
          >
            View Projects
          </a>

          <a
            href="#contact"
            class="rounded-lg border border-[#67D5D0] px-6 py-3 font-semibold text-[#BDD9D7] transition hover:border-[#34E0A1]"
          >
            Contact Me
          </a>
        </div>
      </div>

      
      <div class="flex justify-center md:justify-end">
        <div class="perspective">
        <div class="letter-r">
          R
        </div>
        </div>
      </div>

    </div>
  </section>
</template>