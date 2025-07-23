<template>
  <div ref="container" class="title-container">
    <div>
      <h2 ref="title" class="title"><slot name="title" /></h2>
      <p ref="titleSymbols" class="title-symbols"><slot name="title-symbols" /></p>
    </div>
    <p ref="introText"><slot name="intro-text" /></p>
  </div>
</template>

<style scoped>
.title-container{
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.title-symbols{
  margin-top: 0.5rem;
  color: var(--color-primary);
}

@media (min-width: 1024px) {
  .title-container{
      max-width: 50%;
  }
}
</style>

<style>
.alt-font{
  font-family: 'Distant Galaxy Outline';
  font-weight: normal;
}
</style>

<script setup lang="ts">
import { onMounted, ref } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger) 


const container = ref<HTMLElement | null>(null)
const title = ref<HTMLElement | null>(null)
const titleSymbols = ref<HTMLElement | null>(null)
const introText = ref<HTMLElement | null>(null)


onMounted(() => {
gsap.timeline({
    scrollTrigger: {
      trigger: container.value,
      start: 'top 80%',
      once: true,
      toggleActions: 'restart none none none',
    }
  })
  .from(title.value, { opacity: 0, y: 50, duration: 0.8, ease: 'power2.out' })
  .from(titleSymbols.value, { opacity: 0, y: 30, duration: 0.6, ease: 'power2.out' }, '-=0.4')
  .from(introText.value, { opacity: 0, y: 20, duration: 0.6, ease: 'power2.out' }, '-=0.3')

})

</script>