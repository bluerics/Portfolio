<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const showNavbar = ref(false)

const handleScroll = () => {
  showNavbar.value = window.scrollY > 80
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <nav
    class="fixed left-0 top-0 z-50 w-full overflow-hidden border-b border-white/10 transition-all duration-500"
    :class="
      showNavbar
        ? 'translate-y-0 opacity-100'
        : '-translate-y-full opacity-0'
    "
  >
    <!--background -->
    <div class="absolute inset-0 -z-10">
      <video
        src="@/assets/bg.mp4"
        autoplay
        muted
        loop
        playsinline
        class="h-full w-full object-cover"
      ></video>

      <!-- Dark overlay -->
      <div class="absolute inset-0 bg-[#03363D]/65"></div>
    </div>

    <!-- Navbar content -->
    <div
      class="relative mx-auto flex max-w-6xl items-center justify-between px-6 py-4"
    >
      <!-- Logo -->
      <a
        href="#home"
        class="text-xl font-bold text-white transition hover:text-[#34E0A1]"
      >
        Rica<span class="text-[#34E0A1]">.</span>
      </a>

      <!-- Links -->
      <div class="flex gap-6">
        <a
          href="#home"
          class="text-white transition hover:text-[#34E0A1]"
        >
          Home
        </a>

        <a
          href="#about"
          class="text-white transition hover:text-[#34E0A1]"
        >
          About
        </a>

        <a
          href="#skills"
          class="text-white transition hover:text-[#34E0A1]"
        >
          Skills
        </a>

        <a
          href="#projects"
          class="text-white transition hover:text-[#34E0A1]"
        >
          Projects
        </a>

        <a
          href="#contact"
          class="text-white transition hover:text-[#34E0A1]"
        >
          Contact
        </a>
      </div>
    </div>
  </nav>
</template>