<script setup lang="ts">
</script>

<template>
  <div class="title-container">
    <div>
      <h2 class="title"><slot name="title" /></h2>
      <h2 class="title-symbols"><slot name="title-symbols" /></h2>
    </div>
    <p><slot name="intro-text" /></p>
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