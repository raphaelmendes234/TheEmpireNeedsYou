<script setup lang="ts">
import HeroSection from './components/HeroSection.vue';
import IconAmbition from './components/icons/IconAmbition.vue';
import IconLoyalty from './components/icons/IconLoyalty.vue';
import IconPower from './components/icons/IconPower.vue';
import SectionTitle from './components/SectionTitle.vue';
import StrenghtCard from './components/StrenghtCard.vue';
</script>

<template>
  <header>
    <HeroSection></HeroSection>
  </header>

  <main>
    <section>
      <SectionTitle>
        <template #title>
          Nos
          <span class="alt-font">forces</span>
        </template>
        <template #title-symbols>nos forces</template>
        <template #intro-text>Plonge dans l'essence du Côté Obscur : une philosophie rigoureusement sélective, impitoyablement ambitieuse… et étonnamment cohérente.</template>
      </SectionTitle>
      
      <div class="grid-container">
        <div></div>
        <div>
          <StrenghtCard>
            <template #icon><IconPower /></template>
            <template #title>Pouvoir</template>
            <template #title-symbols>pouvoir</template>
            <template #text>La Force n’est pas un outil, c’est une arme. Rejoins-nous pour en maîtriser les moindres recoins : lévitation, étranglement mental, contrôle des esprits... Tu ne suivras plus jamais les ordres : tu les donneras.</template>
          </StrenghtCard>
        </div>
        <div>
          <StrenghtCard>
            <template #icon><IconAmbition /></template>
            <template #title>Ambition</template>
            <template #title-symbols>ambition</template>
            <template #text>Ici, gravir les échelons n’est pas une option, c’est une vocation. L’échec ? Toléré une fois. Deux fois ? Expulsé dans une chambre sans oxygène. À chaque victoire, une promotion. À chaque défaite, une méditation... forcée.</template>
          </StrenghtCard>
        </div>
        <div>
          <StrenghtCard>
            <template #icon><IconLoyalty /></template>
            <template #title>Loyauté</template>
            <template #title-symbols>loyaute</template>
            <template #text>Ton libre arbitre ? On te le laisse… jusqu’à ce que l’Empereur te le reprenne. Une seule ligne de conduite : servir le plan de domination galactique. Un seul patron : Sa Majesté Palpatine. La trahison ? Très mauvaise idée.</template>
          </StrenghtCard>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: 1fr;
}

header{
  position: relative;
  width: 100%;
  height: 50vh;
  box-sizing: border-box;
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  background-color: var(--color-background);
  background: url("/images/dark-vador.webp");
  background-repeat: no-repeat;
  background-position: center 60%;
  background-size: 100%;
}

section{
  width: 100%;
  padding: 1rem;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  gap: 4rem;
}

@media (min-width: 768px) {
  header{
    height: 75vh;
    background-position: center 65%;
    background-size: 75%;
  }
}

@media (min-width: 1024px) {
  header{
    height: 100vh;
    background-position: center 50%;
    background-size: 75%;
  }
  section{
    padding: 4rem;
  }
   .grid-container {
    grid-template-columns: repeat(2, 1fr);
  }
}

</style>
