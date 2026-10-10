
<script setup lang="ts">
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import {
  faFacebook,
  faGithub,
  faLinkedin
} from '@fortawesome/free-brands-svg-icons'
import { faEnvelope } from '@fortawesome/free-solid-svg-icons'
</script>

<template>
  <footer class="bg-[#1A2D42] text-[#D4D8DD] py-8 px-6">
    <div class="max-w-6xl mx-auto flex flex-col items-center gap-5">

      <div class="flex items-center gap-6 text-2xl">
        <a
          href="https://www.facebook.com/rica.fernando.71"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Facebook"
          class="text-[#AAB7B7] hover:text-white transition"
        >
          <FontAwesomeIcon :icon="faFacebook" />
        </a>

        <a
          href="https://github.com/bluerics"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="GitHub"
          class="text-[#AAB7B7] hover:text-white transition"
        >
          <FontAwesomeIcon :icon="faGithub" />
        </a>

        <a
          href="mailto:callosricas@example.com"
          aria-label="Email"
          class="text-[#AAB7B7] hover:text-white transition"
        >
          <FontAwesomeIcon :icon="faEnvelope" />
        </a>

        <a
          href="https://www.linkedin.com/in/rica-fernando/"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="LinkedIn"
          class="text-[#AAB7B7] hover:text-white transition"
        >
          <FontAwesomeIcon :icon="faLinkedin" />
        </a>
      </div>

      <div class="w-full max-w-md border-t border-[#2E4156]"></div>

      <p class="text-sm text-center text-[#C0C8CA]">
        © 2026 Rica Fernando. All rights reserved.
      </p>

      <p class="text-xs text-center text-[#AAB7B7]">
        Designed & built with care.
      </p>

    </div>
  </footer>
</template>

