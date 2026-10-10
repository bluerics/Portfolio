<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const showNavbar = ref(false)
const menuOpen = ref(false)

const handleScroll = () => {
  showNavbar.value = window.scrollY > 80
}

const closeMenu = () => {
  menuOpen.value = false
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
    class="fixed left-0 top-0 z-50 w-full border-b border-white/10 bg-[#1A2D42]/80 backdrop-blur-md transition-all duration-500"
    :class="
      showNavbar
        ? 'translate-y-0 opacity-100'
        : '-translate-y-full opacity-0'
    "
  >
    <div
      class="mx-auto flex max-w-6xl items-center justify-between gap-4 px-6 py-4"
    >
     
      <a
        href="#home"
        class="shrink-0 text-2xl font-bold text-white transition hover:text-[#D4D8DD]"
        @click="closeMenu"
      >
        Rica<span class="text-[#D4D8DD]">.</span>
      </a>

      
      <div class="hidden items-center justify-end gap-5 text-lg md:flex lg:gap-6">
        <a href="#home" class="nav-link">Home</a>
        <a href="#about" class="nav-link">About</a>
        <a href="#skills" class="nav-link">Skills</a>
        <a href="#projects" class="nav-link">Projects</a>
        <a href="#contact" class="nav-link">Contact</a>

        <a
          href="/CV.pdf"
          download="CV.pdf"
          class="inline-flex shrink-0 items-center gap-2 rounded-lg bg-[#D4D8DD] px-4 py-2.5 text-sm font-bold text-[#1A2D42] shadow-lg shadow-[#D4D8DD]/10 transition duration-300 hover:-translate-y-1 hover:bg-[#AAB7B7] hover:shadow-[#D4D8DD]/25"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="18"
            height="18"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4" />
            <path d="m7 10 5 5 5-5" />
            <path d="M12 15V3" />
          </svg>
          Download CV
        </a>
      </div>

      
      <button
        type="button"
        class="inline-flex items-center justify-center rounded-lg border border-white/15 p-2 text-[#D4D8DD] transition hover:bg-white/10 focus:outline-none focus:ring-2 focus:ring-[#D4D8DD] md:hidden"
        :aria-expanded="menuOpen"
        aria-label="Toggle navigation menu"
        aria-controls="mobile-navigation"
        @click="menuOpen = !menuOpen"
      >
        <!-- Hamburger Icon -->
        <svg
          v-if="!menuOpen"
          xmlns="http://www.w3.org/2000/svg"
          width="26"
          height="26"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <line x1="4" y1="6" x2="20" y2="6" />
          <line x1="4" y1="12" x2="20" y2="12" />
          <line x1="4" y1="18" x2="20" y2="18" />
        </svg>

        
        <svg
          v-else
          xmlns="http://www.w3.org/2000/svg"
          width="26"
          height="26"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <line x1="18" y1="6" x2="6" y2="18" />
          <line x1="6" y1="6" x2="18" y2="18" />
        </svg>
      </button>
    </div>

    
    <div
      v-if="menuOpen"
      id="mobile-navigation"
      class="border-t border-white/10 bg-[#1A2D42]/95 px-6 py-5 shadow-xl backdrop-blur-md md:hidden"
    >
      <div class="mx-auto flex max-w-6xl flex-col gap-2">
        <a href="#home" class="mobile-link" @click="closeMenu">Home</a>
        <a href="#about" class="mobile-link" @click="closeMenu">About</a>
        <a href="#skills" class="mobile-link" @click="closeMenu">Skills</a>
        <a href="#projects" class="mobile-link" @click="closeMenu">Projects</a>
        <a href="#contact" class="mobile-link" @click="closeMenu">Contact</a>

        <a
          href="/CV.pdf"
          download="CV.pdf"
          class="mt-3 inline-flex items-center justify-center gap-2 rounded-lg bg-[#D4D8DD] px-4 py-3 text-center text-sm font-bold text-[#1A2D42] transition hover:bg-[#AAB7B7]"
          @click="closeMenu"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="18"
            height="18"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4" />
            <path d="m7 10 5 5 5-5" />
            <path d="M12 15V3" />
          </svg>
          Download CV
        </a>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.nav-link {
  color: #aab7b7;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #d4d8dd;
}

.mobile-link {
  display: block;
  border-radius: 0.5rem;
  padding: 0.75rem 1rem;
  color: #aab7b7;
  transition:
    color 0.3s ease,
    background-color 0.3s ease;
}

.mobile-link:hover {
  color: #d4d8dd;
  background-color: rgb(255 255 255 / 8%);
}

@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    transition-duration: 0.01ms !important;
  }
}
</style>
