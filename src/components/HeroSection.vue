<template>
    <div class="title-container">
      <h1 ref="title" class="title">L'empire</h1>
      <p ref="titleSymbols" class="title-symbols">l empire</p>
      <p ref="subtitle" class="subtitle">recrute, et il a besoin de toi</p>
    </div>
</template>

<style scoped>
.background-image{
  z-index: 1;
  position: absolute;
  bottom: 6rem;
  left: 0;
  width: 100%;
}
.title-container{
  z-index: 10;
  width: 100%;
  height: 100%;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  background: linear-gradient(180deg, rgba(var(--color-background-rgb), 0.5) 30%, rgb(var(--color-background-rgb), 1) 100%);
}
.title{
  background: -webkit-linear-gradient(var(--color-primary), var(--color-background));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.title-symbols{
  opacity: 0.5;
    color: var(--color-primary);
}
.subtitle{
  margin-top: 0.5rem;
  font-family: 'Stereo Gothic 500';
  font-size: 0.75rem;
  color: var(--color-text);
}

@media (min-width: 768px) { 
  .title-container{
    background: linear-gradient(180deg, rgba(var(--color-background-rgb), 0.5) 30%, rgb(var(--color-background-rgb), 1) 80%);
  }
  .subtitle{
    font-size: 1rem;
  }  
}

@media (min-width: 1024px) {
  .title-container{
    padding: 4rem;
    background: linear-gradient(180deg, rgba(var(--color-background-rgb), 0.5) 30%, rgb(var(--color-background-rgb), 1) 80%);
  }
  .subtitle{
    font-size: 1.5rem;
  }
}

</style>

<script setup lang="ts">
import { onMounted, ref } from 'vue'
import gsap from 'gsap'

const title = ref<HTMLElement | null>(null)
const titleSymbols = ref<HTMLElement | null>(null)
const subtitle = ref<HTMLElement | null>(null)


onMounted(() => {
  const tl = gsap.timeline({delay: 1})

  tl.from(title.value, { opacity: 0, y: 50, duration: 0.8, ease: 'power2.out'})
  tl.from(titleSymbols.value, { opacity: 0, y: 30, duration: 0.6, ease: 'power2.out'}, '-=0.4')
  tl.from(subtitle.value, { opacity: 0, y: 20, duration: 0.6, ease: 'power2.out'}, '-=0.3')

})

</script>