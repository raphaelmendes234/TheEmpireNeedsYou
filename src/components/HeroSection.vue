<template>
    <img class="background-image" src="/images/dark-vador.webp" alt="dark vador">
    <div class="title-container">
      <h1 class="title">L'empire</h1>
      <p class="title-symbols">l empire</p>
      <p class="subtitle">recrute, et il a besoin de toi</p>
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
  background: linear-gradient(180deg, rgba(var(--color-background-rgb), 0.5) 50%, rgb(var(--color-background-rgb), 1) 100%);
}
.title{
  background: -webkit-linear-gradient(var(--color-primary), var(--color-background));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.title-symbols{
    font-size: 1.5rem;
    color: var(--color-primary);
}
.subtitle{
  font-family: 'Stereo Gothic 500';
  font-size: 1.5rem;
  color: var(--color-text);
}

@media (min-width: 1024px) {
  .title-container{
    padding: 4rem;
  }
}

</style>
