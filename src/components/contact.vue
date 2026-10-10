<script setup lang="ts">
import { ref } from 'vue'
import ScrollReveal from '@/components/ScrollReveal.vue'

type ContactType = 'email' | 'github' | 'linkedin' | null

const activeContact = ref<ContactType>(null)

const email = 'callosrica@gmail.com'
const githubUsername = 'bluerics'
const linkedinUsername = 'Rica Fernando'

const openContact = (type: ContactType) => {
  activeContact.value = type
}

const closeContact = () => {
  activeContact.value = null
}
</script>

<template>
  <section
    id="contact"
    class="flex min-h-screen items-center px-6 py-24"
  >
    <div class="mx-auto w-full max-w-6xl">
      <ScrollReveal>

       
        <div class="mb-14 text-center">
          <p
            class="mb-2 text-sm font-semibold uppercase tracking-[0.3em] text-[#AAB7B7]"
          >
            Let's connect
          </p>

          <h2 class="text-5xl font-bold text-white">
            Open a
            <span class="text-[#D4D8DD]">Connection</span>
          </h2>

          <p
            class="mx-auto mt-5 max-w-2xl leading-7 text-[#D4D8DD]"
          >
            Have an idea, project, or opportunity? You can find me
            through the channels below.
          </p>
        </div>

        <!-- Connection Terminal -->
        <div class="connection-terminal">
          <div class="terminal-glow"></div>

         
          <div
            class="relative flex items-center justify-between border-b border-[#AAB7B7]/20 px-6 py-4"
          >
            <div class="flex items-center gap-2">
              <span class="terminal-dot"></span>

              <span
                class="text-xs font-semibold tracking-[0.2em] text-[#AAB7B7]"
              >
                CONNECTION TERMINAL
              </span>
            </div>

            <span class="text-xs text-[#C0C8CA]">
              ONLINE
            </span>
          </div>

          
          <div
            class="relative grid items-center gap-12 p-8 md:grid-cols-2 md:p-12"
          >

            
            <div>
              <p class="text-sm text-[#AAB7B7]">
                STATUS
              </p>

              <div class="mt-3 flex items-center gap-3">
                <span class="status-pulse"></span>

                <span class="font-semibold text-white">
                  Available for collaboration
                </span>
              </div>

              <h3
                class="mt-8 text-3xl font-bold leading-tight text-white md:text-4xl"
              >
                Let's build something
                <span class="text-[#D4D8DD]">
                  meaningful.
                </span>
              </h3>

              <p
                class="mt-5 max-w-md leading-7 text-[#D4D8DD]"
              >
                Whether it's software, artificial intelligence,
                embedded systems, or a new idea worth exploring,
                feel free to reach out.
              </p>

              
              <button
                type="button"
                @click="openContact('email')"
                class="mt-8 inline-flex items-center gap-3 rounded-lg bg-[#D4D8DD] px-6 py-3 font-semibold text-[#1A2D42] transition duration-300 hover:-translate-y-1 hover:bg-[#AAB7B7] hover:shadow-[0_0_25px_rgba(52,224,161,0.25)]"
              >
                Send a message
                <span>→</span>
              </button>
            </div>

            
            <div class="orbit-container">

              <!-- Orbit Rings -->
              <div class="orbit-ring orbit-ring-one"></div>
              <div class="orbit-ring orbit-ring-two"></div>

              
              <div class="orbit-center">
                <span>R</span>
                <div></div>
              </div>

              
              <button
                type="button"
                class="orbit-item orbit-email"
                aria-label="Email"
                @click="openContact('email')"
              >
                <span class="orbit-icon">@</span>
                <span>Email</span>
              </button>

              
              <button
                type="button"
                class="orbit-item orbit-github"
                aria-label="GitHub"
                @click="openContact('github')"
              >
                <span class="orbit-icon">GH</span>
                <span>GitHub</span>
              </button>

              
              <button
                type="button"
                class="orbit-item orbit-linkedin"
                aria-label="LinkedIn"
                @click="openContact('linkedin')"
              >
                <span class="orbit-icon">in</span>
                <span>LinkedIn</span>
              </button>

            </div>
          </div>

          
          <div
            class="relative border-t border-[#AAB7B7]/20 px-6 py-4 text-center"
          >
            <p
              class="text-xs tracking-[0.15em] text-[#C0C8CA]"
            >
              CONNECTION READY • LET'S CREATE
            </p>
          </div>
        </div>

      </ScrollReveal>
    </div>
  </section>

  
  <div
    v-if="activeContact"
    class="contact-popup-overlay"
    @click.self="closeContact"
  >
    <div class="contact-popup">

      
      <button
        type="button"
        class="contact-close"
        aria-label="Close"
        @click="closeContact"
      >
        ×
      </button>

      
      <template v-if="activeContact === 'email'">
        <div class="contact-popup-icon">
          @
        </div>

        <p class="text-sm text-[#AAB7B7]">
          EMAIL
        </p>

        <h3 class="mt-2 break-all text-xl font-bold text-white">
          {{ email }}
        </h3>

        <p class="mt-3 text-sm text-[#D4D8DD]">
          Send me a message through email.
        </p>

        <a
          :href="`mailto:${email}`"
          class="mt-6 inline-flex rounded-lg bg-[#D4D8DD] px-5 py-3 font-semibold text-[#1A2D42] transition hover:bg-[#AAB7B7]"
        >
          Send Email →
        </a>
      </template>

      
      <template v-if="activeContact === 'github'">
        <div class="contact-popup-icon">
          GH
        </div>

        <p class="text-sm text-[#AAB7B7]">
          GITHUB
        </p>

        <h3 class="mt-2 text-2xl font-bold text-white">
          {{ githubUsername }}
        </h3>

        <p class="mt-3 text-sm text-[#D4D8DD]">
          Check out my GitHub profile and projects.
        </p>

        <a
          href="https://github.com/bluerics"
          target="_blank"
          rel="noopener noreferrer"
          class="mt-6 inline-flex rounded-lg bg-[#D4D8DD] px-5 py-3 font-semibold text-[#1A2D42] transition hover:bg-[#AAB7B7]"
        >
          Visit GitHub →
        </a>
      </template>

      
      <template v-if="activeContact === 'linkedin'">
        <div class="contact-popup-icon">
          in
        </div>

        <p class="text-sm text-[#AAB7B7]">
          LINKEDIN
        </p>

        <h3 class="mt-2 text-2xl font-bold text-white">
          {{ linkedinUsername }}
        </h3>

        <p class="mt-3 text-sm text-[#D4D8DD]">
          Connect with me on LinkedIn.
        </p>

        <a
          :href="`https://www.linkedin.com/in/rica-fernando`"
          target="_blank"
          rel="noopener noreferrer"
          class="mt-6 inline-flex rounded-lg bg-[#D4D8DD] px-5 py-3 font-semibold text-[#1AD42] transition hover:bg-[#AAB7B7]"
        >
          Visit LinkedIn →
        </a>
      </template>

    </div>
  </div>
</template>