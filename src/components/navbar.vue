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
    class="fixed left-0 top-0 z-50 w-full border-b border-white/10 bg-[#0A0e12] transition-all duration-500"
    :class="
      showNavbar
        ? 'translate-y-0 opacity-100'
        : '-translate-y-full opacity-0'
    "
  >

    
    <div
      class="relative mx-auto flex max-w-6xl items-center justify-between px-6 py-4"
    >
      
      <a
        href="#home"
        class="text-xl font-bold text-white transition hover:text-[#34E0A1]"
      >
        Portfolio<span class="text-[#34E0A1]">.</span>
      </a>

      
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