<script setup lang="ts">
import profile from '@/assets/profile.png'
import ScrollReveal from '@/components/ScrollReveal.vue'
</script>

<template>
  <section
    id="about"
    class="flex min-h-screen items-center px-6 py-24"
  >
    <div class="mx-auto w-full max-w-6xl">

      <ScrollReveal>

        <!-- Section Title -->
        <div class="mb-12 text-center">
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

        <!-- About Content -->
        <div class="grid items-center gap-10 md:grid-cols-2">

          <!-- ================= PHOTO ================= -->
          <div class="flex justify-center">
            <div class="photo-perspective">

              <div class="photo-card">

                <!-- Green Glow -->
                <div
                  class="absolute -left-10 -top-10 h-32 w-32 rounded-full bg-[#34E0A1]/20 blur-3xl"
                ></div>

                <!-- Photo -->
                <img
                  :src="profile"
                  alt="Rica Fernando"
                  class="relative h-[420px] w-full rounded-xl object-cover"
                />

                <!-- Photo Label -->
                <div
                  class="absolute bottom-5 left-5 rounded-lg border border-[#67D5D0]/30 bg-black/70 px-4 py-2 backdrop-blur-md"
                >
                  <p class="text-sm font-semibold text-[#34E0A1]">
                    Computer Engineering
                  </p>
                </div>

              </div>

            </div>
          </div>

          <!-- ================= MESSAGE ================= -->
          <div
            class="rounded-2xl border border-[#67D5D0]/30 bg-[#03363D]/70 p-8 shadow-2xl backdrop-blur-md transition duration-500 hover:border-[#34E0A1]"
          >

            <h3 class="text-3xl font-bold text-white">
              Hello! I'm
              <span class="text-[#34E0A1]">
                Rica Fernando
              </span>
            </h3>

            <p class="mt-6 leading-8 text-[#D9F3F1]">
              I am a Computer Engineering student with an interest in
              technology, software development, artificial intelligence,
              and embedded systems.
            </p>

            <p class="mt-5 leading-8 text-[#D9F3F1]">
              I enjoy learning how hardware and software can work
              together to create useful and innovative solutions.
              Through my academic projects, I have explored web
              development, computer vision, artificial intelligence,
              databases, and embedded systems.
            </p>

            <p class="mt-5 leading-8 text-[#D9F3F1]">
              I am continuously developing my skills and looking
              forward to creating technology that can solve real-world
              problems.
            </p>

            <!-- Information Cards -->
            <div class="mt-8 grid gap-4 sm:grid-cols-2">

              <!-- Field -->
              <div
                class="rounded-lg border border-[#67D5D0]/20 bg-black/20 p-4 transition duration-300 hover:border-[#34E0A1]"
              >
                <p class="text-sm text-[#A8D5D2]">
                  Field
                </p>

                <p class="mt-1 font-semibold text-white">
                  Computer Engineering
                </p>
              </div>

              <!-- Interests -->
              <div
                class="rounded-lg border border-[#67D5D0]/20 bg-black/20 p-4 transition duration-300 hover:border-[#34E0A1]"
              >
                <p class="text-sm text-[#A8D5D2]">
                  Interests
                </p>

                <p class="mt-1 font-semibold text-white">
                  AI & Software
                </p>
              </div>

            </div>

          </div>

        </div>

      </ScrollReveal>

    </div>
  </section>
</template>