<script setup lang="ts">
import SectionTitle from './components/SectionTitle.vue';
</script>

<template>
  <header>
    <div class="title-container">
      <h1>L'empire</h1>
      <p class="title-symbol" style="opacity: 0.5;">l empire</p>
      <p class="subtitle">recrute, et il a besoin de toi</p>
    </div>
  </header>

  <main>
    <section>
      <SectionTitle msg="You did it!" />
    </section>
  </main>

</template>

<style scoped>
header{
  width: 100%;
  height: 100vh;
  padding: 4rem;
  background-color: #000000;
}

.title-container{
  display: flex;
  flex-direction: column;
}
h1{
  font-family: 'Distant galaxy';
  font-size: 8rem;
  font-weight: normal;
  color: #FF0000;
}
.title-symbol{
  font-family: 'Distant galaxy symbols';
  font-size: 1.5rem;
  color: #FF0000;
}
.subtitle{
  font-family: 'Stereo Gothic 500';
  font-size: 1.5rem;
  color: #FFFFFF;
}
</style>
