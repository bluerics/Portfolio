<script setup lang="ts">
import photo3 from '@/assets/photos/photo3.jpg'
</script>

<template>
  <section
    id="home"
    class="relative flex min-h-screen items-center overflow-hidden px-6 pt-20"
  >
   
    <div class="home-photo" aria-hidden="true">
      <img :src="photo3" alt="" />
    </div>

    <div
      class="relative z-10 mx-auto grid w-full max-w-6xl items-center gap-12 md:grid-cols-2"
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
          I am a Computer Engineering student with a strong interest in
          software development, artificial intelligence, embedded systems,
          and creating useful technology solutions that solve real-world
          problems.
        </p>

        <p class="mt-4 max-w-xl leading-7 text-[#D9F3F1]">
          I enjoy exploring how hardware and software work together, from
          building web applications and databases to developing computer
          vision and AI-based projects. I am always learning, building, and
          looking for new ways to turn ideas into technology.
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
    </div>
  </section>
</template>

<style scoped>
.home-photo {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  z-index: 0;

  width: 100%;
  opacity: 0.25;
  pointer-events: none;
}

.home-photo img {
  width: 100%;
  height: 100%;

  object-fit: cover;
  object-position: center top;

  -webkit-mask-image:
    linear-gradient(to right, transparent 0%, #000 45%),
    linear-gradient(to top, transparent 0%, #000 30%);
  -webkit-mask-composite: source-in;
  mask-image:
    linear-gradient(to right, transparent 0%, #000 45%),
    linear-gradient(to top, transparent 0%, #000 30%);
  mask-composite: intersect;
}

@media (min-width: 768px) {
  .home-photo {
    width: 55%;
    opacity: 0.85;
  }
}
</style>