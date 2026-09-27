<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'

const element = ref<HTMLElement | null>(null)

let observer: IntersectionObserver | null = null

onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('show')
        } else {
          entry.target.classList.remove('show')
        }
      })
    },
    {
      threshold: 0.15,
    }
  )

  if (element.value) {
    observer.observe(element.value)
  }
})

onUnmounted(() => {
  observer?.disconnect()
})
</script>

<template>
  <div ref="element" class="scroll-reveal">
    <slot />
  </div>
</template>